---
description: Data Workbench verwendet reguläre Ausdrücke (regex) für Such- und Sortiervorgänge.
solution: Analytics
title: Reguläre Ausdrücke
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Regular expressions{#regular-expressions}

Data Workbench verwendet reguläre Ausdrücke (regex) für Such- und Sortiervorgänge.

Innerhalb des **[!UICONTROL Search]** Felds können Sie eine Suche nach der Anweisung &quot;re:&quot;durchführen, indem Sie z. B. allgemeine Ausdrücke verwenden:

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
   <td colname="col1"> <p>. (Punkt) </p> </td> 
   <td colname="col2"> <p>Entspricht einem einzelnen Zeichen, z. B.: " <span class="filepath"> re:x.z" </span> entspricht "xyz"oder "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (Stern) </p> </td> 
   <td colname="col2"> <p>Entspricht einem oder mehreren Zeichen, z. B.: <span class="filepath"> re:Z* </span> findet "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (Platzhalter) </p> </td> 
   <td colname="col2"> <p>Sucht nach 0 oder 1 des vorherigen Ausdrucks, um eine minimale Übereinstimmung zu erzwingen, z. B.: <span class="filepath"> xy?z </span> findet "xy"und "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

Zusätzliche reguläre Ausdrücke können auch verwendet werden, um komplexere Suchzeichenfolgen zu erstellen. Reguläre Ausdrücke werden in allen Data Workbench-Suchfeldern einschließlich der Abfrageentitätsbedienfelder verwendet.

Detaillierte Informationen finden Sie unter [Reguläre Ausdrücke](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
