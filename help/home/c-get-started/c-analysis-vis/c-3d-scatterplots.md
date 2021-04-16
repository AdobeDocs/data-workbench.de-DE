---
description: Ein 3D-Streudiagramm zeichnet die Elemente einer Datendimension (z. B. Tage oder Referrer-Site) in einem dreidimensionalen Raster auf, wobei die X-, Y- und Z-Achsen verschiedene Metriken darstellen.
title: 3D-Streudiagramme
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 1%

---

# 3D-Streudiagramme{#d-scatter-plots}

Ein 3D-Streudiagramm zeichnet die Elemente einer Datendimension (z. B. Tage oder Referrer-Site) in einem dreidimensionalen Raster auf, wobei die X-, Y- und Z-Achsen verschiedene Metriken darstellen.

Wie beim Streudiagramm 2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots) ist diese Visualisierung nützlich, wenn versucht wird, die Beziehung zwischen einer großen Anzahl unterschiedlicher Elemente, die verschiedene Metriken verwenden, zu verstehen.[

**So verwenden Sie die Visualisierung des 3D-Streudiagramms:**

1. Öffnen Sie eine neue Arbeitsfläche.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehend entsperren** klicken.
1. Klicken Sie mit der rechten Maustaste und wählen Sie **Visualisierung** > **3D-Streudiagramm**.

   Daraufhin wird ein Menü mit der Liste **[!UICONTROL Dimensions]** geöffnet.

1. Wählen Sie eine Dimension für die Abfrage aus.

   Das 3D-Streudiagramm öffnet die Standardmetriken für diese Dimension.

   ![](assets/3D_main.png)

   Wenn Sie das Menü **[!UICONTROL Days]** auswählen, wird das folgende 3D-Streudiagramm mit diesen Standardmetriken auf den folgenden Achsen angezeigt: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** und **[!UICONTROL z=Visits]**.

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

1. Setzen Sie **[!UICONTROL Orthographic Camera]** ein. Mit dieser Option können Sie die gezeichneten Punkte im Verhältnis zu ihrer wahren Perspektive anhand der Radiusmetrik identifizieren, um eine dreidimensionale Verzerrung zu vermeiden.

   Wenn das 3D-Streudiagramm zuerst angezeigt wird, wird es in einer dreidimensionalen rotierenden Projektion angezeigt, was zu einer Verzerrung von Punkten führt, die näher an der Perspektive platziert werden, oder zu einer virtuellen &quot;Kamera&quot;. (Die näher an der Kamera liegenden Plots erscheinen viel größer als die Punkte, die sich weiter von der Kamera weg drehen.)

   Um diese perspektivische Verzerrung zu vermeiden, können Sie die Option **[!UICONTROL Orthographic Camera]** auswählen, indem Sie mit der rechten Maustaste auf den Titel klicken und aus dem Menü wählen. Dadurch können Sie die dreidimensionalen Objekte in zwei Dimensionen darstellen. Dadurch werden die gezeichneten Punkte als flach dargestellt und die Punkte werden relativ zur Radiusmetrik angezeigt, wodurch die dreidimensionalen Versatzwerte verringert werden.

1. Wählen Sie Punkte aus dem Streudiagramm.

   * **So entfernen Sie einen Punkt oder eine Punktgruppe**: Klicken Sie auf den Punkt.
   * **So fügen Sie Ihrer Auswahl** einen weiteren Punkt oder eine weitere Punktgruppe hinzu:  **Bei gedrückter Strg** -Taste  **** klicken oder bei  **Strg** + über mehrere Punkte  **** ziehen.

   * **So entfernen Sie einen Punkt oder eine Punktgruppe aus Ihrer Auswahl**:  **Umschalttaste** +  **** Klicken auf Punkt oder  **Umschalttaste** **+** **** Ziehen über mehrere Punkte.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
