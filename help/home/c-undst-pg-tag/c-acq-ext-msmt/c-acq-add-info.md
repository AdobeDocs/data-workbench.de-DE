---
description: Abfragezeichenfolgenvariablen können zu einer JavaScript-Anforderung hinzugefügt werden, um zusätzliche Messungen bei einer Anforderung zu erfassen.
title: Erfassen zusätzlicher Informationen
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Erfassen zusätzlicher Informationen{#acquiring-additional-information}

Abfragezeichenfolgenvariablen können zu einer JavaScript-Anforderung hinzugefügt werden, um zusätzliche Messungen bei einer Anforderung zu erfassen.

Diese Variablen können manuell oder durch ein Skript auf der Seite selbst hinzugefügt werden.

Zusätzliche Informationen, die von einer Seite erfasst werden können, können dem eingebetteten Objekt über ein Skript hinzugefügt werden. Verwenden Sie dazu als Beispiel den folgenden Code:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

In diesem Beispiel können die Skriptvariablen für v_1 und v_2 von einer anderen Funktion auf Ihrer Webseite abgeleitet werden. Die Variablen wurden als Beispiele eingefügt. Zusätzlich zu den bei jeder Anfrage erfassten Grundlinienmessungen werden die folgenden erweiterten Messungen mit der obigen Anfrage der URL erfasst:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_pn= | Wert, der der Abfragezeichenfolgenvariable v_pn zugeordnet ist | v_pn=Antragsformular |
| v_1= | Wert, der der Abfragezeichenfolgenvariable v_1 zugeordnet ist | v_1=99.99 |
| v_2= | Wert, der der Abfragezeichenfolgenvariablen v_2 zugeordnet ist | v_2=visa |
