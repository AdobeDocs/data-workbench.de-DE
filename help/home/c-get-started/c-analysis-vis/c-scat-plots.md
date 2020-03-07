---
description: Streudiagramme zeichnen die Elemente einer Datendimension (z. B. Seite oder Stadt) in einem Raster ab, in dem die X- und Y-Achsen verschiedene Metriken darstellen.
solution: Analytics
title: 2D-Streudiagramme
topic: Data workbench
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 2D-Streudiagramme{#d-scatter-plots}

Streudiagramme zeichnen die Elemente einer Datendimension (z. B. Seite oder Stadt) in einem Raster ab, in dem die X- und Y-Achsen verschiedene Metriken darstellen.

Streudiagramme können nützlich sein, wenn Sie versuchen, die Beziehung zwischen einer großen Anzahl unterschiedlicher Elemente, nach zwei verschiedenen Metriken, zu verstehen. Im folgenden Beispiel zeigt das Streudiagramm jede Stadt nach Anzahl der Besucher und der jeweiligen Retentionsrate an.

![](assets/vis_ScatterPlot_City.png)

Mit dem Streudiagramm können Sie die Ausreißer schnell sehen. Salt Lake City beispielsweise hat eine überdurchschnittliche Retentionsrate pro Besucher.

Streudiagramme können auch verwendet werden, um die Konsistenz der Daten zu zeigen. Im folgenden Beispiel zeigt das Streudiagramm die Anzahl der Besucher mit Sitzungen einer bestimmten Länge.

![](assets/vis_ScatterPlot_SessionDuration.png)

Die Größe der einzelnen Punkte auf dem Streudiagramm wird durch die Radiusmetrik bestimmt. Die Standardradius-Metrik unterscheidet sich für jede Adobe-Anwendung. Beispielsweise basiert die Metrik &quot;Radius&quot; [!DNL Site]standardmäßig auf Sitzungen. Sie können die Radiusmetrik ändern, damit die Punkte in Ihren Streudiagrammen eine beliebige verfügbare Metrik darstellen. Anweisungen dazu finden Sie unter [Ändern von Radius-Metriken](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) Die Farbe der Punkte basiert auf der Farblegende, die im Arbeitsbereich geöffnet ist. Weitere Informationen zu Farblegenden finden Sie unter [Farblegende](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Punkte auswählen {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**So wählen Sie einen einzelnen Punkt aus**

* Klicken Sie auf den Punkt.

**So fügen Sie Ihrer Auswahl einen anderen Punkt oder eine weitere Punktgruppe hinzu**

* Halten Sie beim Klicken die Strg- bzw. Strg- bzw. Umschalttaste gedrückt und ziehen Sie über mehrere Punkte.

**So entfernen Sie einen Punkt oder eine Punktgruppe aus Ihrer Auswahl**

* Halten Sie beim Klicken die Umschalttaste gedrückt, oder ziehen Sie bei gedrückter Umschalttaste über mehrere Punkte.

## Ändern von Dimensionen {#section-796cd962ef3f476caa89d99083782ed1}

* Klicken Sie mit der rechten Maustaste auf die Beschriftung der Dimension oben im Diagramm und klicken Sie auf **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Ändern von Metriken {#section-44b8be9215cd4039b1eeb98ae1b31445}

**So ändern Sie die Metrik auf der X- oder Y-Achse eines Streudiagramms**

* Klicken Sie mit der rechten Maustaste auf die Bezeichnung der zu ändernden Metrik und klicken Sie auf **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Ändern von Radiusmetriken {#section-fd80576d583c430cb469daf12e39aa2a}

**So ändern Sie die Radiusmetrik eines Streudiagramms**

Klicken Sie mit der rechten Maustaste auf die Beschriftung der Dimension oben im Diagramm und klicken Sie auf **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)

