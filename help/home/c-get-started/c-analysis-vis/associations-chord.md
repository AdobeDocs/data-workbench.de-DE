---
description: Mit der Visualisierung des Assoziierungszeichens können Sie sowohl den Anteil als auch die Verbindung zwischen Metriken, Dimensionen und Elementen anzeigen, wobei größere Akkorde als Indikator für eine stärkere Verknüpfung angezeigt werden.
title: Visualisierung von Assoziations-Akkord
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualisierung von Assoziations-Akkord{#association-chord-visualization}

Mit der Visualisierung des Assoziierungszeichens können Sie sowohl den Anteil als auch die Verbindung zwischen Metriken, Dimensionen und Elementen anzeigen, wobei größere Akkorde als Indikator für eine stärkere Verknüpfung angezeigt werden.

Die Assoziationstabelle vergleicht Werte mit der V-Berechnung von Cramer, statt Pearson den Korrelationskoeffizienten zu verwenden, der in den Visualisierungen [Korrelationsmatrix](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) und [Korrelationshebel](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) verwendet wird (diese können nur Metriken vergleichen, während die Assoziationstabelle und das Akkord Metriken, Dimensionen und Elemente vergleichen können). Das Vereinsregister bietet außerdem eine weitere Ansicht in einer zuvor erstellten [Assoziationstabelle](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f).

**So erstellen Sie ein Assoziierungsabkommen**

1. Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste auf **Visualisierung > Prädiktive Analyse > Vereinigungszeichen**.

   Daraufhin wird ein Menü geöffnet, in dem Sie eine erweiterte Dimension aus der Liste auswählen können.

   ![](assets/association_chord1.png)

   Nach der Auswahl wird die leere Assoziationstabelle mit der im Titel angegebenen ausgewählten Dimension geöffnet. ![](assets/association_chord2.png)

1. **Wählen Sie eine Metrik, Dimension oder ein Dimensionselement** aus.

   Klicken Sie mit der rechten Maustaste auf die Akkordvisualisierung und wählen Sie **Metrik** hinzufügen oder Dimension **hinzufügen**. Wählen Sie Elemente aus dem Menü aus, die Sie dem Akkord hinzufügen möchten.

   Sie können Metriken und Dimensionen auch aus der **[!UICONTROL Finder]** Liste ziehen, indem Sie auf Metriken **[!UICONTROL Ctrl-Alt]** und Dimensionen klicken und sie in die Liste ziehen. Oder ziehen Sie Dimensionselemente direkt von einer geöffneten Tabelle in die Akkordvisualisierung.

1. **Wählen Sie zusätzliche Metriken, Dimensionen und Elemente aus, die Sie verknüpfen** möchten.

   Nachdem zwei oder mehr Werte ausgewählt wurden, wird das Diagramm automatisch aktualisiert und es werden Verknüpfungsdaten angezeigt. Fügen Sie nach Bedarf weitere Metriken hinzu, um Datenpunkte zuzuordnen.

   ![](assets/association_chord.png)

   Die Chord-Visualisierung zeigt den Anteil des Ganzen an, der durch den Bereich jedes Segments repräsentiert wird. Fügen Sie nach Bedarf weitere Metriken/Dimensionen/Elemente hinzu, um wichtige Beziehungen zu identifizieren und zu untersuchen.

1. **Zeigen Sie die Chord-Visualisierung** an.

   Bewegen Sie den Mauszeiger über jeden Wert in der Visualisierung, um Beziehungen anzuzeigen.

1. **Einstellungen ändern.** Klicken Sie mit der rechten Maustaste auf die Akkordvisualisierung, um ein Menü zu öffnen, um die Metrik, Dimension oder Elemente zu ändern und die Dimensionen als absolute Zahlen oder Prozentwerte anzuzeigen, die ausgewählte Metrik oder alle Metriken zu entfernen, Farben und Details zu bearbeiten und Werte in eine Assoziationstabelle zu exportieren.

**So erstellen Sie ein Assoziierungszeichen aus einer Assoziationstabelle:**

1. Öffnen Sie eine **Visualisierung der** Assoziationstabelle.
1. Klicken Sie mit der rechten Maustaste und wählen Sie **Visualisierung** exportieren. Daraufhin wird ein Diagramm mit den in der Assoziationstabelle ausgewählten Werten geöffnet. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Das Exportieren einer Assoziationstabelle aus einem Vereinsfelddiagramm, das mindestens eine Metrik enthält, führt zu doppelten Elementen in den Zeilen/Spalten der Assoziationstabelle. Um doppelte Elemente zu vermeiden, erstellen Sie eine neue Assoziierungstabelle und fügen Sie die gewünschten Elemente hinzu, anstatt die Elemente aus einem Assoziierungszeichendiagramm zu exportieren.

