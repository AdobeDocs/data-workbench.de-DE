---
description: Die Mathematik-Transformation ermöglicht die Verwendung von arithmetischen Operationen in Feldern in den Protokolleinträgen.
title: Math
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
exl-id: d8b9cacd-67d1-447c-94dd-7028aa371dfa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 7%

---

# Math{#math}

Die Mathematik-Transformation ermöglicht die Verwendung von arithmetischen Operationen in Feldern in den Protokolleinträgen.

Die Vorgänge können Dezimalzahlen und Fließkommakonstanten enthalten.

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausdruck </td> 
   <td colname="col2"> <p>Ein arithmetischer Ausdruck, der die Berechnung beschreibt. </p> <p> Sie können die unten aufgeführten Vorgänge und Funktionen verwenden und Feldnamen in den Ausdruck integrieren: </p> <p> Betrieb 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> Addition (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> Subtraktion (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> Multiplikation (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> Division (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> Rest (%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> Potenzierung (^) </li>
     </ul></p> <p>Funktionen 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x). Gibt 1 zurück, wenn x positiv ist, 0, wenn x null ist, oder -1, wenn x negativ ist. </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x). Gibt den absoluten Wert von x zurück. </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> floor(x). Gibt die größte Ganzzahl von kleiner oder gleich x zurück. </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x). Gibt die nächste Ganzzahl zu x zurück. </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x). Gibt den Logarithmus von x Basis b zurück. </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x,y,...) Gibt die kleinste aller Argumente zurück. </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...) Gibt das größte aller Argumente zurück. </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Felds, das das Ergebnis des arithmetischen Vorgangs enthält. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel, das Datenfelder verwendet, die aus dem Website-Traffic erfasst wurden, wird ein neues Feld namens x-page-duration berechnet, indem x-last-pv-timestamp von x-timestamp subtrahiert und dann 1 hinzugefügt wird. Die Ausgabe wird nur berechnet, wenn das benutzerdefinierte Feld x-last-pv-timestamp (das den Zeitstempel der letzten Ansicht eines Besuchers darstellt) ausgefüllt oder &quot;nicht leer&quot;ist.

![](assets/cfg_TransformationType_Math.png)

Weitere Informationen zur Bedingung [!DNL Not Empty] finden Sie unter [Bedingungen](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
