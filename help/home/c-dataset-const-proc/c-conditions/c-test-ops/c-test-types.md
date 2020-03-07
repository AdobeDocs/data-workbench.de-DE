---
description: Die Bedingung "Vergleichen"und "Bereich"erfordern, dass Sie den Vergleichstyp für die Bedingung angeben.
solution: Analytics
title: Testtypen für Testvorgänge
topic: Data workbench
uuid: dc0433dd-a35e-472e-8975-f58347512c11
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Testtypen für Testvorgänge{#test-types-for-test-operations}

Die Bedingung &quot;Vergleichen&quot;und &quot;Bereich&quot;erfordern, dass Sie den Vergleichstyp für die Bedingung angeben.

Die folgende Tabelle beschreibt die verfügbaren Typen ( [!DNL LEXICAL], [!DNL NUMERIC]und [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Testtyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Hinweise </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span> </p> </td> 
   <td colname="col2"> <p>Zunächst wird das Eingabefeld in eine Ganzzahl umgewandelt. Ist dies nicht möglich, wird der Wert Null verwendet. Der Test gibt "true"nur dann zurück, wenn der resultierende ganzzahlige Eingabewert größer oder gleich dem angegebenen Mindestwert und kleiner oder gleich dem angegebenen Maximalwert ist. </p> </td> 
   <td colname="col3"> <p>Wenn eines der Felder "min"oder "max"leer gelassen wird, verwendet das System den entsprechenden Min- oder Höchstwert, der für 64-Bit-signierte Ganzzahlen verfügbar ist. </p> <p> Wenn der in der Bedingung angegebene Min- oder Höchstwert nicht erfolgreich mit einem Ganzzahlwert analysiert wird, ersetzt das System null und stoppt nicht die Verarbeitung des Datensatzes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> TAGESZEIT</span> </p> </td> 
   <td colname="col2"> <p>Zunächst wird das Eingabefeld zu einem Datum. Wenn das Eingabefeld nicht in ein gültiges Datum umgewandelt werden kann, gibt der Bedingungstest "false"zurück. Wenn das Feld in ein Datum umgewandelt werden kann, gibt der Test nur dann "true"zurück, wenn das Eingabedatum auf oder nach dem angegebenen Mindestdatum und am oder vor dem angegebenen Höchstdatum fällt. </p> </td> 
   <td colname="col3"> <p>Wenn die Mindest- und Höchstdaten nicht gültig sind, wird der Datensatz nicht erstellt. </p> <p> Wenn keine Mindest- oder Höchstdaten angegeben werden, ersetzt das System entweder das Mindest- (1. Januar 1600) oder das Höchstdatum (irgendwann im 24. Jahrhundert) entsprechend. </p> <p> Adobe empfiehlt die Verwendung eines der folgenden Formate für <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1. Januar 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1. Januar 2013 HH:MM:SS GMT </li> 
    </ul> <p> Wenn keine Angabe gemacht wird, wird in der Zeitzone standardmäßig GMT verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXISCH</span> </p> </td> 
   <td colname="col2"> <p>Gibt "true"nur dann zurück, wenn das Eingabefeld lexikalisch größer oder gleich der als Minimum angegebenen Zeichenfolge und kleiner als oder gleich der im Maximalwert angegebenen Zeichenfolge ist. </p> </td> 
   <td colname="col3"> <p>Beim Lexischen Vergleich wird der ASCII-Wert der Zeichen in den Zeichenfolgen verwendet, die von links nach rechts verschoben werden, und die Zeichen werden verglichen. Für das erste Zeichen, das nicht übereinstimmt, wird das mit dem größeren ASCII-Wert als das größere von beiden betrachtet. Wenn eine Zeichenfolge kürzer als die andere ist, bis zu diesem Zeitpunkt jedoch alle Zeichen gleich waren, gilt die längere Zeichenfolge als der größere der beiden Zeichen. Wenn die Zeichenfolgen Zeichen für Entsprechungen und exakt dieselbe Länge sind, werden sie als wörtlich gleichwertig betrachtet. </p> </td> 
  </tr> 
 </tbody> 
</table>

