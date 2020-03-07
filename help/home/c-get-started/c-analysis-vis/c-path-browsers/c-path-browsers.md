---
description: Mit einem Pfadbrowser können Sie die Sequenz analysieren, in der auf die Elemente einer bestimmten Dimension zugegriffen wurde.
solution: Analytics
title: Pfadbrowser
topic: Data workbench
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Pfadbrowser{#path-browsers}

Mit einem Pfadbrowser können Sie die Sequenz analysieren, in der auf die Elemente einer bestimmten Dimension zugegriffen wurde.

Sie erstellen einen Pfadbrowser, indem Sie ein Element einer Dimension per Drag &amp; Drop in eine leere Pfadbrowser-Visualisierung ziehen. Das Element, das Sie per Drag &amp; Drop in den Pfadbrowser ziehen, wird zum Stamm des Pfadbrowsers. Der Pfadbrowser zeigt Pfade an, die durch den Stamm verlaufen, sodass Sie die Sequenz der Elemente sehen können, auf die vor und nach dem Stamm zugegriffen wurde.

Der folgende Pfadbrowser zeigt die Sequenz von Filmen, die Betrachter vor und nach dem Rating des Films *The Aviator* bewertet haben, der die Wurzel des Pfadbrowsers ist. Jeder Filmname ist ein Element der Dimension &quot;Film&quot;, das in einem Datensatz definiert ist, der aus Filmdaten besteht, die die Namen der Filme und die Bewertungen der Betrachter dieser Filme enthalten.

![](assets/vis_PathBrowser_Movies.png)

Sie können Pfadbrowser erstellen, um die Sequenz anzuzeigen, in der Elemente einer beliebigen Dimension in Ihrem Datensatz aufgerufen wurden. Wenn Sie beispielsweise mit Website-Daten arbeiten, können Sie einen Pfadbrowser erstellen, der die Sequenz der Webseiten anzeigt, die vor und nach dem Stammordner für jede Sitzung aufgerufen wurden, in der der Stammordner angezeigt wurde, oder für jeden Sitebesucher, der den Stammordner angezeigt hat.

![](assets/vis_PathBrowser_Pages.png)

Jeder Pfadbrowser verfügt über eine zugehörige Basisdimension, Gruppendimension, Ebenendimension und Metrik, die Schlüssel zur Interpretation der im Pfadbrowser angezeigten Daten bereitstellen.

* **Basisdimension:** Wenn Sie ein Stammelement in den Pfadbrowser ziehen und dort ablegen, ziehen Sie ein Element der Basisdimension. Alle anderen Elemente, die in den Pfaden angezeigt werden, sind Elemente der Basisdimension. Sie können die Basisdimension ändern, indem Sie ein Element einer anderen Dimension in den Pfadbrowser ziehen und dort ablegen.
* **Ebene:** Jede Dimension in Ihrem Datensatz hat eine zugehörige Dimension der Ebene (auch als übergeordnetes Element bezeichnet). Die Dimension &quot;level&quot;für Ihren Pfadbrowser sollte mit der Dimension &quot;level&quot;(oder der Dimension &quot;parent&quot;) für die Basisdimension des Pfadbrowsers identisch sein. Die Dimension der Ebene eines Pfadbrowsers ist aus zwei Gründen wichtig:

   * Wenn Sie einem Pfad von einem grundlegenden Dimensionselement zum nächsten folgen, wechseln Sie von einem Dimensionselement auf die nächste Ebene. Angenommen, Sie haben einen Pfadbrowser erstellt, der Seiten einer Website anzeigt. Jede Seite ist ein Element der Dimension &quot;Seite&quot;, und die Dimension &quot;Ebene&quot;für &quot;Seite&quot;ist &quot;Seitenansicht&quot;. Wenn Sie von einer Seite zur nächsten wechseln, wechseln Sie von einer Seitenansicht zur nächsten.
   * Wenn Sie in einem Pfadbrowser einen Pfad mit grundlegenden Dimensionselementen auswählen, wählen Sie Daten für die entsprechenden Elemente der Dimension &quot;Ebene&quot;aus. Die Auswahl enthält immer die Elemente der Dimension &quot;Ebene&quot;, die mit dem Stammordner in Verbindung stehen, und wird durch Hinzufügen weiterer Elemente zum Pfad verfeinert. Wenn Sie beispielsweise einen Pfad von Seiten auswählen, z. B. Stamm > A > B, wählen Sie Daten für die Seitenansichten aus, die mit dem Stamm verknüpft sind, wobei die nächste Seite A und die nächste Seite B ist.

      Informationen zum Auswählen eines Pfades in einem Pfadbrowser finden Sie unter [Auswählen von Pfaden](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Weitere Informationen zu Auswahlen finden Sie unter [Vornehmen von Auswahlen in Visualisierungen](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >Der Pfadbrowser ignoriert die Elemente der Dimension &quot;Ebene&quot;ohne zugehörige grundlegende Dimensionselemente. Diese Situation kann auftreten, wenn Sie einen Pfadbrowser aus einer Prozesszuordnung erstellen. Siehe [Erstellen von Pfadbrowsern](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff).

* **Gruppendimension:** Die Gruppendimension legt fest, wie die Elemente der Ebenendimension gruppiert werden, um die Pfade eines Pfadbrowsers zu bilden. Insbesondere dürfen die Dimensionselemente der Ebene, die mit einem einzelnen Pfad in einem Pfadbrowser verknüpft sind, nicht mehr als ein Element einer Gruppendimension umfassen.

   Um dies zu verstehen, sollten Sie sich ein Beispiel für die Verwendung von Webdaten vorstellen. Angenommen, die Basis-, Ebenen- und Gruppenabmessungen für Ihren Pfadbrowser sind Seiten-, Seiten- bzw. Sitzungsangaben. Ein Pfad im Pfadbrowser zeigt die Seitensequenz A > B > C. Die Gruppendimension (Sitzung) teilt Ihnen mit, dass die Seitenansichten (Elemente der Seitenansichtsdimension), die mit der Seitensequenz A > B > C verbunden sind, während einer einzelnen Sitzung aufgetreten sind. Es ist wichtig zu beachten, dass es möglicherweise mehrere Sitzungen gibt, während denen Seitenansichten für die Seitensequenz A > B > C angezeigt wurden. Daher stellt der Pfad mit der Seitensequenz A > B > C alle einzelnen Sitzungen dar, in denen die Seitenansichten für diese Sequenz auftraten.

* **Metrik**: Die Stärke des Pfads, der zu einem bestimmten Element führt, ist proportional zum Wert der Metrik für dieses Element. Je dicker die Pfade sind, desto größer sind die Metrikwerte als die dünnen Pfade.

Die Beschriftung in der oberen linken Ecke des Pfadbrowsers benennt die Basis- und Gruppendimensionen, die in der Visualisierung dargestellt werden. Der Name der Dimension &quot;level&quot;ist in der Pfadbrowser-Visualisierung nicht sichtbar. Die Beschriftung hat die Form &quot;Sequenz der *Basisabmessungen Name*+s für jeden *Gruppennamen*&quot;. Beispielsweise zeigt die Beschriftungssequenz der Filme für jeden Benutzer an, dass die grundlegende Dimension &quot;Film&quot;und die Gruppendimension &quot;Benutzer&quot;ist.

![](assets/vis_PathBrowser_Movies.png)

Wenn Sie mit der rechten Maustaste auf ein Element im Pfadbrowser klicken, können Sie den Namen der mit dem Pfadbrowser verknüpften Metrik und den zugehörigen Wert für dieses Element anzeigen.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Sie können die Standardmaße und -metrik für einen Pfadbrowser ändern. Anweisungen zum Konfigurieren einer Pfadbrowser-Visualisierung finden Sie unter Pfadbrowser [konfigurieren](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

