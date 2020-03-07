---
description: Die Trichtervisualisierung umfasst Funktionen zum Aufbau eines Trichters mit mehreren Dimensionen, rohen Besucherzahlen, prozentualen Besucherzahlen bei jedem Schritt und separaten Bereichen.
solution: Analytics
title: Trichterfunktionen
topic: Data workbench
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trichterfunktionen{#funnel-features}

Die Trichtervisualisierung umfasst Funktionen zum Aufbau eines Trichters mit mehreren Dimensionen, rohen Besucherzahlen, prozentualen Besucherzahlen bei jedem Schritt und separaten Bereichen.

Hier sind die grundlegenden Funktionen der Trichtervisualisierung.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Erstes Element </td> 
   <td colname="col2"> Erster Trichterschritt im Prozess. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Drittes Element </td> 
   <td colname="col2">Dritter Trichterschritt im Prozess. <p><p>Hinweis:  Die ausgewählten Elemente müssen nicht aus derselben Dimension stammen. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Durchbruchprozentsatz </td> 
   <td colname="col2"> Prozentsatz, der den definierten Pfad abgeschlossen hat, wird in drei Bereichen angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Trichteranalyse-Browser </td> 
   <td colname="col2">Trichteranalysepfeil. Klicken Sie mit der rechten Maustaste und wählen Sie <span class="uicontrol"> Pfadbrowser</span> hinzufügen, um zu sehen, welchen Pfad Besucher eingeschlagen haben. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Prozent-Trichteranalyse </td> 
   <td colname="col2">Prozentsätze, die drei Bereiche des vorzeitigen Ausschnitts für Benutzer beschreiben, die den Pfad nicht abgeschlossen haben. <p>Die Prozentsätze werden in drei Bereichen dargestellt: </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> Der Prozentsatz der vorzeitigen Trichteranalyse. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> Der Prozentsatz der Trichteranalyse aus dem ersten Schritt im Trichter. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> Der Prozentsatz der vorzeitigen Ausstiege basierend auf der Gesamtanzahl der Besucher. </p></td> 
  </tr> 
 </tbody> 
</table>

## Trichterschritte {#section-96a6732558dd4740b73541844f06d3ef}

Die Scheiben in einem Trichter stellen die Schritte in der Navigation dar, die Keulen stellen den Durchbruch von einem Schritt zum nächsten dar und die Pfeile stellen den Abgang dar. Wenn Sie auf einen Kegel klicken, wählen Sie die Benutzer aus, die an diesem Punkt durchgefallen sind, und fügen Sie sie in den aktuellen Arbeitsflächenfilter ein. Wenn Sie auf einen Pfeil klicken, werden die Besucher ausgewählt, die ausgefallen sind.

>[!NOTE]
>
>Die Trichter-Visualisierung besteht aus acht Schritten, die angewendet werden können.

## Zusätzliche Trichterfunktionen und -funktionen {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Passen Sie den Clip und die Ebene des Trichters** an. Wählen Sie die Option &quot;Trichter&quot;im Menü &quot;Visualisierung&quot;aus. Nachdem der Trichter erstellt wurde, können Sie mit der rechten Maustaste auf den Titel klicken, um den Clip und die Ebene an eine beliebige zählbare Metrik in Ihrem System anzupassen.

   ![](assets/funnel_path_browser_9.png)

* **Ziehen Sie weitere Elemente**. Fügen Sie dem Trichter weitere Elemente hinzu, indem Sie sie per Drag &amp; Drop aus der Dimensionstabelle in den Trichter ziehen und mit den Tasten `<Ctrl>` + `<Alt>` ablegen. Sie können mehrere Schritte gleichzeitig aus der Dimensionstabelle ziehen, indem Sie mehrere Elemente auswählen (mit `<Ctrl>` +Klick) und sie dann mit den `<Ctrl>` +- `<Alt>` Tasten zur Trichtervisualisierung ziehen.
* **Löschen Sie einen Schritt**: Löschen Sie Elemente, indem Sie mit der rechten Maustaste auf den Schritt in der Visualisierung klicken und auf **Ja** klicken.

   ![](assets/funnel_path_browser_4.png)

* **Ordnen Sie die Schritte, die Sie in den Trichter** gezogen haben, neu an. Klicken Sie einfach auf den Schritt, um ihn auszuwählen, und ziehen Sie ihn an eine andere Position, um die Schritte neu anzuordnen.
* **Öffnen Sie einen Pfadbrowser**. Mit der Funktion &quot;Pfadbrowser [hinzufügen&quot;können Sie detailliertere Informationen darüber anzeigen, wo Kunden den Prozess durchlaufen oder verlassen](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) .

* **Fügen Sie weitere Schritte** hinzu. Sie können jeder Trichtervisualisierung maximal acht Schritte hinzufügen.
* **Ändern Sie die Metrik**. Die Metrik kann geändert werden, sodass die Schritte bei jedem Schritt Besuche oder eine andere Metrik zählen. Die verfügbaren Optionen variieren je nach Datensatz.
* **In Tabellenansicht** anzeigen. Klicken Sie mit der rechten Maustaste auf den Titel, um das Menü &quot;Trichtervisualisierung&quot;anzuzeigen, und klicken Sie auf **[!UICONTROL Show Tabular View]**. In der Tabellenansicht können Sie festlegen, dass der Trichter wieder grafisch dargestellt **[!UICONTROL Show Graph View]** werden soll. Um die Tabellenansicht zu öffnen, klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie &quot;Tabellenansicht anzeigen&quot;aus dem Menü.

* **Vergleichen Sie Sequenzen**. Eine effiziente Möglichkeit zum Vergleich zweier ähnlicher Sequenzen besteht darin, ihre beiden Visualisierungen nebeneinander anzuzeigen. Mit der Funktion &quot;Duplizieren&quot;können Sie auch die Tabellenansicht und die Diagrammansicht nebeneinander anzeigen. Klicken Sie zum Öffnen mit der rechten Maustaste auf den Titel und wählen Sie Duplizieren aus dem Menü.
