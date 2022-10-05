---
description: Mithilfe des JavaScript Document Object Model können zusätzliche Skriptmethoden verwendet werden, um die Anforderung für die Datei zig.js zu ergänzen.
title: Erfassen von Dokumentenobjekten
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Erfassen von Dokumentenobjekten{#acquiring-document-objects}

{{eol}}

Mithilfe des JavaScript Document Object Model können zusätzliche Skriptmethoden verwendet werden, um die Anforderung für die Datei zig.js zu ergänzen.

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

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1= | Wert, der der Abfragezeichenfolgenvariablen METAVALUE zugeordnet ist. Dieser Wert stellt die Daten im META-Element des HTML-Dokuments dar. | v_1=Diese Seite stellt Inhalte bereit, die sich auf die Dankeseite für die Bestellung beziehen. |

Nachdem die Daten erfasst wurden, können Sie den Data Workbench-Server so konfigurieren, dass diese Messdaten zum Zwecke der Analyse und Berichterstellung verarbeitet werden.
