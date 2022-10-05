---
description: Mit der Visualisierung von Assoziations-Chord können Sie sowohl den Anteil als auch die Verknüpfung zwischen Metriken, Dimensionen und Elementen anzeigen und größere Akkorde als Hinweis auf eine stärkere Verknüpfung anzeigen.
title: Chord-Visualisierung von Assoziationen
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
exl-id: e71394ef-4895-4a3e-912d-d6f56ca8f001
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 1%

---

# Chord-Visualisierung von Assoziationen{#association-chord-visualization}

{{eol}}

Mit der Visualisierung von Assoziations-Chord können Sie sowohl den Anteil als auch die Verknüpfung zwischen Metriken, Dimensionen und Elementen anzeigen und größere Akkorde als Hinweis auf eine stärkere Verknüpfung anzeigen.

Die Assoziationstabelle vergleicht Werte mit der Cramer-V-Berechnung, anstatt den Korrelationskoeffizienten von Pearson zu verwenden, der in der Variablen [Korrelationsmatrix](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) und [Korrelations-Chord](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) Visualisierungen (diese können nur Metriken vergleichen, während die Assoziationstabelle und das Akkord Metriken, Dimensionen und Elemente vergleichen können). Der Chord für Verknüpfungen bietet außerdem eine weitere Ansicht in einem zuvor erstellten [Assoziationstabelle](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f).

**So erstellen Sie einen Assoziations-Chord**

1. Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste auf **Visualisierung > Prädiktive Analyse > Assoziations-Chord**.

   Daraufhin wird ein Menü geöffnet, in dem Sie eine erweiterte Dimension aus der Liste auswählen können.

   ![](assets/association_chord1.png)

   Nach der Auswahl wird die leere Zuordnungstabelle mit der im Titel angegebenen Dimension geöffnet. ![](assets/association_chord2.png)

1. **Metrik, Dimension oder Dimensionselement auswählen**.

   Klicken Sie mit der rechten Maustaste auf die Akkordvisualisierung und wählen Sie **Metrik hinzufügen** oder **Dimension hinzufügen**. Wählen Sie Elemente aus dem Menü aus, die Sie dem Akkord hinzufügen möchten.

   Sie können auch Metriken und Dimensionen aus der **[!UICONTROL Finder]** durch Klicken auf **[!UICONTROL Ctrl-Alt]** und das Ziehen von Metriken und Dimensionen in den Akkord. Oder ziehen Sie Dimensionselemente direkt aus einer offenen Tabelle in die Akkordvisualisierung.

1. **Zusätzliche Metriken, Dimensionen und Elemente auswählen, die verknüpft werden sollen**.

   Nachdem zwei oder mehr Werte ausgewählt wurden, wird das Diagramm automatisch aktualisiert und zeigt die Zuordnungsdaten an. Fügen Sie nach Bedarf weitere Metriken hinzu, um Datenpunkte zuzuordnen.

   ![](assets/association_chord.png)

   Die Chord-Visualisierung zeigt den Anteil des Ganzen an, der durch den Bereich jedes Segments dargestellt wird. Fügen Sie nach Bedarf Metriken/Dimensionen/Elemente hinzu, um wichtige Beziehungen zu identifizieren und zu untersuchen.

1. **Chord-Visualisierung anzeigen**.

   Bewegen Sie den Mauszeiger über die einzelnen Werte in der Visualisierung, um die Beziehungen anzuzeigen.

1. **Einstellungen ändern.** Klicken Sie mit der rechten Maustaste auf die Akkordvisualisierung, um ein Menü zu öffnen, in dem die Metrik, Dimension oder Elemente geändert werden, um die Dimensionen als absolute Zahlen oder Prozentwerte anzuzeigen, die ausgewählte Metrik oder alle Metriken zu entfernen, Farben und Details zu bearbeiten und Werte in eine Assoziationstabelle zu exportieren.

**So erstellen Sie einen Assoziations-Chord aus einer Assoziationstabelle:**

1. Öffnen Sie eine **Assoziationstabelle** Visualisierung.
1. Klicken Sie mit der rechten Maustaste und wählen Sie **Chord-Visualisierung exportieren**. Daraufhin wird ein Diagramm für Assoziations-Akkord mit den in der Assoziationstabelle ausgewählten Werten geöffnet. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Durch das Exportieren einer Assoziationstabelle aus einem zugehörigen Akkorddiagramm, das mindestens eine Metrik enthält, werden doppelte Elemente in den Zeilen/Spalten der Assoziationstabelle angezeigt. Um doppelte Elemente zu vermeiden, erstellen Sie eine neue Assoziationstabelle und fügen Sie die gewünschten Elemente hinzu, anstatt die Elemente aus einem Assoziations-Chord-Diagramm zu exportieren.
