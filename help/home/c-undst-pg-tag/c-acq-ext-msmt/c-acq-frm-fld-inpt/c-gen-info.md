---
description: Werte, die in ein Formular auf einer Webseite eingegeben werden, können mithilfe von JavaScript erfasst und in die Abfragezeichenfolge der anschließend angeforderten Seite (bei Formularübermittlung) angehängt werden.
title: Allgemeine Informationen
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 7%

---

# Allgemeine Informationen{#general-information}

{{eol}}

Werte, die in ein Formular auf einer Webseite eingegeben werden, können mithilfe von JavaScript erfasst und in die Abfragezeichenfolge der anschließend angeforderten Seite (bei Formularübermittlung) angehängt werden.

Siehe dazu das folgende Beispiel. Schließen Sie dieses JavaScript nach allen Skripten zur Formularüberprüfung ein, die auf Ihren HTML-Seiten verwendet werden.

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

In diesem Beispiel werden die vom Browser-Benutzer in das Formular eingegebenen Werte an die nachfolgende Seite &quot;thankyou.asp&quot;angehängt, die im Wert der FORM-Aktion wie folgt angegeben ist:

```
https://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Zusätzlich zu den von [!DNL Sensor]:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Wert, der dem Feld &quot;NAME&quot;zugeordnet ist | v_1=John Smith |
| v_2 | Mit dem Formularfeld STADT verknüpfter Wert | v_2=Los Angeles |
| v_3 | Wert, der dem Feld STATE form zugeordnet ist | v_3=California |
| v_4 | Wert, der dem ZIP-Formularfeld zugeordnet ist | v_4=90210 |
