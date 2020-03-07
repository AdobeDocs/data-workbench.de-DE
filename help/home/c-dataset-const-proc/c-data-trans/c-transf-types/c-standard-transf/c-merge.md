---
description: Die Merge-Transformation nimmt die Werte aus dem Eingabefeld (normalerweise ein Vektor von Zeichenfolgen), kombiniert sie in eine einzige Zeichenfolge, die durch das angegebene Trennzeichen getrennt ist, und platziert die resultierende Zeichenfolge in das angegebene Ausgabefeld.
solution: Analytics
title: Zusammenführen
topic: Data workbench
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Merge{#merge}

Die Merge-Transformation nimmt die Werte aus dem Eingabefeld (normalerweise ein Vektor von Zeichenfolgen), kombiniert sie in eine einzige Zeichenfolge, die durch das angegebene Trennzeichen getrennt ist, und platziert die resultierende Zeichenfolge in das angegebene Ausgabefeld.

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standardeinstellung </th> 
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
   <td colname="col1"> Standardeinstellung </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>String, der verwendet wird, um die einzelnen Elemente des Eingabestring-Vektors in der einzelnen Ausgabestrategie zu trennen. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste in den Trennzeichner-Parameter klicken, wird ein Menü " <span class="wintitle"> Einfügen</span> "angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Ein Vektor von Zeichenfolgenwerten, die zu einer Ausgabestrategie kombiniert werden. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name der Ausgabezeichenfolge. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird davon ausgegangen, dass ein EingabekVektor von Zeichenfolgen eine Reihe von Produkten enthält, die zum Kauf ausgewählt wurden. Diese Produkte werden in einer einzigen Ausgabestrategie platziert und durch &quot;:&quot;(zwei Doppelpunkte) getrennt.

![](assets/cfg_TransformationType_Merge.png)

Wenn also das Eingabefeld x-products die Zeichenfolgenwerte B57481, C46355 und Z97123 enthielt, wäre die resultierende Ausgabezeichenfolge x-show-products B57481::C46355::Z97123.
