---
description: Erfassen von Aktivitäten über Links zu Websites von Drittanbietern, um die Ausstiegsziel-Analyse zu aktivieren.
solution: Analytics
title: Verfolgen von Ausstiegen zu externen Links
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verfolgen von Ausstiegen zu externen Links{#tracking-exits-to-external-links}

Erfassen von Aktivitäten über Links zu Websites von Drittanbietern, um die Ausstiegsziel-Analyse zu aktivieren.

Webseiten können Links zu Websites von Drittanbietern enthalten. Aktivitäten über diese Links hinweg können erfasst werden, um die Ausstiegsziel-Analyse zu aktivieren, insbesondere dann, wenn die Drittanbietersite für die Zahlung von Verweisgebühren beim Eingang solcher Verweise verantwortlich ist. Da das click-Ereignis standardmäßig in die Protokolldateien des Drittanbietersystems geschrieben wird, müssen Änderungen am Link vorgenommen werden, damit das click-Ereignis lokal erfasst werden kann. Der Link eines Drittanbieters auf Ihrer Website muss wie folgt geändert werden:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Die referenzierte [!DNL PageExit.htm] Datei muss erstellt und so strukturiert sein, dass sie das folgende Skript enthält:

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

Durch die Anforderung der [!DNL PageExit.htm] Datei wird der Wert v_eurl für Analysezwecke erfasst. Außerdem [!DNL PageExit.htm] wird beim Laden sofort an den angegebenen v_eurl-Zielort weitergeleitet.

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_eurl | Der mit der Abfragezeichenfolgen-Variablen v_eurl verknüpfte Wert. Dieser Wert stellt die Ziel-URL des Links dar, der auf der HTML-Seite vorhanden ist. | v_eurl=www.othersite.com |

