---
description: Entscheidungsbäume sind eine prädiktive Analysevisualisierung, die zur Bewertung von Besuchermerkmalen und -beziehungen verwendet wird. Der Entscheidungsbaum-Aufbau erzeugt eine Entscheidungsbaumdarstellung basierend auf einem angegebenen positiven Fall und einer Reihe von Eingaben.
title: Decision Tree Builder
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
exl-id: d93e6a34-be59-4af5-84c3-c13deb98b57b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 23%

---

# Decision Tree Builder{#decision-tree-builder}

{{eol}}

Entscheidungsbäume sind eine prädiktive Analysevisualisierung, die zur Bewertung von Besuchermerkmalen und -beziehungen verwendet wird. Der Entscheidungsbaum-Aufbau erzeugt eine Entscheidungsbaumdarstellung basierend auf einem angegebenen positiven Fall und einer Reihe von Eingaben.

Ein Entscheidungsbaum ist ein binärer Klassifizierer mit einem Satz von Regeln (oder Filtern), der Benutzer erkennt, die basierend auf einem positiven Fall bestimmte Regeln erfüllen. Ein Entscheidungsbaum legt Regeln zur Classification von Besuchern fest, die diesem positiven Fall entsprechen (oder nicht). Diese Regeln erzeugen eine Tree Map, die ein Konfidenzniveau bietet, das diesen positiven Fallergebnissen entspricht.

Ein Entscheidungsbaum wird erstellt, indem die Eingaben auf jeder Ebene geprüft und die Ebene ausgewählt wird, die einen maximalen Informationsgewinn an einem bestimmten Aufspaltungspunkt ermöglicht. Aufspaltungspunkte für jede Variablenebene erzeugen zwei Sätze:

* Werte kleiner oder gleich dem Aufteilungspunkt und
* Werte, die größer als der Trennpunkt sind.

Verwenden Sie Entscheidungsbäume, um

* Führen Sie in kürzerer Zeit eine aussagekräftige Analyse und Interpretation durch.
* Verwenden Sie die automatisierte Segmenterstellung.
* Sie können schnell Rückschlüsse aus einem Modell ziehen, das auf einer großen Datenmenge basiert.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Symbolleiste und Menüs</b> </p> <p>Die Symbolleiste enthält Schaltflächen und Menübefehle für den Entscheidungsbaum, einschließlich Funktionen zum Festlegen der Groß-/Kleinschreibung und Hinzufügen von Eingabeauflistungen. </p> <p>Wie bei anderen Visualisierungen wird die <span class="uicontrol"> Element</span> können Sie Dimension und Elemente per Drag &amp; Drop verschieben. Sie können jedoch auch direkt aus dem Bereich Finder ziehen. </p> <p>Weitere Informationen finden Sie unter <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Entscheidungsbaum-Optionen</a>. </p> </td> 
   <td colname="col2"> <p><b>Input Listing</b> </p> <p>In diesem Bereich werden die Eingaben in das Baummodell angezeigt. Sie sind farbcodiert, um Knoten im Anzeigebereich "Baum"abzugleichen. </p> <p>Wenn Sie mit der rechten Maustaste auf eine Eingabe klicken, können Sie die Eingabe aus dem Modell entfernen und zurücksetzen. </p> <p>Wenn Sie den Mauszeiger über einen Strukturknoten bewegen, werden die Aufspaltungsbedingungen entlang des Zweigs zu diesem Knoten und die Prognose an diesem Knoten mit dem Vertrauenswert angezeigt. </p> </td> 
   <td colname="col3"> <p><b>Baumanzeige</b> </p> <p>In diesem Bereich wird das Baummodell mit Blattknoten angezeigt, die basierend auf ihrer Prognose farbcodiert sind: grün für eine True-Prognose für den positiven Fall und rot für eine False-Prognose. </p> <p>Die Aufspaltungsknoten sind farbkodiert für die Eingaben, die ihren Auswahlbedingungen entsprechen. Wenn Sie den Mauszeiger über einen Knoten bewegen, werden Informationen über die Aufspaltung angezeigt und die Eingabeauflistung erweitert, um die Aufspaltungspunkte entlang des Zweigs und die Verteilung des Trainings-Sets anzuzeigen. </p> <p>Knoten unterhalb eines Schwellenwerts werden nicht standardmäßig angezeigt. Klicken Sie auf einen erweiterbaren Knoten (durch ein "+"-Symbol gekennzeichnet), um eine Verzweigung zu untersuchen. Klicken Sie auf den Stammknoten, um zur vollständigen Baumanzeige zurückzukehren. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->
