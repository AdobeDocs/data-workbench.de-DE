---
description: Mit der Visualisierung Zuordnungstabelle können Sie Metriken mit Metriken, Dimensionen und Dimensionselementen verknüpfen, indem Sie den V-Algorithmus von Cramer verwenden.
title: Visualisierung mittels Assoziationstabelle
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 2%

---

# Visualisierung mittels Assoziationstabelle{#association-table-visualization}

{{eol}}

Mit der Visualisierung Zuordnungstabelle können Sie Metriken mit Metriken, Dimensionen und Dimensionselementen verknüpfen, indem Sie den V-Algorithmus von Cramer verwenden.

Die Assoziationstabelle vergleicht Werte mit der Cramers V-Berechnung, anstatt den Korrelationskoeffizienten von Pearson zu verwenden, der in der Variablen [Korrelationsmatrix](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) und [Korrelations-Chord](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) Visualisierungen (diese können nur Metriken vergleichen, während die Assoziationstabelle und [Assoziations-Chord](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) kann Metriken, Dimensionen und Elemente vergleichen).

## Erstellen einer Zuordnungstabelle {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Die Assoziationstabelle vergleicht Metriken über eine zählbare oder nicht zählbare Dimension. Die Tabelle kann geändert werden, um Verknüpfungen innerhalb der Visualisierung durch Farbauswahl hervorzuheben oder als Textkarte, Heatmap oder beides zu rendern.

1. Öffnen Sie eine Assoziationstabelle.

   Rechtsklick [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Wählen Sie eine erweiterte Dimension aus - eine Clickthrough-, Treffer-, Produkt-, Besuchs- oder Besucherdimension. Daraufhin wird eine Assoziationstabelle geöffnet, in der die erweiterte Dimension in der Ecke identifiziert und die zugehörige Metrik sowohl in der Zeile als auch in der Spalte platziert wird.

   ![](assets/association_table1.png)

   Die Assoziationstabelle verwendet Cramers V als symmetrische Korrelation, was zu ausgewählten Metriken, Dimensionen und Elementwerten führt, die sowohl in den Spalten als auch in den Zeilen einer Assoziationstabelle angezeigt werden. Wählen Sie beispielsweise die **Produkt** Die erweiterte Dimension verwendet **[!UICONTROL Visits]** Metrik als zugehörige Metrik in Zeile und Spalte der Tabelle verwenden, was zu einem perfekten, aber nutzlosen Vergleich (1,00) führt, da die verglichenen Werte identisch sind.

1. Fügen Sie der Assoziationstabelle weitere Werte hinzu.

   Klicken Sie mit der rechten Maustaste auf eine Spalte oder Zeile und wählen Sie **Metrik hinzufügen** oder **Dimension hinzufügen**. Sie können auch Metriken und Dimensionen aus einer **Finder** Bereich. Dimension-Elemente können auch aus einer offenen Tabelle in die Tabellenvisualisierung gezogen und dort abgelegt werden.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >In der Assoziationstabelle sind maximal zehn Zeilen und Spalten zulässig.
