---
description: Ein 3D-Streudiagramm zeichnet die Elemente einer Datendimension (z. B. Tage oder Referrer-Site) in einem dreidimensionalen Raster auf, wobei die X-, Y- und Z-Achsen verschiedene Metriken darstellen.
solution: Analytics
title: 3D-Streudiagramme
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 3D-Streudiagramme{#d-scatter-plots}

Ein 3D-Streudiagramm zeichnet die Elemente einer Datendimension (z. B. Tage oder Referrer-Site) in einem dreidimensionalen Raster auf, wobei die X-, Y- und Z-Achsen verschiedene Metriken darstellen.

Wie das [Streudiagramm 2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots)ist diese Visualisierung nützlich, wenn versucht wird, die Beziehung zwischen einer großen Anzahl unterschiedlicher Elemente, die verschiedene Metriken verwenden, zu verstehen.

**So verwenden Sie die Visualisierung des 3D-Streudiagramms:**

1. Öffnen Sie eine neue Arbeitsfläche.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehend entsperren** klicken.
1. Klicken Sie mit der rechten Maustaste und wählen Sie **Visualisierung** > **3D-Streudiagramm**.

   Daraufhin **[!UICONTROL Dimensions]** wird eine Menüliste geöffnet.

1. Wählen Sie eine Dimension für die Abfrage aus.

   Das 3D-Streudiagramm öffnet die Standardmetriken für diese Dimension.

   ![](assets/3D_main.png)

   Wenn Sie das **[!UICONTROL Days]** Menü auswählen, wird auf den folgenden Achsen das folgende 3D-Streudiagramm mit den folgenden Standardmetriken angezeigt: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** und **[!UICONTROL z=Visits]**.

1. Metriken ändern Klicken Sie mit der rechten Maustaste auf die Metrikbeschriftung auf der X-, Y- oder Z-Achse und wählen Sie **[!UICONTROL Change Metric]**. Wählen Sie dann eine andere Metrik für die ausgewählte Achse aus.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Ziehen Sie eine Metrik auf eine der drei Achsenbeschriftungen und legen Sie sie ab, um die ausgewählte Achse in die Dropdown-Metrik zu ändern.
   >    * Ziehen Sie eine Metrik an eine andere Stelle der Visualisierung und legen Sie sie ab, um die Radiusmetrik für diese Achse zu ändern.
   >    * Ziehen Sie eine Dimension an eine beliebige Stelle der Visualisierung und legen Sie sie ab, um die Dimension für die Visualisierung zu ändern.


1. Ändern Sie die Radius-Metrik. Klicken Sie mit der rechten Maustaste auf den Titel oben auf der Seite (nach der ausgewählten Dimension benannt) und wählen Sie **[!UICONTROL Change Radius Metric]**.

   Die Metrik &quot;Radius&quot;definiert die Größe des geplotten Punkts basierend auf der Metrikauswahl. Die relative Position der Punkte ändert sich nicht im Streudiagramm, aber die Größe der gezeichneten Punkte innerhalb der Visualisierung wird basierend auf dem Metrikwert erhöht.

   ![](assets/3D_change_radius.png)

1. Setzen Sie die **[!UICONTROL Orthographic Camera]**. Mit dieser Option können Sie die gezeichneten Punkte im Verhältnis zu ihrer wahren Perspektive anhand der Radiusmetrik identifizieren, um eine dreidimensionale Verzerrung zu vermeiden.

   Wenn das 3D-Streudiagramm zuerst angezeigt wird, wird es in einer dreidimensionalen rotierenden Projektion angezeigt, was zu einer Verzerrung von Punkten führt, die näher an der Perspektive platziert werden, oder zu einer virtuellen &quot;Kamera&quot;. (Die näher an der Kamera liegenden Plots erscheinen viel größer als die Punkte, die sich weiter von der Kamera weg drehen.)

   Um diese perspektivische Verzerrung zu vermeiden, können Sie die **[!UICONTROL Orthographic Camera]** Option auswählen, indem Sie mit der rechten Maustaste auf den Titel klicken und aus dem Menü wählen. Dadurch können Sie die dreidimensionalen Objekte in zwei Dimensionen darstellen. Dadurch werden die gezeichneten Punkte als flach dargestellt und die Punkte werden relativ zur Radiusmetrik angezeigt, wodurch die dreidimensionalen Versatzwerte verringert werden.

1. Wählen Sie Punkte aus dem Streudiagramm.

   * **So entfernen Sie einen Punkt oder eine Punktgruppe**: Klicken Sie auf den Punkt.
   * **So fügen Sie Ihrer Auswahl** einen weiteren Punkt oder eine weitere Punktgruppe hinzu: Halten Sie die **Strg** -Taste gedrückt, **klicken Sie auf** einen Punkt oder **halten Sie die** Strg-Taste gedrückt und **ziehen Sie** über mehrere Punkte.

   * **So entfernen Sie einen Punkt oder eine Punktgruppe aus Ihrer Auswahl**: Halten Sie die **Umschalttaste** gedrückt und **klicken Sie auf** einen Punkt oder **halten** Sie die Umschalttaste **gedrückt und** ziehen Sie **** über mehrere Punkte.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

