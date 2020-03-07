---
description: Als Teil der erfassten Basismessdaten sammelt Sensor die Domänencookies, die von einem Besuchercomputer gesendet werden, wenn eine Anforderung von Ihrem Webserver gesendet wird.
solution: Analytics
title: Erfassen von Messungsdaten über Cookies
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erfassen von Messungsdaten über Cookies{#acquiring-measurement-data-through-cookies}

Als Teil der erfassten Basismessdaten sammelt Sensor die Domänencookies, die von einem Besuchercomputer gesendet werden, wenn eine Anforderung von Ihrem Webserver gesendet wird.

Dazu gehören sowohl beständige als auch Sitzungs-Cookies, die Ihre Website einrichtet, wenn ein Besucher mit Ihrem System interagiert.

In den meisten Fällen setzen Websites beständige Cookies, um Besucher zu identifizieren oder Benutzereingaben zur Verwendung in nachfolgenden Besuchersitzungen zu erfassen. Alle in beständigen Cookies geschriebenen und gespeicherten Informationen können zusammen mit allen anderen Messungsdaten innerhalb des Data Workbench-Servers erfasst und verwendet werden.

Ein Beispiel für ein solches beständiges Cookie könnte eine Kundenkennung in Form eines numerischen Schlüssels beinhalten, der in einem domänenspezifischen Cookie auf dem Computer des Besuchers vorhanden ist. Neben der Identifizierung des Benutzers als wiederkehrender Besucher könnte das beständige Cookie auch dazu verwendet werden, den Besucher als wiederkehrenden Kunden weiter zu identifizieren oder den Besucher mit Informationen in einer Kundendatenbank zu verknüpfen, damit demografische Offline-Daten von Kunden innerhalb einer Datenbank angezeigt [!DNL Site] und für interaktive Analysen verwendet werden können.

Sitzungs-Cookies können ein guter Mechanismus sein, um Benutzereingaben über Formularfelder oder andere dynamische interaktive Elemente auf Ihrer Website zu erfassen. Bei einer Website, die Formulare zur Erfassung benutzerspezifischer Eingabedaten implementiert, bleiben die Informationen nur so lange im Sitzungs-Cookie, wie die Sitzung aktiv ist. Wenn ein Benutzer Ihre Website verlässt oder anschließend eine Sitzung beendet, werden die Informationen nicht mehr auf dem Computer des Benutzers gespeichert. Die eingegebenen Informationen werden jedoch von erfasst [!DNL Sensor] und als Messdaten innerhalb von [!DNL Site]bereitgestellt.

Im Folgenden finden Sie ein Beispiel für die Verwendung eines Sitzungs-Cookies zur Erfassung einer einzelnen Formularvariable, die von einem Besucher eingegeben wurde.

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

In diesem Beispiel wird eine Funktion aufgerufen, um ein Sitzungs-Cookie auf dem Computer des Besuchers mit dem Namen des Felds und dem in das Formularfeld eingegebenen Wert festzulegen. Während das Formular gesendet und die nachfolgende Webseite angefordert wird, wird der Sitzungs-Cookie-Satz an den Webserver übergeben und von [!DNL Sensor]diesem erfasst. Die folgenden Daten stehen daher im Data Workbench-Server zur Verwendung in der Datenanalyse zur Verfügung:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Mit dem Cookie v_1 verknüpfter Wert. Dieser Wert steht für den in das Formularfeld eingegebenen Namen, der dazu führte, dass das Sitzungs-Cookie gesetzt wurde. | v_1=John Smith |

Sitzungs-Cookies können auch dazu verwendet werden, Formularfelder oder eine Vielzahl eingebetteter JavaScript-Variablen, die auf einer HTML-Seite vorhanden sind, iterativ zu erfassen. Im folgenden Beispiel wird JavaScript verwendet, um rekursiv alle Formularfelder in einer HTML-Datei zu erfassen und ein Sitzungs-Cookie mit den entsprechenden Paaren name=Wert festzulegen.

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

In diesem Beispiel wird auf dem Computer des Besuchers ein Sitzungs-Cookie mit dem Namen und dem Wert jedes Formularfelds gesetzt, das im Formular vorhanden ist. Dazu gehören Eingabefelder, Kontrollkästchen, Optionsfelder, Auswahlfelder und Textbereiche. Da die Anzahl der Formularfelder unbekannt ist, müssen Sie, wie Sie in diesem Beispiel bemerken können, alle Formularnamen- und Feldwerte als eine einzige Zeichenfolge erfassen, die durch ein kaufmännisches Und getrennt ist. Dieser Schritt muss aufgrund einer Beschränkung der Anzahl von Cookies, die ein Benutzer zu einem bestimmten Zeitpunkt auf seinem Computer hat, durchgeführt werden. Microsoft Internet Explorer lässt nur zwanzig (20) Sitzungs-Cookies zu, bevor der älteste Cookie abgelegt wird.
