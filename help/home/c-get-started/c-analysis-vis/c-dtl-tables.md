---
description: Mithilfe von Detailtabellen können Sie zusätzliche Informationen zu einer Teilmenge von Daten anzeigen, die durch die Auswahlen definiert wird, die Sie in anderen Visualisierungen vornehmen.
title: Detailtabelle
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
exl-id: d7f0b768-f341-41e8-904b-ec98a25f7aa9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# Detailtabelle{#detail-table}

{{eol}}

Mithilfe von Detailtabellen können Sie zusätzliche Informationen zu einer Teilmenge von Daten anzeigen, die durch die Auswahlen definiert wird, die Sie in anderen Visualisierungen vornehmen.

Die zusätzlichen Informationen, die Sie sehen, sind eine Stichprobe aller verfügbaren Daten.

![](assets/vis_details.png)

In der folgenden Tabelle werden die Elemente einer Detailtabelle beschrieben.

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
   <td colname="col2"> <p>Jede zählbare Dimension, für die Sie detaillierte Attribut- und Metrikinformationen anzeigen möchten. Der Ebene wird die Anzahl der von der Anzahl der verfügbaren Elemente angezeigten Elemente vorangestellt. Beispielsweise gibt 6/444 an, dass von einem möglichen 444 6 Elemente angezeigt werden. Im obigen Beispiel zeigt die Ebene Besucher an, dass alle angegebenen Details auf dem Besucher basieren. Die Ebene "Seitenansichten"zeigt an, dass alle bereitgestellten Details auf der Seitenansicht basieren. Die gleichzeitige Anzeige mehrerer Ebenen ist nützlich, wenn Sie Daten mit unterschiedlichen zählbaren übergeordneten Elementen analysieren möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribut </p> </td> 
   <td colname="col02"> <p>Grün </p> </td> 
   <td colname="col2"> <p>Jede Dimension, bei der es sich um eine Eins-zu-viele- oder Eins-zu-Eins-Dimension mit der Ebene handelt, z. B. Stadt bis Besucher. Jede Zeile zeigt das Element an, das zu jedem Element der ausgewählten Ebene gehört. Im obigen Beispiel führen die Attribute Domäne und Stadt die Domäne und den Ort für jeden Beispielbesucher auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik </p> </td> 
   <td colname="col02"> <p>Blau </p> </td> 
   <td colname="col2"> <p>Metrikdetails zur ausgewählten Ebene. Im obigen Beispiel zeigt die Metrik "Seitenansichten"mit der auf "Besucher"festgelegten Ebene die Anzahl der Seitenansichten für einen einzelnen Besucher an, während die Ebene "Seitenansichten"die Details zu den einzelnen Seitenansichten anzeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

Angenommen, Sie arbeiten mit Website-Daten und möchten herausfinden, welche Seiten Besucher in bestimmten Städten und von bestimmten Domänen während eines bestimmten Zeitraums besucht haben.

Erstellen Sie zunächst eine Visualisierung, die den Zeitrahmen anzeigt, an dem Sie interessiert sind, und wählen Sie dann diesen Zeitrahmen aus. Jetzt können Sie eine Detailtabelle hinzufügen, um die gewünschten Details für eine Beispielanzahl von Besuchern im Datensatz anzuzeigen.

Um die oben beschriebenen Details anzuzeigen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Visitors]** Ebenenüberschrift und -klick **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Besucherebene und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Besucherebene und klicken Sie auf **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Klicken Sie mit der rechten Maustaste auf die Überschrift auf Seitenansichten und klicken Sie auf **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

Der folgende Beispielarbeitsbereich zeigt die zugehörigen Details für eine zufällige Auswahl von sechs Besuchern der Site während des von Ihnen festgelegten Zeitraums.

![](assets/client-tab1.png)

## Ebene hinzufügen {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Klicken Sie mit der rechten Maustaste in die Detailtabelle und klicken Sie auf **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_AddLevel.png)

## Entfernen einer Ebene {#section-a8c820e0b656451e98e5ea75373edefc}

* Klicken Sie mit der rechten Maustaste auf die Überschrift der vorhandenen Ebene und klicken Sie auf **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_Level.png)

## Hinzufügen von Attributen und Metriken {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Klicken Sie mit der rechten Maustaste auf eine Überschrift für ein Attribut oder eine Metrik und klicken Sie auf **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]**>* oder **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Entfernen von Attributen und Metriken {#section-4002ac957a2846678f9940270987d651}

* Klicken Sie mit der rechten Maustaste auf die Spalte, die Sie entfernen möchten, und klicken Sie auf **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>* oder **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Exportieren in Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Informationen zum Exportieren von Fenstern finden Sie unter [Exportieren von Fensterdaten](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
