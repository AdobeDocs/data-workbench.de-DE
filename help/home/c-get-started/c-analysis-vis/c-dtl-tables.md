---
description: Mithilfe von Detailtabellen können Sie zusätzliche Informationen zu einer Untergruppe von Daten Ansicht haben, die durch die Auswahl definiert werden, die Sie in anderen Visualisierungen vornehmen.
title: Detailtabelle
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
exl-id: d7f0b768-f341-41e8-904b-ec98a25f7aa9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# Detailtabelle{#detail-table}

Mithilfe von Detailtabellen können Sie zusätzliche Informationen zu einer Untergruppe von Daten Ansicht haben, die durch die Auswahl definiert werden, die Sie in anderen Visualisierungen vornehmen.

Die zusätzlichen Informationen, die Sie sehen, sind eine Stichprobe aller verfügbaren Daten.

![](assets/vis_details.png)

Die folgende Tabelle beschreibt die Elemente einer Detailtabelle.

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col02" class="entry"> Farbe </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ebene </p> </td> 
   <td colname="col02"> <p>Rosa </p> </td> 
   <td colname="col2"> <p>Jede zählbare Dimension, für die detaillierte Attribut- und Metrikinformationen Ansicht werden sollen. Der Ebene wird die Anzahl der Elemente vorangestellt, die aus der Anzahl der verfügbaren Elemente hervorgegangen sind. Beispielsweise zeigt 6/444 an, dass von möglichen 444 6 Elemente angezeigt werden. Im obigen Beispiel weisen die Besucher der Ebene darauf hin, dass alle angegebenen Details auf dem Besucher basieren. Die Ansichten auf Seitenniveau weisen darauf hin, dass alle bereitgestellten Details auf der Ansicht der Seite basieren. Die gleichzeitige Ansicht mehrerer Ebenen ist nützlich, wenn Sie Daten mit unterschiedlichen zählbaren übergeordneten Elementen analysieren möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut </p> </td> 
   <td colname="col02"> <p>Grün </p> </td> 
   <td colname="col2"> <p>Jede Dimension, die ein- oder eins-zu-eins mit der Ebene ist, z. B. Stadt zu Besuchern. Jede Zeile zeigt das Element an, das mit jedem Element der ausgewählten Ebene in Beziehung steht. Im obigen Beispiel werden die Domäne und der Ort für jeden der Besucher mit der Liste der Domäne und des Ortes verknüpft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik </p> </td> 
   <td colname="col02"> <p>Blau </p> </td> 
   <td colname="col2"> <p>Metrikdetails zur ausgewählten Ebene. Im obigen Beispiel zeigt die Metrik "Seiten"-Ansichten, bei der die Ebene auf "Besucher"gesetzt ist, die Anzahl der Ansichten für einen einzelnen Besucher an, während die Ebene "Seiten-Ansichten"die Details zu den einzelnen Ansichten anzeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

Angenommen, Sie arbeiten mit Website-Daten und möchten herausfinden, welche Seiten Besucher in bestimmten Städten und von bestimmten Domänen während eines bestimmten Zeitraums besucht haben.

Zuerst müssen Sie eine Visualisierung erstellen, die den Zeitraum anzeigt, in dem Sie interessiert sind, und dann müssen Sie diesen Zeitraum auswählen. Jetzt können Sie eine Detailtabelle zur Ansicht der gewünschten Details für eine Anzahl von Besuchern im Datensatz hinzufügen.

Zur Ansicht der oben beschriebenen Details müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift **[!UICONTROL Visitors]** und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Besucher-Ebene und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Besucher-Ebene und klicken Sie auf **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Seitenebene und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

Der folgende Beispielarbeitsbereich zeigt die zugehörigen Details für eine zufällige Stichprobe von sechs Besuchern zur Site während des angegebenen Zeitraums.

![](assets/client-tab1.png)

## hinzufügen einer Ebene {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]***.

![](assets/mnu_DetailsTable_AddLevel.png)

## Ebene {#section-a8c820e0b656451e98e5ea75373edefc} entfernen

* Klicken Sie mit der rechten Maustaste auf die Überschrift der vorhandenen Ebene und klicken Sie auf **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]***.

![](assets/mnu_DetailsTable_Level.png)

## hinzufügen Attribute und Metriken {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Klicken Sie mit der rechten Maustaste auf ein Attribut oder eine Metrik-Überschrift und klicken Sie auf **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]*** oder **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]***.

![](assets/mnu_DetailsTable.png)

## Attribute und Metriken {#section-4002ac957a2846678f9940270987d651} entfernen

* Klicken Sie mit der rechten Maustaste auf die Spalte, die Sie entfernen möchten, und klicken Sie auf **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]*** oder **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]***.

![](assets/mnu_DetailsTable.png)

## Exportieren in Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
