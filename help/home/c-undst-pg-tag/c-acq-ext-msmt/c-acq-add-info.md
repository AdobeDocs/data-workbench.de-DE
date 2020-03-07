---
description: Abfragezeichenfolgen-Variablen können einer JavaScript-Anforderung hinzugefügt werden, um bei einer Anforderung zusätzliche Messungen zu erfassen.
solution: Analytics
title: Zusätzliche Informationen abrufen
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zusätzliche Informationen abrufen{#acquiring-additional-information}

Abfragezeichenfolgen-Variablen können einer JavaScript-Anforderung hinzugefügt werden, um bei einer Anforderung zusätzliche Messungen zu erfassen.

Diese Variablen können manuell oder durch Skript auf der Seite selbst hinzugefügt werden.

Zusätzliche Informationen, die von einer Seite erfasst werden können, können dem eingebetteten Objekt mithilfe eines Skripts hinzugefügt werden, wobei der folgende Code als Beispiel verwendet wird:

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

In diesem Beispiel können die Skriptvariablen für v_1 und v_2 von einer anderen Funktion auf Ihrer Webseite abgeleitet werden. Die Variablen wurden als Beispiele eingefügt. Zusätzlich zu den bei jeder Anforderung gewonnenen Basiswerten werden die folgenden erweiterten Messungen mit der oben genannten URL-Anforderung erfasst:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_pn= | Mit der Abfragezeichenfolgen-Variable v_pn verknüpfter Wert | v_pn=Antragsformular |
| v_1= | Mit der Abfragezeichenfolgen-Variable v_1 verknüpfter Wert | v_1=99.99 |
| v_2= | Mit der Abfragezeichenfolgen-Variable v_2 verknüpfter Wert | v_2=visa |

