---
description: Ein 3D-Streudiagramm stellt die Elemente einer Datendimension (z. B. Tage oder Referrer-Site) in einem dreidimensionalen Raster dar, in dem die Achsen x, y und z verschiedene Metriken darstellen.
title: 3D-Streudiagramme
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 1%

---

# 3D-Streudiagramme{#d-scatter-plots}

Ein 3D-Streudiagramm stellt die Elemente einer Datendimension (z. B. Tage oder Referrer-Site) in einem dreidimensionalen Raster dar, in dem die Achsen x, y und z verschiedene Metriken darstellen.

Wie das [Streudiagramm 2D](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Scatter_Plots) ist diese Visualisierung nützlich, wenn versucht wird, die Beziehung zwischen einer großen Anzahl unterschiedlicher Elemente zu verstehen, die unterschiedliche Metriken verwenden.

**So verwenden Sie die 3D-Streudiagramm-Visualisierung:**

1. Öffnen Sie einen neuen Arbeitsbereich.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehendes Entsperren** klicken.
1. Klicken Sie mit der rechten Maustaste und wählen Sie **Visualisierung** > **3D-Streudiagramm** aus.

   Daraufhin wird ein Menü mit **[!UICONTROL Dimensions]** geöffnet.

1. Wählen Sie eine Dimension für die Abfrage aus.

   Das 3D-Streudiagramm öffnet die Standardmetriken für diese Dimension.

   ![](assets/3D_main.png)

   Wenn Sie das Menü **[!UICONTROL Days]** auswählen, wird das folgende 3D-Streudiagramm mit diesen Standardmetriken für die folgenden Achsen angezeigt: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** und **[!UICONTROL z=Visits]**.

1. Metriken ändern. Klicken Sie mit der rechten Maustaste auf die Metrikbezeichnung auf der X-, Y- oder Z-Achse und wählen Sie **[!UICONTROL Change Metric]** aus. Wählen Sie dann eine andere Metrik für die ausgewählte Achse aus.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Ziehen Sie eine Metrik in eine der drei Achsenbeschriftungen und legen Sie sie ab, um die ausgewählte Achse in die abgelegte Metrik zu ändern.
   >    * Ziehen Sie eine Metrik an eine andere Stelle in der Visualisierung und legen Sie sie ab, um die Metrik &quot;Radius&quot;für diese Achse zu ändern.
   >    * Ziehen Sie eine Dimension an eine beliebige Stelle in der Visualisierung und legen Sie sie ab, um die Dimension für die Visualisierung zu ändern.


1. Ändern Sie die Radius-Metrik. Klicken Sie mit der rechten Maustaste auf den Titel oben auf der Seite (nach der ausgewählten Dimension benannt) und wählen Sie **[!UICONTROL Change Radius Metric]** aus.

   Die Metrik &quot;Radius&quot;definiert die Größe des gezeichneten Punkts basierend auf der Metrikauswahl. Die relative Position der Punkte ändert sich im Streudiagramm nicht, aber die gezeichneten Punktgrößen innerhalb der Visualisierung werden basierend auf dem Metrikwert erhöht.

   ![](assets/3D_change_radius.png)

1. Verwenden Sie **[!UICONTROL Orthographic Camera]**. Mit dieser Option können Sie die gezeichneten Punkte im Verhältnis zu ihrer wahren Perspektive basierend auf der Radius-Metrik identifizieren, um dreidimensionale Verzerrungen zu vermeiden.

   Wenn das 3D-Streudiagramm zuerst erscheint, wird es in einer dreidimensionalen rotierenden Projektion angezeigt, was zu einer gewissen Verzerrung bei Punkten führt, die näher an der Perspektive platziert werden, oder zu einer virtuellen &quot;Kamera&quot;. (Die Karten, die näher an der Kamera liegen, sind viel größer als die Punkte, die sich weiter von der Kamera entfernen.)

   Um diese Verzerrung der Perspektive zu vermeiden, können Sie die Option **[!UICONTROL Orthographic Camera]** auswählen, indem Sie mit der rechten Maustaste auf den Titel klicken und aus dem Menü auswählen. Auf diese Weise können Sie die dreidimensionalen Objekte in zwei Dimensionen darstellen. Dadurch werden die gezeichneten Punkte als flach dargestellt und die Punkte als relativ zur Radius-Metrik angezeigt, wodurch die dreidimensionalen Versätze verringert werden.

1. Wählen Sie Punkte aus dem Streudiagramm aus.

   * **So entfernen Sie einen Punkt oder eine Punktgruppe**: Klicken Sie auf den Punkt.
   * **So fügen Sie Ihrer Auswahl** einen weiteren Punkt oder eine Punktgruppe hinzu:  **Strg** +  **** Klickpunkt oder  **Strg** +  **** über mehrere Punkte ziehen.

   * **So entfernen Sie einen Punkt oder eine Punktgruppe aus Ihrer Auswahl**:  **Halten Sie die Umschalttaste**  gedrückt und  **** klicken Sie auf einen Punkt oder  **halten Sie** **die Umschalttaste** ****  gedrückt.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
