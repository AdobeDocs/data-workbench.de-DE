---
description: Erfassung der Aktivität über Links zu Websites von Drittanbietern, um die Analyse der Zielgruppe beenden zu aktivieren.
title: Tracking von Ausstiegen zu externen Links
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Tracking von Ausstiegen zu externen Links{#tracking-exits-to-external-links}

Erfassung der Aktivität über Links zu Websites von Drittanbietern, um die Analyse der Zielgruppe beenden zu aktivieren.

Webseiten können Links zu Websites von Drittanbietern enthalten, und die Aktivität über diese Links kann erfasst werden, um die Analyse der Zielgruppe von Ausstiegen zu ermöglichen, insbesondere dann, wenn die Drittanbietersite für die Zahlung von Verweisgebühren beim Eingang solcher Verweise verantwortlich ist. Da das click-Ereignis standardmäßig in die Protokolldateien des Drittanbietersystems geschrieben wird, müssen Änderungen am Link vorgenommen werden, damit das click-Ereignis lokal erfasst werden kann. Der Link eines Drittanbieters auf Ihrer Website muss wie folgt geändert werden:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Die referenzierte Datei [!DNL PageExit.htm] muss erstellt werden und sollte so strukturiert sein, dass sie das folgende Skript enthält:

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

Durch die Anforderung für die Datei [!DNL PageExit.htm] wird der Wert v_eurl für die Analyse erfasst. Wenn [!DNL PageExit.htm] geladen wird, wird sofort der Speicherort der v_eurl-Zielgruppe umgeleitet.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_eurl | Der mit der Zeichenfolgenvariablen v_eurl verknüpfte Abfrage. Dieser Wert steht für die Zielgruppen-URL des Links auf der HTML-Seite. | v_eurl=www.othersite.com |
