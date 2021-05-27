---
description: Streudiagramme zeichnen die Elemente einer Datendimension (z. B. Seite oder Stadt) in einem Raster aus, in dem die X- und Y-Achsen verschiedene Metriken darstellen.
title: 2D-Streudiagramme
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
exl-id: 340f8c18-ce47-4f3a-aba4-3d6124505313
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# 2D-Streudiagramme{#d-scatter-plots}

Streudiagramme zeichnen die Elemente einer Datendimension (z. B. Seite oder Stadt) in einem Raster aus, in dem die X- und Y-Achsen verschiedene Metriken darstellen.

Streudiagramme können nützlich sein, wenn Sie versuchen, die Beziehung zwischen einer großen Anzahl unterschiedlicher Elemente anhand von zwei verschiedenen Metriken zu verstehen. Im folgenden Beispiel zeigt das Streudiagramm jede Stadt anhand der Anzahl der Besucher und der jeweiligen Treuerate an.

![](assets/vis_ScatterPlot_City.png)

Mit dem Streudiagramm können Sie die Ausreißer schnell sehen. Salt Lake City beispielsweise hat eine überdurchschnittliche Treuerate pro Besucher.

Streudiagramme können auch verwendet werden, um die Konsistenz der Daten zu zeigen. Im folgenden Beispiel zeigt das Streudiagramm die Anzahl der Besucher mit Sitzungen einer bestimmten Länge.

![](assets/vis_ScatterPlot_SessionDuration.png)

Die Größe jedes Punkts auf dem Streudiagramm wird durch die Radius-Metrik bestimmt. Die Standardradius-Metrik unterscheidet sich für jede Adobe App. Beispielsweise basiert die Radius-Metrik in [!DNL Site] standardmäßig auf Sitzungen. Sie können die Metrik &quot;Radius&quot;ändern, damit die Punkte in Ihren Streudiagrammen jede verfügbare Metrik darstellen. Anweisungen dazu finden Sie unter [Ändern von Radius-Metriken](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) Die Farbe der Punkte basiert auf der Farblegende, die im Arbeitsbereich geöffnet ist. Weitere Informationen zu Farblegenden finden Sie unter [Farblegenden](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Auswählen von Punkten {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**So wählen Sie einen einzelnen Punkt aus**

* Klicken Sie auf den Punkt.

**So fügen Sie Ihrer Auswahl einen weiteren Punkt oder eine Punktgruppe hinzu**

* Halten Sie beim Klicken die Strg- oder Strg- bzw. Umschalttaste gedrückt, um mehrere Punkte zu überwinden.

**So entfernen Sie einen Punkt oder eine Punktgruppe aus Ihrer Auswahl**

* Klicken Sie bei gedrückter Umschalt- oder Umschalttaste über mehrere Punkte.

## Ändern von Dimensionen {#section-796cd962ef3f476caa89d99083782ed1}

* Klicken Sie oben im Diagramm mit der rechten Maustaste auf den Titel der Dimension und klicken Sie auf **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]***.

## Ändern von Metriken {#section-44b8be9215cd4039b1eeb98ae1b31445}

**So ändern Sie die auf der x- oder y-Achse eines Streudiagramms angezeigte Metrik**

* Klicken Sie mit der rechten Maustaste auf den Titel der Metrik, die Sie ändern möchten, und klicken Sie auf **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]***.

## Ändern von Radius-Metriken {#section-fd80576d583c430cb469daf12e39aa2a}

**So ändern Sie die Radius-Metrik eines Streudiagramms**

Klicken Sie oben im Diagramm mit der rechten Maustaste auf den Titel der Dimension und klicken Sie auf **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]***.

![](assets/mnu_ScatterPlot_Change.png)
