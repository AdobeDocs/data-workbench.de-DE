---
description: Die Visualisierung der Dichtekarte zeigt Elemente als schattierte Rechtecke innerhalb einer Quadratkarte an.
title: Dichtekarte
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# Dichtekarte{#density-map}

{{eol}}

Die Visualisierung der Dichtekarte zeigt Elemente als schattierte Rechtecke innerhalb einer Quadratkarte an.

Die Größe der Rechtecke hängt von Elementwerten ab, wobei größere Werte durch Rechtecke mit größerem Bereich dargestellt werden. Ähnlich wie bei einem Tortendiagramm können Sie mit dieser Visualisierung schnell erkennen, welche Elemente den größten Prozentsatz der ausgewählten Dimension ausmachen.

![](assets/density_map_day_visits.png)

So erstellen Sie eine Dichtekarte:

1. Öffnen Sie einen neuen Arbeitsbereich.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehendes Entsperren**.
1. Klicken Sie auf **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Wählen Sie eine **[!UICONTROL Dimension]** aus dem Menü.

   Wählen Sie beispielsweise **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   Im Gegensatz dazu können Sie **[!UICONTROL Time]** > **[!UICONTROL Hours]** erhalten Sie mehr Elemente mit kleineren Werten, die als kleinere Rechtecke angezeigt werden.

   >[!NOTE]
   >
   >Sie möchten je nach Bedarf eine Dimension mit mehreren Elementen auswählen. Die aktuelle Begrenzung beträgt 200 der größten Elemente für jede Dimension.

1. Sie können Dimensionsansichten ändern, indem Sie **[!UICONTROL Visualization]** > **[!UICONTROL Table]** und die Auswahl über Elemente aus der Tabelle hinweg, die in der Zuordnung angezeigt werden sollen.

   ![](assets/density_map_day_selections.png)

   Die Zuordnung reagiert auf die in der Tabelle enthaltenen Auswahlmöglichkeiten.

1. Wenn Sie den Mauszeiger über kleine Elemente bewegen, werden deren Name und Wert im Text angezeigt, der in der Nähe des Mauszeigers angezeigt wird.
1. Elemente durch Rechtsklick und Auswahl maskieren **[!UICONTROL Mask]** und wählen Sie dann eine Option aus.

   ![](assets/density_map_day_mask.png)

   Um alle maskierten Knoten anzuzeigen, wählen Sie **[!UICONTROL Unhide All]**.

1. Spotlight-Elemente durch Rechtsklick und Auswahl **[!UICONTROL Spotlight]** und wählen Sie dann eine Option aus. Mit der Spotlight-Funktion können Sie Elemente in einem Bereich markieren und abdunkeln.
1. Fügen Sie dem Arbeitsbereich eine Farblegende hinzu. Sie können Werte in der Zuordnung mithilfe der Farblegende identifizieren.

   Sie können eine Farblegende zum Arbeitsbereich hinzufügen. Die Knoten ändern die Farbe basierend auf der zusätzlichen Datendimension.
1. Ändern Sie die Dimension oder Metrik, indem Sie mit der rechten Maustaste auf den Zuordnungstitel klicken und im Menü auswählen.

   ![](assets/density_map_change_dim.png)

1. Hinzufügen von Hinweisen durch Rechtsklicken auf eine Zelle und Auswählen **[!UICONTROL Add Callout]**. Sie können aus verschiedenen Typen oder Visualisierungen im Menü auswählen.

   ![](assets/density_map_callout.png)

1. Wie bei allen Visualisierungen können Sie mit der rechten Maustaste über die Titelleiste klicken, um grundlegende Befehle zum Schließen, Speichern, Exportieren in Microsoft Excel, Sortieren, Kopieren, Minimieren und Ränder zu erhalten und so eine Visualisierung ohne Rahmen anzuzeigen.

   ![](assets/density_map_export.png)

1. Mit der Dichtekarte können Sie mehrere Elemente ähnlich wie andere Visualisierungen auswählen und deren Auswahl aufheben:

* Klicken Sie mit der linken Maustaste, um ein Element auszuwählen.
* Strg + Klicken zur Auswahl mehrerer Elemente
* Halten Sie die Umschalttaste gedrückt, um die Auswahl eines Elements aufzuheben.
* Klicken Sie mit der rechten Maustaste auf die ausgewählten Elemente, um ein Menü zu öffnen. Dann wählen Sie **[!UICONTROL Deselect]** oder **[!UICONTROL Deselect All]** um ausgewählte Elemente zu löschen.

## Zusätzliche Optionen {#section-d77defb012424de4a7ced8e5c93115bc}

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
   <td colname="col1"> Hinzufügen Callout </td> 
   <td colname="col2">Fügen Sie in der Visualisierung einen Text oder eine Grafik als Callout hinzu, um ein Element weiter zu identifizieren oder zu beschreiben. <p>Sie können auch basierend auf dem ausgewählten Element in der Dichtekarte eine leere Metrik-Legende, Tabelle, Liniendiagramm oder Streudiagramm auswählen. Anschließend können Sie diesen leeren Visualisierungen nach Bedarf Metriken und Dimensionen hinzufügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskieren </td> 
   <td colname="col2">Mit den Maskierungsoptionen können Sie ausgewählte Elemente ausblenden. Klicken Sie mit der rechten Maustaste, um die Maskenoptionen anzuzeigen. <p><span class="uicontrol"> Dieses Element ausblenden</span>—Wählen Sie diese Option, um ein einzelnes Element, das Sie ausgewählt haben, zu maskieren. </p> <p><span class="uicontrol"> Ausgewählte Elemente ausblenden</span>—Wählen Sie diese Option, um mehrere ausgewählte Elemente zu maskieren. </p> <p><span class="uicontrol"> Oben anzeigen</span>— Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die Top-100-, 50-, 25- oder 10-Elemente anzuzeigen. </p> <p><span class="uicontrol"> Unten anzeigen</span>—Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die unteren 100-, 50-, 25- oder 10 Top-Elemente anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spotlight </td> 
   <td colname="col2"> Mit der Spotlight-Funktion können Sie Elemente in einem Bereich markieren und abdunkeln. Klicken Sie mit der rechten Maustaste, um ein Optionsmenü zu öffnen. <p><span class="uicontrol"> Oben anzeigen</span>— Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die 100, 50, 25 oder 10 obersten Elemente hervorzuheben. </p> <p><span class="uicontrol"> Unten anzeigen</span>—Wählen Sie diese Option, um basierend auf den Werten in der Dichtekarte nur die unteren 100-, 50-, 25- oder 10 Top-Elemente hervorzuheben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Auswahl aufheben </p> <p>Auswahl für alle aufheben </p> </td> 
   <td colname="col2"> <p> Wählen Sie diese Befehle aus, um die Auswahl des aktuellen Elements (falls ausgewählt) aufzuheben oder die Auswahl aller ausgewählten Elemente aufzuheben. </p> </td> 
  </tr> 
 </tbody> 
</table>
