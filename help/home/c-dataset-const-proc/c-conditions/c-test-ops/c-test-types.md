---
description: Für die Bedingungen Vergleichen und Bereich müssen Sie den Vergleichstyp für die Bedingung angeben.
title: Typen von Tests für Testoperationen
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 2%

---

# Typen von Tests für Testoperationen{#test-types-for-test-operations}

{{eol}}

Für die Bedingungen Vergleichen und Bereich müssen Sie den Vergleichstyp für die Bedingung angeben.

In der folgenden Tabelle werden die verfügbaren Typen ( [!DNL LEXICAL], [!DNL NUMERIC]und [!DNL DATETIME]).

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
   <td colname="col2"> <p>Wandelt das Eingabefeld zunächst in eine Ganzzahl um. Ist dies nicht möglich, wird der Wert null verwendet. Der Test gibt nur dann "true"zurück, wenn der resultierende ganzzahlige Eingabewert größer oder gleich dem angegebenen Mindestwert und kleiner oder gleich dem angegebenen Maximalwert ist. </p> </td> 
   <td colname="col3"> <p>Wenn eines der Felder min oder max leer gelassen wird, verwendet das System den entsprechenden Mindest- oder Höchstwert für 64-Bit-signierte Ganzzahlen. </p> <p> Wenn der in der Bedingung angegebene Mindest- oder Höchstwert nicht erfolgreich auf einen ganzzahligen Wert analysiert wird, ersetzt das System null und stoppt die Verarbeitung des Datensatzes nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>Wandelt das Eingabefeld zunächst in ein Datum um. Wenn das Eingabefeld nicht in ein gültiges Datum umgewandelt werden kann, gibt der Bedingungstest "false"zurück. Wenn das Feld in ein Datum umgewandelt werden kann, gibt der Test nur dann "true"zurück, wenn das Eingabedatum auf oder nach dem angegebenen Mindestdatum liegt und am oder vor dem angegebenen Höchstdatum liegt. </p> </td> 
   <td colname="col3"> <p>Wenn die Mindest- und Höchstdaten nicht gültig sind, wird der Datensatz nicht erstellt. </p> <p> Wenn keine Mindest- oder Höchstdaten angegeben werden, ersetzt das System entsprechend entweder das Mindest- (1. Januar 1600) oder das Höchstdatum (irgendwann im 24. Jahrhundert). </p> <p> Adobe empfiehlt die Verwendung eines der folgenden Formate für <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1. Januar 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1. Januar 2013 HH:MM:SS GMT </li> 
    </ul> <p> Wenn nicht anders angegeben, wird in der Zeitzone standardmäßig GMT verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXISCH</span> </p> </td> 
   <td colname="col2"> <p>Gibt "true"nur zurück, wenn das Eingabefeld lexikalisch größer als die als Minimum angegebene Zeichenfolge oder kleiner oder gleich der im Maximalwert angegebenen Zeichenfolge ist. </p> </td> 
   <td colname="col3"> <p>Beim Lexischen Vergleich wird der ASCII-Wert der Zeichen in den Zeichenfolgen verwendet, die von links nach rechts verschoben werden, um die Zeichen zu vergleichen. Für das erste Zeichen, das nicht übereinstimmt, wird das mit dem größeren ASCII-Wert als das größere von beiden betrachtet. Falls eine Zeichenfolge kürzer als die andere ist, bis zu diesem Punkt jedoch alle Zeichen gleich waren, wird die längere Zeichenfolge als die größere der beiden betrachtet. Wenn die Zeichenfolgen Zeichen für Zeichenäquivalent und exakt dieselbe Länge sind, werden sie als lexikalisch äquivalent betrachtet. </p> </td> 
  </tr> 
 </tbody> 
</table>
