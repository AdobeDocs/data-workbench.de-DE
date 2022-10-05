---
description: Erfassen von Aktivitäten über Website-Links von Drittanbietern, um die Target-Analyse für Ausstieg zu ermöglichen.
title: Tracking von Ausstiegen zu externen Links
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Tracking von Ausstiegen zu externen Links{#tracking-exits-to-external-links}

{{eol}}

Erfassen von Aktivitäten über Website-Links von Drittanbietern, um die Target-Analyse für Ausstieg zu ermöglichen.

Webseiten können Links zu Websites von Drittanbietern enthalten und Aktivitäten über diese Links hinweg können erfasst werden, um die Analyse von Exit Target zu ermöglichen, insbesondere dann, wenn die Drittanbieter-Website für die Zahlung von Verweisgebühren zuständig ist, wenn solche Verweise empfangen werden. Da das Klickereignis standardmäßig in die Protokolldateien des Drittanbietersystems geschrieben wird, müssen Änderungen am Link vorgenommen werden, damit das Klickereignis lokal erfasst werden kann. Der in Ihrer Website vorhandene Drittanbieter-Link muss wie folgt geändert werden:

```
<A HREF=”https://www.myserver.com/PageExit.htm?v_eurl=https://www.othersite.com”>
```

Die referenzierte [!DNL PageExit.htm] -Datei muss erstellt werden und sollte so strukturiert sein, dass sie das folgende Skript enthält:

```
<html>
<head>

<script>
function getExitURLQuery(variable)
{

var query = window.location.search.substring(1);
var vars = query.split("&");
for (var i=0; i<vars.length; i++)
{
var pair = vars[i].split("=");
if (pair[0] == variable)
{
return pair[1];
}
 }
}
</script>

<script>
location.replace(getExitURLQuery("v_eurl"));
</script>

</head>
</html>
```

Indem Sie die Anfrage für die [!DNL PageExit.htm] -Datei, wird der Wert v_eurl zu Analysezwecken erfasst. Wenn [!DNL PageExit.htm] geladen wird, wird sofort zum angegebenen Zielspeicherort v_eurl umgeleitet.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_eurl | Wert, der mit der Abfragezeichenfolgenvariablen v_eurl verknüpft ist. Dieser Wert stellt die Ziel-URL des Links dar, der auf der HTML-Seite vorhanden ist. | v_eurl=www.othersite.com |
