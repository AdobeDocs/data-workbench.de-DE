---
description: Mit der Visualisierung der Assoziationstabelle können Sie Metriken mit Metriken, Dimensionen und Dimensionselementen verbinden, indem Sie den V-Algorithmus von Cramer verwenden.
title: Visualisierung von Assoziationstabellen
uuid: 4563c336-3377-4929-8694-8c0d00866825
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Visualisierung von Assoziationstabellen{#association-table-visualization}

Mit der Visualisierung der Assoziationstabelle können Sie Metriken mit Metriken, Dimensionen und Dimensionselementen verbinden, indem Sie den V-Algorithmus von Cramer verwenden.

Die Assoziierungstabelle vergleicht Werte mit der Cramers V-Berechnung, anstatt Pearsons Korrelationskoeffizient zu verwenden, wie in den Visualisierungen [Korrelationsmatrix](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) und [Korrelationschord](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) verwendet (diese können nur Metriken vergleichen, während die Assoziationstabelle und das [Assoziierungszeichen](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) Metriken, Dimensionen und Elemente vergleichen können).

## Erstellen einer Assoziationstabelle {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Die Assoziationstabelle vergleicht Metriken über eine zählbare oder nicht zählbare Dimension. Die Tabelle kann geändert werden, um Verbindungen innerhalb der Visualisierung durch Farbauswahl hervorzuheben oder als Textkarte, Heatmap oder beides zu rendern.

1. Öffnen Sie eine Assoziationstabelle.

   Klicken Sie mit der rechten Maustaste [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Wählen Sie eine erweiterte Dimension aus: eine Clickthrough-, Treffer-, Produkt-, Besuch- oder Besucherdimension. Eine Assoziationstabelle wird geöffnet, wobei die erweiterte Dimension in der Ecke identifiziert wird und die zugehörige Metrik sowohl in der Zeile als auch in der Spalte platziert wird.

   ![](assets/association_table1.png)

   Die Assoziationstabelle verwendet Cramers V als symmetrische Korrelation, was zu ausgewählten Metriken, Dimensionen und Elementwerten führt, die sowohl in den Spalten als auch in den Zeilen einer Assoziationstabelle angezeigt werden. Bei der Auswahl der Dimension &quot; **Produkt** **[!UICONTROL Visits]** erweitert&quot;wird beispielsweise die Metrik als zugehörige Metrik sowohl in der Zeile als auch in der Spalte der Tabelle verwendet, was zu einem perfekten, aber nutzlosen Vergleich (1,00) führt, da die Vergleichswerte identisch sind.

1. Fügen Sie der Assoziationstabelle weitere Werte hinzu.

   Klicken Sie mit der rechten Maustaste auf eine Spalte oder Zeile und wählen Sie Metrik **hinzufügen** oder Dimension **hinzufügen**. Sie können Metriken und Dimensionen auch aus einem **Finder** -Bedienfeld ziehen. Dimensionselemente können auch von einer geöffneten Tabelle in die Tabellenvisualisierung gezogen und abgelegt werden.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Es sind maximal zehn Zeilen und Spalten in der Assoziationstabelle zulässig.

