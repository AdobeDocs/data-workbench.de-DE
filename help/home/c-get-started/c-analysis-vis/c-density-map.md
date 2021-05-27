---
description: Die Visualisierung der Dichtekarte zeigt Elemente als schattierte Rechtecke innerhalb einer Quadratkarte an.
title: Dichtekarte
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# Dichtekarte{#density-map}

Die Visualisierung der Dichtekarte zeigt Elemente als schattierte Rechtecke innerhalb einer Quadratkarte an.

Die Größe der Rechtecke hängt von Elementwerten ab, wobei größere Werte durch Rechtecke mit größerem Bereich dargestellt werden. Ähnlich wie bei einem Tortendiagramm können Sie mit dieser Visualisierung schnell erkennen, welche Elemente den größten Prozentsatz der ausgewählten Dimension ausmachen.

![](assets/density_map_day_visits.png)

So erstellen Sie eine Dichtekarte:

1. Öffnen Sie einen neuen Arbeitsbereich.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehendes Entsperren** klicken.
1. Klicken Sie auf **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Wählen Sie eine **[!UICONTROL Dimension]** aus dem Menü aus.

   Wählen Sie beispielsweise **[!UICONTROL Time]** > **[!UICONTROL Days]** aus.

   Wenn Sie hingegen **[!UICONTROL Time]** > **[!UICONTROL Hours]** auswählen, erhalten Sie mehr Elemente mit kleineren Werten, die als kleinere Rechtecke angezeigt werden.

   >[!NOTE]
   >
   >Sie möchten je nach Bedarf eine Dimension mit mehreren Elementen auswählen. Die aktuelle Begrenzung beträgt 200 der größten Elemente für jede Dimension.

1. Sie können Dimensionsansichten ändern, indem Sie **[!UICONTROL Visualization]** > **[!UICONTROL Table]** öffnen und über Elemente aus der Tabelle hinweg auswählen, die auf der Karte angezeigt werden sollen.

   ![](assets/density_map_day_selections.png)

   Die Zuordnung reagiert auf die in der Tabelle enthaltenen Auswahlmöglichkeiten.

1. Wenn Sie den Mauszeiger über kleine Elemente bewegen, werden deren Name und Wert im Text angezeigt, der in der Nähe des Mauszeigers angezeigt wird.
1. Maskieren Sie Elemente, indem Sie mit der rechten Maustaste klicken und **[!UICONTROL Mask]** auswählen, und wählen Sie dann eine Option aus.

   ![](assets/density_map_day_mask.png)

   Um alle maskierten Knoten anzuzeigen, wählen Sie **[!UICONTROL Unhide All]** aus.

1. Spotlight-Elemente durch Rechtsklick und Auswahl von **[!UICONTROL Spotlight]** und anschließende Auswahl einer Option. Mit der Spotlight-Funktion können Sie Elemente in einem Bereich markieren und abdunkeln.
1. Fügen Sie dem Arbeitsbereich eine Farblegende hinzu. Sie können Werte in der Zuordnung mithilfe der Farblegende identifizieren.

   Sie können eine Farblegende zum Arbeitsbereich hinzufügen. Die Knoten ändern die Farbe basierend auf der zusätzlichen Datendimension.
1. Ändern Sie die Dimension oder Metrik, indem Sie mit der rechten Maustaste auf den Zuordnungstitel klicken und im Menü auswählen.

   ![](assets/density_map_change_dim.png)

1. Fügen Sie Legenden hinzu, indem Sie mit der rechten Maustaste auf eine Zelle klicken und **[!UICONTROL Add Callout]** auswählen. Sie können aus verschiedenen Typen oder Visualisierungen im Menü auswählen.

   ![](assets/density_map_callout.png)

1. Wie bei allen Visualisierungen können Sie mit der rechten Maustaste über die Titelleiste klicken, um grundlegende Befehle zum Schließen, Speichern, Exportieren nach Microsoft Excel, Sortieren, Kopieren, Minimieren und Ränder zu erhalten und so eine Visualisierung ohne Rahmen anzuzeigen.

   ![](assets/density_map_export.png)

1. Mit der Dichtekarte können Sie mehrere Elemente ähnlich wie andere Visualisierungen auswählen und deren Auswahl aufheben:

* Klicken Sie mit der linken Maustaste, um ein Element auszuwählen.
* Strg + Klicken zur Auswahl mehrerer Elemente
* Halten Sie die Umschalttaste gedrückt, um die Auswahl eines Elements aufzuheben.
* Klicken Sie mit der rechten Maustaste auf die ausgewählten Elemente, um ein Menü zu öffnen. Wählen Sie dann **[!UICONTROL Deselect]** oder **[!UICONTROL Deselect All]** aus, um die ausgewählten Elemente zu löschen.

## Weitere Optionen {#section-d77defb012424de4a7ced8e5c93115bc}

Klicken Sie mit der rechten Maustaste auf die Dichtekarte, um ein Menü mit den folgenden Optionen zu öffnen:

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fügen Sie Callout </td> 
   <td colname="col2">Fügen Sie in der Visualisierung einen Text oder eine Grafik als Callout hinzu, um ein Element weiter zu identifizieren oder zu beschreiben. <p>Sie können auch basierend auf dem ausgewählten Element in der Dichtekarte eine leere Metriklegende, Tabelle, Liniendiagramm oder Streudiagramm auswählen. Anschließend können Sie diesen leeren Visualisierungen nach Bedarf Metriken und Dimensionen hinzufügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskieren </td> 
   <td colname="col2">Mit den Maskierungsoptionen können Sie ausgewählte Elemente ausblenden. Klicken Sie mit der rechten Maustaste, um die Maskenoptionen anzuzeigen. <p><span class="uicontrol"> Dieses Element</span> ausblenden - Wählen Sie diese Option, um ein einzelnes Element, das Sie ausgewählt haben, zu maskieren. </p> <p><span class="uicontrol"> Ausgewählte Elemente ausblenden</span> - Wählen Sie diese Option, um mehrere ausgewählte Elemente zu maskieren. </p> <p><span class="uicontrol"> Oben anzeigen</span> - Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die obersten 100-, 50-, 25- oder 10-Elemente anzuzeigen. </p> <p><span class="uicontrol"> Unten anzeigen</span> - Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die unteren 100-, 50-, 25- oder 10 Top-Elemente anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spotlight </td> 
   <td colname="col2"> Mit der Spotlight-Funktion können Sie Elemente in einem Bereich markieren und abdunkeln. Klicken Sie mit der rechten Maustaste, um ein Optionsmenü zu öffnen. <p><span class="uicontrol"> Oben anzeigen</span> - Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die 100-, 50-, 25- oder 10 obersten Elemente zu markieren. </p> <p><span class="uicontrol"> Unten anzeigen</span> - Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die unteren 100-, 50-, 25- oder 10 Top-Elemente zu markieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Auswahl aufheben </p> <p>Auswahl für alle aufheben </p> </td> 
   <td colname="col2"> <p> Wählen Sie diese Befehle aus, um die Auswahl des aktuellen Elements (falls ausgewählt) aufzuheben oder die Auswahl aller ausgewählten Elemente aufzuheben. </p> </td> 
  </tr> 
 </tbody> 
</table>
