---
description: Bewerten Sie eine Entscheidungsstruktur mit der Regressionsstruktur-Option mit neuen Sampling- und Visualisierungsfunktionen.
title: Regressionsbaumoption für Entscheidungsstruktur
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Regressionsbaumoption für Entscheidungsstruktur{#regression-tree-option-for-decision-tree}

Bewerten Sie eine Entscheidungsstruktur mit der Regressionsstruktur-Option mit neuen Sampling- und Visualisierungsfunktionen.

Bewerten Sie eine Entscheidungsstruktur mit der Option Regressionsstruktur, indem Sie mit der rechten Maustaste klicken und in einer Visualisierung der Entscheidungsstruktur Optionen > **Regressionsstruktur** auswählen.

**Decision Tree Builder** aktualisiert: Der neue Algorithmus wurde zum Erstellen einer [Entscheidungsstruktur](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html)eingeführt. Es verarbeitet allgemeinere Daten und bietet eine informativere Visualisierung, um die Präzision der Prognose zu verbessern.

**Verbessertes Datenstichprobenmodul**: Ein aktualisiertes adaptives Sampling-Schema hilft Entscheidungs-Tree und Tendenzauswertung, präzisere Ergebnisse zu erzielen.

![](assets/CART-RegressionTreeOptions.jpg)

Grün und Rot geben &quot;true&quot;oder &quot;false&quot;an. Die Sättigung der Farbe - z. B. tiefrot oder hellrot - wird verwendet, um die Wahrscheinlichkeit anzugeben. Ein Knoten mit tiefroter Farbe hat beispielsweise eine sehr hohe Wahrscheinlichkeit, falsch zu sein, während ein Knoten mit hellroter Wahrscheinlichkeit falsch ist. Ein Knoten mit tiefgrünem Grün hat eine sehr hohe Wahrscheinlichkeit wahr zu sein.

Alle Entscheidungsstrukturen haben unterschiedliche Zweigstellen, um den Traffic für diesen Zweig des Baumes anzugeben.

Klicken Sie in einer Entscheidungsstruktur-Visualisierung mit der rechten Maustaste und wählen Sie Optionen > **Regressionsstruktur**. Bei Auswahl dieser Option werden zusätzliche Einstellungen bereitgestellt:

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
   <td colname="col2"> <p>Wenn Sie diese Option wählen, wird eine Funktion nicht mehr als einmal verwendet (wie die ursprüngliche Entscheidungsstruktur). Wenn Sie also fünf Eingaben haben, ist der Baum nicht mehr als fünf Stufen und die Baumstruktur sieht ähnlich wie eine Entscheidungsstruktur aus (allerdings etwas komplizierter). Mit dieser Option wird das Baum schnell aufgebaut, indem jede Funktion nur einmal verwendet wird (wie eine ursprüngliche Entscheidungsstruktur). Die Verwendung dieser Funktion ist eine Standardeinstellung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regressionsstufeneinstellung </b> </p> </td> 
   <td colname="col2"> <p>Diese Option steuert die Komplexität der Regressionsstruktur. Abhängig von Ihren Daten müssen Sie eventuell eine <i>feine</i> Struktur (mit einer komplizierten Struktur mit mehr Knoten) erstellen, um eine aussagekräftigere Baumklassifizierung zu erhalten. Wenn Sie viele Daten haben, könnte ein relativ <i>grober</i> Baum (weniger kompliziert mit weniger Baum-Knoten) gut funktionieren. </p> <p> <p>Hinweis: " <i>Typisch</i> "ist die Standardeinstellung. Es gibt einige Extremfälle, in denen die Einstellung " <i>Typisch</i> "nicht so gut funktioniert und die Einstellung " <i>Groß</i> "oder " <i>Fein</i> "eine bessere Ansicht der Daten bieten kann. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Geldbuße</i>: Die komplexeste Struktur mit den granulärsten Berichtsebenen und den meisten Zweigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Typisch</i>: Die durchschnittliche Granularitätsstufe und Verzweigungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Grob</i>: Die am wenigsten komplexe Struktur mit den am wenigsten definierten Kategorien und den geringsten Zweigen. </p> </td> 
  </tr> 
 </tbody> 
</table>

