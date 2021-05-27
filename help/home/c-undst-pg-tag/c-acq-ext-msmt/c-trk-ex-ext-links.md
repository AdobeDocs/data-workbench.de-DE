---
description: Erfassen von Aktivitäten über Website-Links von Drittanbietern, um die Target-Analyse für Ausstieg zu ermöglichen.
title: Tracking von Ausstiegen zu externen Links
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Tracking von Ausstiegen zu externen Links{#tracking-exits-to-external-links}

Erfassen von Aktivitäten über Website-Links von Drittanbietern, um die Target-Analyse für Ausstieg zu ermöglichen.

Webseiten können Links zu Websites von Drittanbietern enthalten und Aktivitäten über diese Links hinweg können erfasst werden, um die Analyse von Exit Target zu ermöglichen, insbesondere dann, wenn die Drittanbieter-Website für die Zahlung von Verweisgebühren zuständig ist, wenn solche Verweise empfangen werden. Da das Klickereignis standardmäßig in die Protokolldateien des Drittanbietersystems geschrieben wird, müssen Änderungen am Link vorgenommen werden, damit das Klickereignis lokal erfasst werden kann. Der in Ihrer Website vorhandene Drittanbieter-Link muss wie folgt geändert werden:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Die referenzierte Datei [!DNL PageExit.htm] muss erstellt und so strukturiert sein, dass sie folgendes Skript enthält:

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

Durch die Anforderung für die Datei [!DNL PageExit.htm] wird der Wert v_eurl zu Analysezwecken erfasst. Wenn [!DNL PageExit.htm] geladen wird, wird sofort der angegebene v_eurl-Zielort umgeleitet.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_eurl | Wert, der mit der Abfragezeichenfolgenvariablen v_eurl verknüpft ist. Dieser Wert stellt die Ziel-URL des Links dar, der auf der HTML-Seite vorhanden ist. | v_eurl=www.othersite.com |
