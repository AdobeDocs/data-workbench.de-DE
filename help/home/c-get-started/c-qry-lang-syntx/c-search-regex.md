---
description: Data Workbench verwendet reguläre Ausdrücke (Regex) für Such- und Sortiervorgänge.
title: Reguläre Ausdrücke
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Reguläre Ausdrücke{#regular-expressions}

Data Workbench verwendet reguläre Ausdrücke (Regex) für Such- und Sortiervorgänge.

Im Feld **[!UICONTROL Search]** können Sie eine Suche nach der Anweisung &quot;re:&quot; durchführen, indem Sie gebräuchliche Ausdrücke verwenden, z. B.:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metacharacter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>  (Punkt) </p> </td> 
   <td colname="col2"> <p>Entspricht einem einzelnen Zeichen, z. B.: <span class="filepath"> re:x.z </span> entspricht "xyz" oder "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (Stern) </p> </td> 
   <td colname="col2"> <p>Entspricht einem oder mehreren Zeichen, z. B.: <span class="filepath"> re:Z* </span> entspricht "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (Platzhalter) </p> </td> 
   <td colname="col2"> <p>Stimmt mit 0 oder 1 des vorherigen Ausdrucks überein, um eine minimale Übereinstimmung zu erzwingen, z. B.: <span class="filepath"> xy?z </span> entspricht "xy" und "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

Zusätzliche häufige reguläre Ausdrücke können auch verwendet werden, um komplexere Suchzeichenfolgen zu erstellen. Reguläre Ausdrücke werden in allen Suchfeldern der Data Workbench verwendet, einschließlich der Bedienfelder der Abfrageentitäten.

Detaillierte Informationen finden Sie unter [Reguläre Ausdrücke](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
