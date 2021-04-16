---
description: Die Visualisierung der Dichtezuordnung zeigt Elemente als schattierte Rechtecke innerhalb einer Quadratkarte an.
title: Dichtekarte
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# Dichtekarte{#density-map}

Die Visualisierung der Dichtezuordnung zeigt Elemente als schattierte Rechtecke innerhalb einer Quadratkarte an.

Die Größe der Rechtecke hängt von den Elementwerten ab, wobei größere Werte durch Rechtecke mit größerem Bereich dargestellt werden. Ähnlich wie bei einem Kreisdiagramm können Sie mit dieser Visualisierung schnell erkennen, welche Elemente den größten Prozentsatz der ausgewählten Dimension ausmachen.

![](assets/density_map_day_visits.png)

So erstellen Sie eine Dichtezuordnung:

1. Öffnen Sie eine neue Arbeitsfläche.

   Nach dem Öffnen eines neuen Arbeitsbereichs müssen Sie möglicherweise auf **Hinzufügen** > **Vorübergehend entsperren** klicken.
1. Klicken Sie auf **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Wählen Sie eine **[!UICONTROL Dimension]** aus dem Menü.

   Wählen Sie beispielsweise **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   Wenn Sie dagegen **[!UICONTROL Time]** > **[!UICONTROL Hours]** wählen, erhalten Sie mehr Elemente mit kleineren Werten, die als kleinere Rechtecke angezeigt werden.

   >[!NOTE]
   >
   >Sie möchten eine Dimension mit mehreren Elementen je nach Bedarf auswählen. Die aktuelle Grenze beträgt 200 der größten Elemente für jede Dimension.

1. Sie können Ansichten Dimensionsänderung werden, indem Sie **[!UICONTROL Visualization]** > **[!UICONTROL Table]** öffnen und über mehrere Elemente der Tabelle zur Anzeige in der Map auswählen.

   ![](assets/density_map_day_selections.png)

   Die Map reagiert auf Auswahlen aus der Tabelle.

1. Wenn Sie den Mauszeiger über kleine Elemente bewegen, werden deren Name und Wert in Text neben dem Mauszeiger angezeigt.
1. Maskieren Sie Elemente, indem Sie mit der rechten Maustaste klicken und **[!UICONTROL Mask]** auswählen und dann eine Option auswählen.

   ![](assets/density_map_day_mask.png)

   Um alle maskierten Knoten anzuzeigen, wählen Sie **[!UICONTROL Unhide All]**.

1. Spotlight-Elemente durch Klicken mit der rechten Maustaste und Auswählen von **[!UICONTROL Spotlight]** und wählen Sie dann eine Option. Mit der Spotlight-Funktion können Sie Elemente in einem Bereich markieren und abdunkeln.
1. hinzufügen eine Farblegende an den Arbeitsbereich. Sie können Werte in der Zuordnung mithilfe der Farblegende identifizieren.

   Sie können der Arbeitsfläche eine Farblegende hinzufügen, und die Knoten ändern die Farbe je nach der zusätzlichen Datendimension.
1. Ändern Sie die Dimension oder Metrik, indem Sie mit der rechten Maustaste auf den Map-Titel klicken und aus dem Menü wählen.

   ![](assets/density_map_change_dim.png)

1. hinzufügen Aufrufe durch Rechtsklicken auf eine Zelle und Auswahl von **[!UICONTROL Add Callout]**. Sie können aus dem Menü verschiedene Typen oder Visualisierungen auswählen.

   ![](assets/density_map_callout.png)

1. Wie bei allen Visualisierungen können Sie mit der rechten Maustaste über die Titelleiste klicken, um einfache Befehle zum Schließen, Speichern, Exportieren nach Microsoft Excel, Bestellen, Kopieren, Minimieren und Richten ohne Rand anzuzeigen, um eine Visualisierung ohne Rand anzuzeigen.

   ![](assets/density_map_export.png)

1. Mithilfe der Dichtezuordnung können Sie mehrere Elemente ähnlich wie andere Visualisierungen auswählen und deaktivieren:

* Klicken Sie mit der linken Maustaste, um ein Element auszuwählen.
* Strg+Klicken, um mehrere Elemente auszuwählen.
* Halten Sie die Umschalttaste gedrückt, um die Auswahl eines Elements aufzuheben.
* Klicken Sie mit der rechten Maustaste auf die ausgewählten Elemente, um ein Menü zu öffnen. Wählen Sie dann **[!UICONTROL Deselect]** oder **[!UICONTROL Deselect All]** aus, um die ausgewählten Elemente zu löschen.

## Weitere Optionen {#section-d77defb012424de4a7ced8e5c93115bc}

Klicken Sie mit der rechten Maustaste auf die Dichtezuordnung, um ein Menü mit den folgenden Optionen zu öffnen:

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
   <td colname="col2">hinzufügen Sie einen Text oder eine Grafik als Callout in der Visualisierung, um ein Element weiter zu identifizieren oder zu beschreiben. <p>Sie können auch eine leere Metriklegende, Tabelle, Liniendiagramm oder Streudiagramm basierend auf dem ausgewählten Element in der Dichtezuordnung auswählen. Anschließend können Sie diesen leeren Visualisierungen nach Bedarf Metriken und Dimensionen hinzufügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maske </td> 
   <td colname="col2">Mit den Maskierungsoptionen können Sie ausgewählte Elemente ausblenden. Klicken Sie mit der rechten Maustaste, um die Maskenoptionen anzuzeigen. <p><span class="uicontrol"> Dieses Element</span> ausblenden: Wählen Sie diese Option, um ein ausgewähltes Element zu maskieren. </p> <p><span class="uicontrol"> Ausgewählte</span> Elemente ausblenden: Wählen Sie diese Option, um mehrere ausgewählte Elemente zu maskieren. </p> <p><span class="uicontrol"> Oben</span> anzeigen— Wählen Sie diese Option, um basierend auf den Werten in der Dichtezuordnung nur die obersten 100-, 50-, 25- oder 10-Elemente anzuzeigen. </p> <p><span class="uicontrol"> Unten</span> anzeigen: Wählen Sie diese Option, um basierend auf den Werten in der Dichtezuordnung nur die unteren Elemente 100, 50, 25 oder 10 anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spotlight </td> 
   <td colname="col2"> Mit der Spotlight-Funktion können Sie Elemente in einem Bereich markieren und abdunkeln. Klicken Sie mit der rechten Maustaste, um ein Menü mit Optionen zu öffnen. <p><span class="uicontrol"> Oben</span> anzeigen— Wählen Sie diese Option, um nur die obersten 100-, 50-, 25- oder 10-Elemente zu markieren, die auf den Werten in der Dichtezuordnung basieren. </p> <p><span class="uicontrol"> Unten</span> anzeigen: Wählen Sie diese Option, um nur die untersten 100-, 50-, 25- oder 10 obersten Elemente basierend auf den Werten in der Dichtezuordnung zu markieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Auswahl aufheben </p> <p>Auswahl aufheben </p> </td> 
   <td colname="col2"> <p> Wählen Sie diese Befehle aus, um die Auswahl des aktuellen Elements aufzuheben oder die Auswahl aller ausgewählten Elemente aufzuheben. </p> </td> 
  </tr> 
 </tbody> 
</table>
