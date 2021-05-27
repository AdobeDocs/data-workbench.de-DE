---
description: Bei der Umwandlung "Zusammenführen"werden die Werte aus dem Eingabefeld (normalerweise ein Zeichenfolgenvektor) übernommen, zu einer durch das angegebene Trennzeichen getrennten Zeichenfolge kombiniert und die resultierende Zeichenfolge in das angegebene Ausgabefeld eingefügt.
title: Merge
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 4%

---

# Zusammenführen{#merge}

Bei der Umwandlung &quot;Zusammenführen&quot;werden die Werte aus dem Eingabefeld (normalerweise ein Zeichenfolgenvektor) übernommen, zu einer durch das angegebene Trennzeichen getrennten Zeichenfolge kombiniert und die resultierende Zeichenfolge in das angegebene Ausgabefeld eingefügt.

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. </td> 
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
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>Zeichenfolge, die verwendet wird, um die einzelnen Elemente des Eingabe-String-Vektors in der einzelnen Ausgabe-Zeichenfolge zu trennen. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste im Trennzeichen-Parameter klicken, wird das Menü <span class="wintitle"> Einfügen</span> angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Ein Vektor von Zeichenfolgenwerten, die kombiniert werden, um die Ausgabezeichenfolge zu bilden. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name der Ausgabezeichenfolge. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird davon ausgegangen, dass ein Eingabefeld von Zeichenfolgen einen Satz von Produkten enthält, die zum Kauf ausgewählt wurden. Diese Produkte werden in einer einzelnen Ausgabezeichenfolge platziert und durch &quot;::&quot;getrennt (zwei Doppelpunkte).

![](assets/cfg_TransformationType_Merge.png)

Wenn also das Eingabefeld x-products die Zeichenfolgenwerte B57481, C46355 und Z97123 enthielt, wäre die resultierende Ausgabestruktur x-show-products B57481::C46355::Z97123.
