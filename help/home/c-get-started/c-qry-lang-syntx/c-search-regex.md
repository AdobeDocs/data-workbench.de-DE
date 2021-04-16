---
description: Data Workbench verwendet reguläre Ausdruck (regex) für Such- und Sortiervorgänge.
title: Reguläre Ausdrücke
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Reguläre Ausdrücke{#regular-expressions}

Data Workbench verwendet reguläre Ausdruck (regex) für Such- und Sortiervorgänge.

Im Feld **[!UICONTROL Search]** können Sie eine Suche nach der Anweisung &quot;re:&quot;durchführen, indem Sie z. B. gängige Ausdruck verwenden:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metazeichen </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>  (Punkt) </p> </td> 
   <td colname="col2"> <p>Entspricht einem einzelnen Zeichen, z. B.: <span class="filepath"> re:x.z </span> entspricht "xyz"oder "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (Stern) </p> </td> 
   <td colname="col2"> <p>Entspricht einem oder mehreren Zeichen, z. B.: <span class="filepath"> re:Z* </span> stimmt mit "ZZZ"überein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (Platzhalter) </p> </td> 
   <td colname="col2"> <p>Sucht nach 0 oder 1 des vorherigen Ausdrucks, um eine minimale Übereinstimmung zu erzwingen. Beispiel: <span class="filepath"> xy?z </span> stimmt mit "xy"und "xyz"überein. </p> </td> 
  </tr> 
 </tbody> 
</table>

Zusätzliche reguläre Ausdruck können auch verwendet werden, um komplexere Suchzeichenfolgen zu erstellen. Reguläre Ausdruck werden in allen Suchfeldern der Data Workbench verwendet, einschließlich der Bereiche für die Abfrage.

Detaillierte Informationen finden Sie unter [Reguläre Ausdruck](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
