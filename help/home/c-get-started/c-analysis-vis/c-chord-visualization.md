---
description: Mit der Chord-Visualisierung können Sie sowohl den Anteil als auch die Korrelation zwischen Metriken anzeigen, indem Sie größere Akkorde als Hinweis auf eine stärkere Korrelation anzeigen.
title: Chord-Visualisierung
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
exl-id: d712f7b3-de2f-4ca4-a1bf-a2e4d42a084e
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Chord-Visualisierung{#chord-visualization}

Mit der Chord-Visualisierung können Sie sowohl den Anteil als auch die Korrelation zwischen Metriken anzeigen, indem Sie größere Akkorde als Hinweis auf eine stärkere Korrelation anzeigen.

Mit der Chord-Visualisierung können Sie Korrelationen zwischen Metriken identifizieren, sodass Sie mögliche Korrelationen hinzufügen und einfach auswerten können. Sie bietet außerdem eine weitere Ansicht in alle zuvor erstellten [Korrelationsmatrix](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html). Mit der Chord-Visualisierung können Sie keine positive oder negative Korrelation zwischen den Metriken identifizieren - nur, dass eine Korrelation vorhanden ist. In bestimmten Fällen kann die Bestimmung einer direkten oder umgekehrten Beziehung durch Anwendung von Zählermetriken identifiziert werden.

1. **Öffnen Sie die **[!UICONTROL Chord]**Visualisierung**.

   Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf [!DNL Visualization > Predictive Analytics > Chord].

1. **Wählen Sie eine Dimension aus dem Menü** aus.

   Daraufhin wird eine leere Visualisierung geöffnet, in der Sie eine Dimension auswählen können. Der Dimensionsname wird oben in der leeren Akkordvisualisierung angezeigt.

   >[!NOTE]
   >
   >Wenn Sie bereits eine Korrelationsmatrix im Arbeitsbereich geöffnet haben, können Sie sie auch als Chord-Visualisierung rendern.

1. **Wählen Sie zu korrelierende** Metriken aus.

   Ziehen Sie Metriken aus dem **[!UICONTROL Finder]**, indem Sie auf **[!UICONTROL Ctrl-Alt]** klicken, um Metriken aus der Tabelle in das Diagramm zu ziehen. Nachdem zwei oder mehr Metriken ausgewählt wurden, wird das Diagramm automatisch aktualisiert und zeigt Korrelationsdaten an. Fügen Sie nach Bedarf weitere Metriken hinzu, um Datenpunkte zu korrelieren.

   ![](assets/chord_drag_metric.png)

   Die Chord-Visualisierung zeigt den Anteil des Ganzen an, der durch den Bereich jedes Segments dargestellt wird. Fügen Sie nach Bedarf weitere Metriken hinzu, um wichtige Beziehungen zu identifizieren und zu untersuchen.

   ![](assets/chord_selected.png)

1. **Chord-Visualisierung anzeigen**.

   Bewegen Sie den Mauszeiger über die einzelnen Metriken in der Visualisierung, um die Beziehungen anzuzeigen. Im Beispiel können Sie eine Korrelation zwischen Einheiten und den meisten anderen Metriken sehen (mit Ausnahme der Metrik **Besuchsdauer** ).

   ![](assets/chord_visualization_1.png)

   Wenn Sie den Mauszeiger über die Metrik **Besuchsdauer** in der Chord-Visualisierung bewegen, sehen Sie, dass nur sehr geringe oder höchstens schwache Korrelationen zwischen allen anderen Metriken bestehen.

   ![](assets/chord_visualization_2.png)

1. **Einstellungen ändern.** Klicken Sie mit der rechten Maustaste auf die Chord-Visualisierung, um ein Menü zum Ändern der Dimension zu öffnen, die Dimensionen als absolute Zahlen oder Prozentwerte anzuzeigen, die ausgewählte Metrik oder alle Metriken zu entfernen, Farben und Details zu bearbeiten und Werte in eine Korrelationsmatrix zu exportieren.

   ![](assets/chord_menu.png)
