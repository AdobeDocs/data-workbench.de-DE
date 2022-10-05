---
description: Das Menü Entscheidungsstruktur enthält Funktionen zum Festlegen des positiven Anwendungsfalls, von Filtern, Blattverteilungsoptionen, Verwirrungsmatrix und anderen erweiterten Optionen.
title: Optionen für Entscheidungsbäume
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---

# Optionen für Entscheidungsbäume{#decision-tree-options}

{{eol}}

Das Menü Entscheidungsstruktur enthält Funktionen zum Festlegen des positiven Anwendungsfalls, von Filtern, Blattverteilungsoptionen, Verwirrungsmatrix und anderen erweiterten Optionen.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schaltflächen der Symbolleiste </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Los </td> 
   <td colname="col2"> Klicken Sie auf , um den Entscheidungsbaum-Algorithmus auszuführen und die Visualisierung anzuzeigen. Dies ist ausgegraut, bis Eingaben vorhanden sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zurücksetzen </td> 
   <td colname="col2"> Löscht Eingaben und Entscheidungsbaummodelle und setzt den Prozess zurück. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Speichern </td> 
   <td colname="col2"><b>Entscheidungsbaum speichern</b>. Sie können die Entscheidungsstruktur in verschiedenen Formaten speichern: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Prädiktive Markup-Sprache (<b>PMML</b>), ein XML-basiertes Dateiformat, das von Anwendungen zur Beschreibung und zum Austausch von Entscheidungsbaummodellen verwendet wird. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Text</b> einfache Spalten und Zeilen mit dem Wert "true"oder "false", Prozentwerte, Anzahl der Mitglieder und Eingabewerte anzeigen. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> mit Zweigen, die den prognostizierten Ergebniselementen entsprechen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Optionen </td> 
   <td colname="col2"> Siehe Tabelle unten für das Menü Optionen . </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Optionen, Menü </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Positiven Fall festlegen </td> 
   <td colname="col2"> Definiert die aktuelle Workspace-Auswahl als positiven Fall des Modells. Löscht die Groß-/Kleinschreibung, wenn keine Auswahl vorhanden ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Populationsfilter festlegen </td> 
   <td colname="col2"> Definiert die aktuelle Workspace-Auswahl als Populationsfilter des Modells und wird von Besuchern gezogen, die diese Bedingung erfüllen. Die Standardeinstellung ist "Alle". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Beschreibung komplexer Filter anzeigen </td> 
   <td colname="col2"> Zeigt Beschreibungen der definierten Filter an. Klicken Sie auf , um die Filterskripten für den Filter Positive Groß-/Kleinschreibung und Population anzuzeigen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Knoten ausblenden </td> 
   <td colname="col2"> Blendet Knoten mit nur einem geringen Prozentsatz der Population aus. Dieser Menübefehl wird nur angezeigt, wenn der Entscheidungsbaum angezeigt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verwirrungsmatrix </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Optionen</span> &gt; <span class="uicontrol"> Verwirrungsmatrix</span> um die Werte für Genauigkeit, Recall, Genauigkeit und F-Score anzuzeigen. Je näher 100 Prozent sind, desto besser ist das Ergebnis. </p> <p>Die Konfusionsmatrix gibt vier Genauigkeitszähler des Modells anhand einer Kombination von Werten an: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Tatsächliche positive Werte (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Prognostiziertes positives (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Tatsächliche Negative (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Prognostizierte Negative (PN) </li> 
     </ul> </p> <p>Tipp: Diese Zahlen erhalten Sie durch Anwendung des resultierenden Scoring-Modells der 20 Prozent zurückbehaltenen Testdaten, die bereits als wahre Antwort bezeichnet werden. Wenn der Wert größer als 50 Prozent ist, wird er als positiver Fall prognostiziert (der mit dem definierten Filter übereinstimmt). Dann, Genauigkeit = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) und Precision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Legende anzeigen </td> 
   <td colname="col2">Ermöglicht das Ein- und Ausschalten eines Legendenschlüssels im Entscheidungsbaum. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Dieser Menübefehl wird nur angezeigt, wenn der Entscheidungsbaum angezeigt wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erweitert </td> 
   <td colname="col2"> Klicken Sie auf , um das erweiterte Menü für die ausführliche Verwendung des Entscheidungsbaums zu öffnen. Menüoptionen finden Sie in der Tabelle unten. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Erweitertes Menü </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Größe des Trainings-Sets </td> 
   <td colname="col2"> <p>Steuert die Größe des für die Modellerstellung verwendeten Trainings-Sets. Größere Sets brauchen länger, kleinere Sets brauchen weniger Zeit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Normalization </td> 
   <td colname="col2"> <p> Ermöglicht dem Benutzer anzugeben, ob die Min-Max- oder die Z-Score-Technik verwendet werden soll, um Eingaben in das Modell zu normalisieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE-Überstichprobenfaktor </td> 
   <td colname="col2"> Wenn der positive Fall in der Trainings-Probe nicht sehr häufig (weniger als 10 Prozent) auftritt, wird SMOTE verwendet, um zusätzliche Beispiele bereitzustellen. Mit dieser Option kann der Benutzer angeben, wie viele weitere Beispiele mit SMOTE erstellt werden sollen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leaf-Klassenverteilungsschwellenwert </td> 
   <td colname="col2"> Ermöglicht das Festlegen der Schwelle, die für ein Blatt während des Baumstrukturerstellungsprozesses angenommen wird. Standardmäßig müssen alle Mitglieder eines Knotens identisch sein, damit es sich um ein Blatt handelt (vor dem Beschneiden). </td> 
  </tr> 
 </tbody> 
</table>
