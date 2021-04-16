---
description: Die in ein Formular auf einer Webseite eingegebenen Werte können mithilfe von JavaScript gesammelt und in die Abfrage-Zeichenfolge der anschließend angeforderten Seite (bei Formularübermittlung) angehängt werden.
title: Allgemeine Informationen
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 7%

---

# Allgemeine Informationen{#general-information}

Die in ein Formular auf einer Webseite eingegebenen Werte können mithilfe von JavaScript gesammelt und in die Abfrage-Zeichenfolge der anschließend angeforderten Seite (bei Formularübermittlung) angehängt werden.

Siehe dazu das folgende Beispiel. Schließen Sie dieses JavaScript nach allen in Ihren HTML-Seiten verwendeten Formularüberprüfungsskripten ein.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

In diesem Beispiel werden die vom Browser-Benutzer in das Formular eingegebenen Werte an die folgende Seite &quot;dank.asp&quot;angehängt, die im Wert der FORM-Aktion wie folgt angegeben ist:

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Mit dieser Anforderung werden zusätzlich zu den von [!DNL Sensor] erfassten Basiswerten die folgenden erweiterten Messungen erfasst:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Mit dem Formularfeld NAME verknüpfter Wert | v_1=John Smith |
| v_2 | Mit dem CITY-Formularfeld verknüpfter Wert | v_2=Los Angeles |
| v_3 | Mit dem STATE-Formularfeld verknüpfter Wert | v_3=Kalifornien |
| v_4 | Mit dem ZIP-Formularfeld verknüpfter Wert | v_4=90210 |
