---
description: Bewerten Sie einen Entscheidungsbaum mit der Option Regressionsbaum mit neuen Sampling- und Visualisierungsfunktionen.
title: Regressionsbaum-Option für Entscheidungsbäume
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
exl-id: e5f8d525-1530-4169-b246-cdaf30e984c0
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 3%

---

# Regressionsbaum-Option für Entscheidungsbäume{#regression-tree-option-for-decision-tree}

Bewerten Sie einen Entscheidungsbaum mit der Option Regressionsbaum mit neuen Sampling- und Visualisierungsfunktionen.

Evaluieren Sie einen Entscheidungsbaum mithilfe der Option Regressionsbaum , indem Sie mit der rechten Maustaste klicken und in einer Visualisierung des Entscheidungsbaums Optionen > **Regressionsbaum** auswählen.

**Decision Tree Builder** aktualisiert: Der neue Algorithmus wurde zum Erstellen eines  [Entscheidungsbaums](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html) eingeführt. Es verarbeitet allgemeinere Daten und bietet eine informativere Visualisierung, um die Präzision der Vorhersage zu verbessern.

**Verbessertes Datenstichprobenmodul**: Ein aktualisiertes adaptives Sampling-Schema hilft Entscheidungsstruktur und Propensity Score, höhere Präzisionsergebnisse zu erzielen.

![](assets/CART-RegressionTreeOptions.jpg)

Grün und Rot geben &quot;true&quot;oder &quot;false&quot;an. Die Sättigung der Farbe - z. B. tiefrot oder hellrot - wird verwendet, um die Wahrscheinlichkeit anzugeben. Beispielsweise hat ein Knoten mit tiefrotem Rot eine sehr hohe Wahrscheinlichkeit, falsch zu sein, während ein Knoten mit hellrot eine geringere Wahrscheinlichkeit hat, falsch zu sein. Ein Knoten mit tiefgrünem Grün hat eine sehr hohe Wahrscheinlichkeit, wahr zu sein.

Alle Entscheidungsbäume haben unterschiedliche Zweigbreiten, um den Traffic für diesen Zweig des Baums anzuzeigen.

Klicken Sie in einer Entscheidungsbaum-Visualisierung mit der rechten Maustaste und wählen Sie Optionen > **Regressionsstruktur** aus. Wenn diese Option aktiviert ist, werden zusätzliche Einstellungen bereitgestellt:

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regressionseinstellung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Jede Funktion nur einmal verwenden</b> </p> </td> 
   <td colname="col2"> <p>Wenn Sie diese Option auswählen, wird eine Funktion nicht mehr als einmal verwendet (wie der ursprüngliche Entscheidungsbaum). Wenn Sie also fünf Eingaben haben, ist der Baum nicht mehr als fünf Ebenen und die Baumstruktur sieht ähnlich wie ein Entscheidungsbaum aus (allerdings etwas komplizierter). Mit dieser Option wird das Baum-Gebäude schneller, indem jede Funktion nur einmal verwendet wird (wie ein ursprünglicher Entscheidungsbaum). Die Verwendung dieser Funktion ist eine Standardeinstellung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regressionsstufeneinstellung  </b> </p> </td> 
   <td colname="col2"> <p>Diese Option steuert die Komplexität des Regressionsbaums. Abhängig von Ihren Daten müssen Sie möglicherweise einen <i>Fine</i>-Baum (mit einer komplizierten Struktur mit mehr Knoten) erstellen, um eine aussagekräftigere Baumklassifizierung zu erhalten. Wenn Sie über viele Daten verfügen, kann ein relativ <i>grober</i> Baum (weniger kompliziert mit weniger Strukturknoten) gut funktionieren. </p> <p> <p>Hinweis: <i>Typical</i> ist die Standardeinstellung. Es gibt einige Extremfälle, in denen die Einstellung <i>Typical</i> nicht ebenfalls funktioniert und die Einstellung <i>Grob</i> oder <i>Fein</i> eine bessere Ansicht der Daten bieten kann. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Gut</i>: Die komplexeste Baumstruktur mit den detailliertesten Ebenen der Berichterstellung und den meisten Verzweigungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Typisch</i>: Durchschnittliche Granularität und Verzweigungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Groß</i>: Der am wenigsten komplexe Baum mit den am wenigsten definierten Kategorien und den am wenigsten verzweigten Zweigen. </p> </td> 
  </tr> 
 </tbody> 
</table>
