---
description: Mit Trendlinien können Sie Diagramme überlagern, um Daten zu vergleichen und zu interpretieren.
title: Trendlinien
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Trendlinien{#trend-lines}

Mit Trendlinien können Sie Diagramme überlagern, um Daten zu vergleichen und zu interpretieren.

Wie bei der Visualisierung [Streudiagramm](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) können Sie nun Trendlinien für eine Diagrammvisualisierung festlegen, um die Änderungsrate basierend auf linearen, exponentiellen, leistungsstarken oder polynomischen Linien anzuzeigen. Mit der Funktion Trendlinie können Sie Trendlinien in einem Diagramm überlagern, am häufigsten über eine Zeitdimension.

In diesem Diagrammvergleich können wir beispielsweise sehen, dass Besuche einen Trend nach oben zeigen, Bestellungen aber einen Trend nach unten zeigen.

![](assets/trend_line.png)

So fügen Sie eine Trendlinie hinzu

1. Öffnen Sie ein Diagramm und klicken Sie mit der rechten Maustaste auf den Metriknamen in der oberen linken Ecke.
1. Klicken Sie auf **[!UICONTROL Trend Lines]** und wählen Sie aus den Optionen aus.

   ![](assets/trend_line_graph.png)

   Sie können die Trendlinie auswählen, die über dem Diagramm angezeigt werden soll: **Einfache Linear**, **Exponentiell**, **Power** oder **Polynomial**. Polynomial erzeugt eine polynomielle Regressions-Trendlinie. Einfache Linear erstellt eine Trendlinie als Änderungsrate entlang der Regressionslinie. Exponentiell berechnet eine Trendlinie als y = b*exp( a*x ) und Power als y = b*x`<sup>a</sup>`.

   Der Trend wird berechnet und im Diagramm gerendert. Daraufhin wird ein Callout mit detaillierten Informationen zur Trendgleichung geöffnet.

   ![](assets/trend_line_detail.png)
