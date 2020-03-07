---
description: Führen Sie die folgenden Schritte aus, um die Propensity-Scoring-Visualisierung zu verwenden.
solution: Analytics
title: Einrichten der Tendenzauswertung
topic: Data workbench
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Einrichten der Tendenzauswertung{#setting-up-propensity-scoring}

Führen Sie die folgenden Schritte aus, um die Propensity-Scoring-Visualisierung zu verwenden.

1. Öffnen Sie eine neue Arbeitsfläche und klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Legen Sie die Variable **[!UICONTROL Target]** (die abhängige Variable) fest.

   Legen Sie die abhängige Variable wie folgt fest:

* **Dimensionselemente**: Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]**. Wählen Sie dann Dimensionselemente als abhängige Variable aus.

   ODER

* **[!UICONTROL Filter Editor]**. Klicken Sie auf **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** , um die Filter-Editor-Visualisierung zu öffnen.

   ![](assets/propensity_visualization_filter_editor.png)

   Nachdem Sie ein Dimensionselement oder einen Filter als abhängige Variable ausgewählt haben, klicken Sie auf **[!UICONTROL Set Target]** und geben Sie einen Namen ein, um die abhängige Variable zu beschreiben. Klicken Sie dann auf **[!UICONTROL OK]** (und stellen Sie sicher, dass das Filterfeld markiert ist), um das Ziel festzulegen.

   ![](assets/propensity_visualization_setTarget.png)

   Der Name, den Sie dem Ziel geben, ist die abhängige Variable, die im linken Bereich angezeigt wird.
1. Fügen Sie unabhängige Variablen hinzu.

   Fügen Sie die unabhängigen Variablen mithilfe von Metriken oder Dimensionselementen hinzu.

   ![](assets/propensity_visualization_metrics.png)

* **Metriken**. Wählen Sie in der Werkzeugleiste Tendenzauswertung eine Metrik aus dem **[!UICONTROL Metrics]** Menü.

* **Dimensionselemente**: Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **[!UICONTROL Table]**. Wählen Sie ein oder mehrere Dimensionselemente aus und ziehen Sie mit den Tasten **[!UICONTROL Independent Variables]** + in die linke Spalte unter **[!UICONTROL Element]** oder in das `<Ctrl>` `<Alt>` Feld.

1. Legen Sie **[!UICONTROL Training Filter]**. Sie können den Besuchersatz definieren, den Sie bewerten möchten, indem Sie in der Werkzeugleiste Tendenzauswertung auf **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** klicken. Dies stellt eine Untergruppe von Daten bereit, die ausschließlich mit den Besuchern erstellt wurden, die Sie bewerten möchten. Beispielsweise Besucher, die im letzten Monat einen Besuch abstatteten, Besucher mit Wohnsitz in Australien oder Besucher, die bestimmte Produkte angesehen haben.

   Der Standardfilter ist **[!UICONTROL Train on Everyone]** festgelegt, Sie können ihn jedoch ändern, indem Sie **[!UICONTROL Dimension Elements]** in einer Tabelle aktivieren oder einen Filter mit der **[!UICONTROL Filter Editor]** Option erstellen.

   Nachdem Sie ein Dimensionselement ausgewählt oder einen Filter erstellt haben, klicken Sie bei Aktivierung auf **Optionen** > **Schulungsfilter** festlegen, geben Sie einen Namen ein, um den Filter zu beschreiben, und klicken Sie dann auf **[!UICONTROL OK]**.
1. Sobald Sie alle Eingaben identifiziert haben, drücken Sie **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Der Bewertungsvorgang beginnt mit der mehrfachen Übergabe der Daten. Die Ergebnisse werden dann als Balkendiagramm über einer Prozentzeile angezeigt.
1. Propensity-Score speichern.

   Ab 6.1 haben Sie jetzt eine Option, wenn Sie die Tendenzauswertung speichern verwenden:

* Dimension
* Dimension und Metrik

   Sie können am Ende zwei gespeicherte Dateien haben, sowohl eine Dimension als auch eine definierte Metrik.

   >[!NOTE]
   >
   >Wenn Sie die Tendenzbewertung zur Verarbeitung senden, erhalten Sie nur eine Dimension.

   Die abgeleitete Metrik ist die zugehörige Metrik für das durchschnittliche Ergebnis.
1. Überprüfen Sie die Genauigkeit.

   Das System zeigt ein Bewertungsmodell an **[!UICONTROL Model Complete]** und generiert es, wenn der Prozess abgeschlossen ist.

   Durch Rechtsklick auf **[!UICONTROL Model Complete]** wird die Genauigkeit des vom System definierten Bewertungsmodells identifiziert. Werte von 0 bis 100 Prozent geben die Wahrscheinlichkeit an, mit der die Besucher die **[!UICONTROL Target]** Variable abgleichen.

   Die Verwechslungsmatrix gibt vier Werte aus der Kombination von &quot;Aktiv Positiv (AP)&quot;, &quot;Aktiv Negativ (AN)&quot;, &quot;Vorhersage Positiv (PP)&quot;und &quot;Vorhersage Negativ&quot;(PN). Diese Zahlen erhalten Sie, indem Sie das Ergebnisbewertungsmodell auf die 20 % zurückbehaltenen Testdaten anwenden, von denen wir die richtige Antwort kennen. Wenn der Wert größer als 50 % ist, wird er als positiver Fall vorhergesagt (Übereinstimmung mit dem definierten Ereignis).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Genauigkeit</b> </td> 
   <td colname="col2"> Gibt an, wie genau das Modell ist, indem die korrekten Vorhersagen für alle Vorhersagen identifiziert werden. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Abruf</b> </td> 
   <td colname="col2"> Identifiziert die Fähigkeit, das Bewertungsmodell erneut zu identifizieren. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Präzision</b> </td> 
   <td colname="col2">Identifiziert den Grad der Diskrepanz. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Öffnen Sie ein [Lift- oder Gewinndiagramm](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)oder den [Modell-Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Klicken Sie mit der rechten Maustaste auf die Visualisierung **Modell abgeschlossen** und wählen Sie **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** oder **[!UICONTROL Model Viewer.]**
