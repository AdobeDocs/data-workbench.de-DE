---
description: Führen Sie diese Schritte aus, um die Visualisierung der Tendenzauswertung zu verwenden.
title: Einrichten der Tendenzauswertung
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Einrichten der Tendenzauswertung{#setting-up-propensity-scoring}

{{eol}}

Führen Sie diese Schritte aus, um die Visualisierung der Tendenzauswertung zu verwenden.

1. Öffnen Sie einen neuen Arbeitsbereich und klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Legen Sie die **[!UICONTROL Target]** (die abhängige Variable).

   Legen Sie die abhängige Variable fest, indem Sie Folgendes auswählen:

* **Dimensionen**: Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]**. Wählen Sie dann eine Dimension als abhängige Variable aus.

   OR

* **[!UICONTROL Filter Editor]**. Klicken **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** , um die Visualisierung des Filter-Editors zu öffnen.

   ![](assets/propensity_visualization_filter_editor.png)

   Nachdem Sie ein Dimension-Element oder Filter als abhängige Variable ausgewählt haben, klicken Sie auf **[!UICONTROL Set Target]** Geben Sie einen Namen ein, um die abhängige Variable zu beschreiben. Klicken Sie anschließend auf **[!UICONTROL OK]** (und stellen Sie sicher, dass das Filterfeld hervorgehoben ist), um Target festzulegen.

   ![](assets/propensity_visualization_setTarget.png)

   Der Name, den Sie dem Ziel geben, ist die abhängige Variable, die im linken Bereich angezeigt wird.
1. Fügen Sie unabhängige Variablen hinzu.

   Fügen Sie die unabhängigen Variablen mithilfe von Metriken oder Dimension-Elementen hinzu.

   ![](assets/propensity_visualization_metrics.png)

* **Metriken**. Wählen Sie in der Symbolleiste Tendenzauswertung eine Metrik aus der **[!UICONTROL Metrics]** Menü.

* **Dimensionen**: Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]**. Wählen Sie ein oder mehrere Dimension -Elemente aus und ziehen Sie sie in die linke Spalte unter **[!UICONTROL Independent Variables]** oder **[!UICONTROL Element]** mit dem `<Ctrl>` + `<Alt>` Schlüssel.

1. Festlegen **[!UICONTROL Training Filter]**. Sie können den Besuchersatz definieren, den Sie bewerten möchten, indem Sie auf **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** in der Symbolleiste &quot;Tendenzauswertung&quot;. Dadurch erhalten Sie eine Untergruppe von Daten, die ausschließlich mit den Besuchern erstellt werden, die Sie bewerten möchten. Zum Beispiel Besucher, die im letzten Monat einen Besuch abgestattet haben, Besucher, die in Australien wohnen, oder Besucher, die bestimmte Produkte angesehen haben.

   Der Standardfilter ist **[!UICONTROL Train on Everyone]** Sie können sie jedoch ändern, indem Sie **[!UICONTROL Dimension Elements]** in einer Tabelle oder beim Erstellen eines Filters mit der **[!UICONTROL Filter Editor]**.

   Nachdem Sie ein Filterelement ausgewählt oder einen Dimension erstellt haben, klicken Sie bei Aktivierung auf **Optionen** > **Trainings-Filter festlegen**, geben Sie einen Namen ein, um den Filter zu beschreiben, und klicken Sie dann auf **[!UICONTROL OK]**.
1. Sobald Sie alle Eingaben identifiziert haben, drücken Sie die **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Der Scoring-Prozess beginnt mit der mehrfachen Übergabe der Daten. Anschließend werden die Ergebnisse als Balkendiagramme über eine Prozentzeile angezeigt.
1. Sparen Sie Propensity Score.

   Ab Version 6.1 haben Sie jetzt eine Option bei der Verwendung der Tendenzbewertung speichern:

* Dimension
* Dimension und Metrik

   Sie können mit zwei gespeicherten Dateien enden, sowohl einer Dimension als auch einer definierten Metrik.

   >[!NOTE]
   >
   >Wenn Sie die Tendenzbewertung zur Verarbeitung senden, erhalten Sie nur eine Dimension.

   Die abgeleitete Metrik ist die zugehörige Metrik für das durchschnittliche Ergebnis.
1. Prüfen Sie die Genauigkeit.

   Das System zeigt **[!UICONTROL Model Complete]** und generieren ein Scoring-Modell, wenn der Prozess abgeschlossen ist.

   Rechtsklick auf **[!UICONTROL Model Complete]** erkennt die Genauigkeit des vom System definierten Scoring-Modells. Werte zwischen 0 Prozent und 100 Prozent identifizieren die Wahrscheinlichkeit, dass die Besucher die **[!UICONTROL Target]** -Variable.

   Die Konfusionsmatrix gibt vier Zählungen anhand der Kombination aus &quot;Tatsächlich positiv&quot;(AP), &quot;Aktiv Negativ&quot;(AN), &quot;Vorhersage positiv&quot;(PP) und &quot;Vorhersage negativ&quot;(PN). Diese Zahlen erhalten Sie, indem Sie das resultierende Scoring-Modell auf die 20 % zurückbehaltenen Testdaten anwenden, von denen wir die wahre Antwort kennen. Wenn der Wert größer als 50 % ist, wird er als positiver Fall prognostiziert (entspricht dem definierten Ereignis).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Genauigkeit</b> </td> 
   <td colname="col2"> Gibt an, wie genau das Modell ist, indem die korrekten Prognosen für alle Prognosen identifiziert werden. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Rückruf</b> </td> 
   <td colname="col2"> Identifiziert die Möglichkeit, das Scoring-Modell erneut zu identifizieren. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Genauigkeit</b> </td> 
   <td colname="col2">Identifiziert die Diskrepanz. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Öffnen Sie eine [Diagramm für Steigerung oder Gewinn](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)oder [Modell-Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Klicken Sie mit der rechten Maustaste auf die **Modell abgeschlossen** Visualisierung und Auswahl **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** oder **[!UICONTROL Model Viewer.]**
