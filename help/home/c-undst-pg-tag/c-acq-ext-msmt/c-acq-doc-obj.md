---
description: Mithilfe des JavaScript-Dokumentobjektmodells können zusätzliche Skriptmethoden zum Erweitern der Anforderung für die Datei "zig.js"verwendet werden.
solution: Analytics
title: Abrufen von Dokumentobjekten
topic: Data workbench
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abrufen von Dokumentobjekten{#acquiring-document-objects}

Mithilfe des JavaScript-Dokumentobjektmodells können zusätzliche Skriptmethoden zum Erweitern der Anforderung für die Datei &quot;zig.js&quot;verwendet werden.

Informationen wie der Wert von META-Tags, ID-Werte von DIV-Tags usw. können anhand des Namens referenziert und als Variablen zur Verwendung in der Analyse erfasst werden. Um beispielsweise die im META-Element des HTML-Dokuments enthaltenen Informationen dynamisch zu erfassen, können Sie die folgende JavaScript-Syntax verwenden:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1= | Der mit der Abfragezeichenfolgen-Variablen METAVALUE verknüpfter Wert. Dieser Wert stellt die Daten im META-Element des HTML-Dokuments dar. | v_1=Diese Seite enthält Inhalte, die mit der Dankeseite für die Bestellung zusammenhängen. |

Nachdem die Daten erfasst wurden, können Sie den Data Workbench-Server so konfigurieren, dass diese Messungsdaten für die Analyse und Berichterstellung verarbeitet werden.
