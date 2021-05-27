---
description: Als Teil der erfassten Grundlinien-Messungsdaten erfasst Sensor die Domänencookies, die von einem Besuchercomputer gesendet werden, wenn eine Anforderung von Ihrem Webserver erfolgt.
title: Erfassen von Messdaten anhand von Cookies
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# Erfassen von Messdaten anhand von Cookies{#acquiring-measurement-data-through-cookies}

Als Teil der erfassten Grundlinien-Messungsdaten erfasst Sensor die Domänencookies, die von einem Besuchercomputer gesendet werden, wenn eine Anforderung von Ihrem Webserver erfolgt.

Dazu gehören sowohl persistente als auch Sitzungs-Cookies, die Ihre Website setzt, wenn ein Besucher mit Ihrem System interagiert.

In den meisten Fällen setzen Websites persistente Cookies, um Besucher zu identifizieren oder Benutzereingaben zur Verwendung in nachfolgenden Besuchersitzungen zu erfassen. Alle in persistente Cookies geschriebenen und gespeicherten Informationen können zusammen mit allen anderen Messdaten innerhalb des Data Workbench-Servers erfasst und verwendet werden.

Ein Beispiel für ein solches persistentes Cookie könnte eine Kundenkennung in Form eines numerischen Schlüssels beinhalten, der in einem domänenspezifischen Cookie auf dem Computer des Besuchers vorhanden ist. Zusätzlich zur Identifizierung des Benutzers als wiederkehrender Besucher kann das beständige Cookie auch verwendet werden, um den Besucher weiter als wiederkehrenden Kunden zu identifizieren oder um ihn mit Informationen aus einer Kundendatenbank zu verknüpfen, damit Offline-Kundendemographie-Informationen innerhalb von [!DNL Site] angezeigt und für interaktive Analysen verwendet werden können.

Sitzungs-Cookies können ein guter Mechanismus sein, um Benutzereingaben über Formularfelder oder andere dynamische interaktive Elemente auf Ihrer Website zu erfassen. Im Fall einer Website, auf der Formulare zur Erfassung benutzerspezifischer Eingabedaten implementiert werden, bleiben die Informationen nur so lange im Sitzungs-Cookie, wie die Sitzung aktiv ist. Wenn ein Benutzer Ihre Website verlässt oder anschließend eine Sitzung beendet, werden die Informationen nicht mehr auf dem Computer des Benutzers gespeichert. Die eingegebenen Informationen werden jedoch von [!DNL Sensor] erfasst und als Messdaten innerhalb von [!DNL Site] bereitgestellt.

Im Folgenden finden Sie ein Beispiel für die Verwendung eines Sitzungs-Cookies zum Erfassen einer einzelnen Formularvariable, die von einem Besucher eingegeben wurde.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

In diesem Beispiel wird eine Funktion aufgerufen, um ein Sitzungs-Cookie auf dem Computer des Besuchers mit dem Namen des Felds und dem im Formularfeld eingegebenen Wert festzulegen. Wenn das Formular gesendet und die nachfolgende Webseite angefordert wird, wird das eingestellte Sitzungs-Cookie an den Webserver übergeben und von [!DNL Sensor] erfasst. Die folgenden Daten sind daher im Data Workbench-Server zur Verwendung in der Datenanalyse verfügbar:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Wert, der dem v_1-Cookie zugeordnet ist. Dieser Wert stellt den im Formularfeld eingegebenen Namen dar, der dazu führte, dass das Sitzungs-Cookie gesetzt wurde. | v_1=John Smith |

Sitzungs-Cookies können auch zum iterativen Erfassen von Formularfeldern oder einer Vielzahl eingebetteter JavaScript-Variablen verwendet werden, die auf einer HTML-Seite vorhanden sind. Im folgenden Beispiel wird JavaScript verwendet, um rekursiv jedes in einer HTML-Datei vorhandene Formularfeld zu erfassen und ein Sitzungs-Cookie mit den entsprechenden Name=Wert-Paaren festzulegen.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

In diesem Beispiel wird ein Sitzungs-Cookie auf dem Computer des Besuchers mit dem Namen und Wert jedes Formularfelds gesetzt, das im Formular vorhanden ist. Dazu gehören Eingabefelder, Kontrollkästchen, Optionsfelder, Auswahlfelder und Textbereiche. Da die Anzahl der Formularfelder unbekannt ist, müssen Sie, wie Sie in diesem Beispiel feststellen können, alle Formularnamen- und Feldwerte als einzelne Zeichenfolge erfassen, die durch ein kaufmännisches Und-Zeichen getrennt ist. Dieser Schritt muss aufgrund einer Begrenzung der Anzahl von Cookies durchgeführt werden, die ein Benutzer zu einem bestimmten Zeitpunkt auf seinem Computer haben kann. Microsoft Internet Explorer lässt nur zwanzig (20) Sitzungs-Cookies zu, bevor mit dem Ablegen des ältesten Cookies begonnen wird.
