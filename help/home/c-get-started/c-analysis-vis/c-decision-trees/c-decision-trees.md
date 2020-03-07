---
description: Entscheidungsbäume sind eine Visualisierung der prädiktiven Analyse, die zur Bewertung von Besuchermerkmalen und -beziehungen verwendet wird. Der Entscheidungsbaum-Aufbau erzeugt eine Entscheidungsbaumdarstellung basierend auf einem angegebenen positiven Fall und einer Reihe von Eingaben.
solution: Analytics
title: Entscheidungsbaum Builder
topic: Data workbench
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Entscheidungsbaum-Builder{#decision-tree-builder}

Entscheidungsbäume sind eine Visualisierung der prädiktiven Analyse, die zur Bewertung von Besuchermerkmalen und -beziehungen verwendet wird. Der Entscheidungsbaum-Aufbau erzeugt eine Entscheidungsbaumdarstellung basierend auf einem angegebenen positiven Fall und einer Reihe von Eingaben.

Ein Entscheidungsbaum ist ein binärer Klassifizierer mit einem Satz von Regeln (oder Filtern), der Benutzer erkennt, die basierend auf einem positiven Fall bestimmte Regeln erfüllen. Ein Entscheidungsbaum legt Regeln zur Classification von Besuchern fest, die diesem positiven Fall entsprechen (oder nicht). Diese Regeln erzeugen eine Tree Map, die ein Konfidenzniveau bietet, das diesen positiven Fallergebnissen entspricht.

Eine Entscheidungsstruktur wird erstellt, indem die Eingaben auf jeder Ebene geprüft und die Ebene gewählt wird, die eine maximale Informationsmenge an einem bestimmten Aufteilungspunkt bietet. Die geteilten Punkte für jede Variablenebene erzeugen zwei Sätze:

* Werte kleiner als oder gleich dem Teilungspunkt und
* Werte größer als der Spaltpunkt.

Verwenden Sie Entscheidungsbäume, um

* Führen Sie aussagekräftige Analysen und Interpretationen in kürzerer Zeit durch.
* Einsatz der automatisierten Segmentgenerierung.
* Erstellen Sie schnell Rückschlüsse aus einem Modell, das auf einer großen Datenmenge basiert.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Symbolleiste und Menüs</b> </p> <p>Die Symbolleiste enthält Schaltflächen und Menübefehle für die Entscheidungsstruktur, einschließlich Funktionen zum Festlegen der Groß-/Kleinschreibung und zum Hinzufügen von Eingabeauflistungen. </p> <p>Wie bei anderen Visualisierungen können Sie auch im Feld " <span class="uicontrol"> Element</span> "Dimension und Elemente per Drag &amp; Drop verschieben. Sie können jedoch auch direkt aus dem Bereich "Finder"ziehen. </p> <p>Weitere Informationen finden Sie unter <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Optionen</a>der Entscheidungsstruktur. </p> </td> 
   <td colname="col2"> <p><b>Eingabe-Auflistung</b> </p> <p>In diesem Bereich werden die Eingaben in das Baummodell angezeigt. Sie sind farbkodiert, um Nodes im Baumanzeigebereich zuzuordnen. </p> <p>Wenn Sie mit der rechten Maustaste auf eine Eingabe klicken, können Sie die Eingabe aus dem Modell entfernen und zurücksetzen. </p> <p>Wenn Sie den Mauszeiger über einen Strukturknoten bewegen, werden die Teilungsbedingungen entlang der Verzweigung zu diesem Knoten und die Vorhersage an diesem Knoten mit dem Vertrauenswert angezeigt. </p> </td> 
   <td colname="col3"> <p><b>Baumanzeige</b> </p> <p>In diesem Bereich wird das Baummodell mit Blattknoten basierend auf der Vorhersage farbkodiert angezeigt: grün für eine echte Prognose des positiven Falls und rot für eine falsche Prognose. </p> <p>Die geteilten Nodes sind farbkodiert für die Eingaben, die ihrer Auswahlbedingung entsprechen. Wenn Sie den Mauszeiger über einen Knoten halten, werden Informationen zur Teilung angezeigt und die Liste der Eingaben erweitert, um die geteilten Punkte entlang der Verzweigung und die Verteilung des Schulungssatzes anzuzeigen. </p> <p>Knoten unter einem Schwellenwert werden standardmäßig nicht angezeigt. Klicken Sie auf einen erweiterbaren Knoten (durch ein +-Symbol gekennzeichnet), um eine Verzweigung zu erkunden. Klicken Sie auf die Stamm-Node, um zur vollständigen Baumanzeige zurückzukehren. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->

