---
description: Mithilfe von Detailtabellen können Sie zusätzliche Informationen zu einer Untergruppe von Daten anzeigen, die durch die Auswahlen definiert sind, die Sie in anderen Visualisierungen vornehmen.
solution: Analytics
title: Detailtabelle
topic: Data workbench
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Detail table{#detail-table}

Mithilfe von Detailtabellen können Sie zusätzliche Informationen zu einer Untergruppe von Daten anzeigen, die durch die Auswahlen definiert sind, die Sie in anderen Visualisierungen vornehmen.

Die zusätzlichen Informationen, die Sie sehen, sind eine Stichprobe aller verfügbaren Daten.

![](assets/vis_details.png)

Die folgende Tabelle beschreibt die Elemente einer Detailtabelle.

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col02" class="entry"> Kanalfarbe </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ebene </p> </td> 
   <td colname="col02"> <p>Rosa </p> </td> 
   <td colname="col2"> <p>Jede zählbare Dimension, für die Sie detaillierte Attribut- und Metrikinformationen anzeigen möchten. Der Ebene wird die Anzahl der Elemente vorangestellt, die aus der Anzahl der verfügbaren Elemente hervorgegangen sind. Beispielsweise zeigt 6/444 an, dass von möglichen 444 6 Elemente angezeigt werden. Im obigen Beispiel zeigt die Ebene Besucher an, dass alle bereitgestellten Details auf dem Besucher basieren. Die Ebene "Seitenansichten"gibt an, dass alle angegebenen Details auf der Seitenansicht basieren. Die gleichzeitige Ansicht mehrerer Ebenen ist nützlich, wenn Sie Daten mit unterschiedlichen zählbaren übergeordneten Elementen analysieren möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut </p> </td> 
   <td colname="col02"> <p>Grün </p> </td> 
   <td colname="col2"> <p>Jede Dimension, die ein- oder eins-zu-eins mit der Ebene ist, z. B. "Stadt zu Besucher". Jede Zeile zeigt das Element an, das mit jedem Element der ausgewählten Ebene in Beziehung steht. Im obigen Beispiel führen die Attribute "Domäne"und "Stadt"die Domäne und den Ort für jeden der Beispielbesucher auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik </p> </td> 
   <td colname="col02"> <p>Blau </p> </td> 
   <td colname="col2"> <p>Metrikdetails zur ausgewählten Ebene. Im obigen Beispiel zeigt die Metrik "Seitenansichten"mit der Einstellung "Besucher"die Anzahl der Seitenansichten eines einzelnen Besuchers an, während die Ebene "Seitenansichten"die Details zu den einzelnen Seitenansichten anzeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

Nehmen wir an, Sie arbeiten mit Website-Daten und möchten herausfinden, welche Seiten Besucher in bestimmten Städten und aus bestimmten Domänen während eines bestimmten Zeitraums besucht haben.

Zuerst müssen Sie eine Visualisierung erstellen, die den Zeitraum anzeigt, in dem Sie interessiert sind, und dann müssen Sie diesen Zeitraum auswählen. Jetzt können Sie eine Detailtabelle hinzufügen, um die gewünschten Details für eine Beispielanzahl von Besuchern im Datensatz anzuzeigen.

Um die oben beschriebenen Details anzuzeigen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift der **[!UICONTROL Visitors]** Ebene und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Besucherebene und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Besucherebene und klicken Sie auf **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift Seitenansichten und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

Der folgende Beispielarbeitsbereich zeigt die zugehörigen Details für eine zufällige Stichprobe von sechs Besuchern der Site während des von Ihnen angegebenen Zeitraums.

![](assets/client-tab1.png)

## Ebene hinzufügen {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_AddLevel.png)

## Ebene entfernen {#section-a8c820e0b656451e98e5ea75373edefc}

* Klicken Sie mit der rechten Maustaste auf die Überschrift der vorhandenen Ebene und klicken Sie auf **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_Level.png)

## Add attributes and metrics {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Klicken Sie mit der rechten Maustaste auf ein Attribut oder eine Metrik-Überschrift und klicken Sie auf **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]**>* oder **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Attribute und Metriken entfernen {#section-4002ac957a2846678f9940270987d651}

* Klicken Sie mit der rechten Maustaste auf die zu entfernende Spalte und klicken Sie auf **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>* oder **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Nach Microsoft Excel exportieren {#section-a9eaba63c88a4598836a34669ba8cac1}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
