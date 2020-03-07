---
description: Die Chord-Visualisierung ermöglicht es Ihnen, sowohl den Anteil als auch die Korrelation zwischen Metriken anzuzeigen und größere Akkorde als Indikator für eine stärkere Korrelation anzuzeigen.
title: Chord-Visualisierung
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Chord-Visualisierung{#chord-visualization}

Die Chord-Visualisierung ermöglicht es Ihnen, sowohl den Anteil als auch die Korrelation zwischen Metriken anzuzeigen und größere Akkorde als Indikator für eine stärkere Korrelation anzuzeigen.

Mit der Chord-Visualisierung können Sie Korrelationen zwischen Metriken identifizieren, sodass Sie mögliche Korrelationen hinzufügen und einfach auswerten können. Es bietet außerdem eine weitere Ansicht in einer zuvor erstellten [Korrelationsmatrix](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html). Mithilfe der Chord-Visualisierung können Sie keine positive oder negative Korrelation zwischen den Metriken identifizieren, sondern nur, dass eine Korrelation vorhanden ist. In bestimmten Fällen kann die Bestimmung einer direkten oder umgekehrten Beziehung durch Anwendung von Zählermetriken identifiziert werden.

1. **Öffnen Sie die **[!UICONTROL Chord]**Visualisierung**.

   Klicken Sie im Arbeitsbereich mit der rechten Maustaste [!DNL Visualization > Predictive Analytics > Chord].

1. **Wählen Sie eine Dimension aus dem Menü**.

   Es wird eine leere Visualisierung geöffnet, mit der Sie eine Dimension auswählen können. Der Dimensionsname wird oben in der leeren Akkordvisualisierung angezeigt.

   >[!NOTE]
   >
   >Wenn Sie bereits eine Korrelationsmatrix im Arbeitsbereich geöffnet haben, können Sie sie auch als Chord-Visualisierung wiedergeben.

1. **Wählen Sie zu korrelierende** Metriken aus.

   Ziehen Sie Metriken aus der Tabelle, **[!UICONTROL Finder]** indem Sie auf klicken, **[!UICONTROL Ctrl-Alt]** um Metriken aus der Tabelle in das Diagramm zu ziehen. Nach Auswahl von zwei oder mehr Metriken wird das Diagramm automatisch aktualisiert und zeigt Korrelationsdaten an. Fügen Sie nach Bedarf weitere Metriken hinzu, um Datenpunkte zu korrelieren.

   ![](assets/chord_drag_metric.png)

   Die Chord-Visualisierung zeigt den Anteil des Ganzen an, der durch den Bereich jedes Segments repräsentiert wird. Fügen Sie nach Bedarf weitere Metriken hinzu, um wichtige Beziehungen zu identifizieren und zu untersuchen.

   ![](assets/chord_selected.png)

1. **Zeigen Sie die Chord-Visualisierung** an.

   Bewegen Sie den Mauszeiger über die einzelnen Metriken in der Visualisierung, um Beziehungen anzuzeigen. In diesem Beispiel können Sie eine Korrelation zwischen Einheiten und den meisten anderen Metriken sehen (mit Ausnahme der Metrik **Besuchsdauer** ).

   ![](assets/chord_visualization_1.png)

   Wenn Sie den Mauszeiger über die Metrik &quot; **Besuchsdauer** &quot;in der Chord-Visualisierung bewegen, sehen Sie, dass es nur sehr wenig oder höchstens eine schwache Korrelation zwischen allen anderen Metriken gibt.

   ![](assets/chord_visualization_2.png)

1. **Einstellungen ändern.** Klicken Sie mit der rechten Maustaste auf die Chord-Visualisierung, um ein Menü zum Ändern der Dimension zu öffnen, die Dimensionen als absolute Zahlen oder Prozentwerte anzuzeigen, die ausgewählte Metrik oder alle Metriken zu entfernen, Farben und Details zu bearbeiten und Werte in eine Korrelationsmatrix zu exportieren.

   ![](assets/chord_menu.png)

