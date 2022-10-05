---
description: Sie können in Prozesskarten Auswahlen vornehmen, um Filter zu erstellen, die mit einem bestimmten Knoten verknüpfte Daten einschließen oder ausschließen.
title: Auswahl von Elementen aus Prozesskarten
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Auswahl von Elementen aus Prozesskarten{#make-a-selection-from-a-process-map}

{{eol}}

Sie können in Prozesskarten Auswahlen vornehmen, um Filter zu erstellen, die mit einem bestimmten Knoten verknüpfte Daten einschließen oder ausschließen.

Eine Auswahl innerhalb einer Prozesszuordnung erfolgt über die Gruppendimension der Zuordnung, die bestimmt, wie die Elemente der Basisdimension (d. h. die Knoten in Ihrer Zuordnung) gruppiert werden, um die Verbindungen zwischen Knoten zu bilden.

>[!NOTE]
>
>Sie können die standardmäßige Gruppendimension für eine Prozesszuordnung ändern. Siehe [Konfigurieren von Prozesskarten](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

Wenn Sie eine Auswahl basierend auf einem Knoten in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, die diesen Knoten betrifft. Um die Rolle der Gruppendimension besser zu verstehen, sehen Sie sich die folgenden Beispiele an:

* Filme können nach den Betrachtern gruppiert werden, die sie bewertet haben. Jeder Viewer ist ein Element der Dimension Benutzer , sodass die Dimension Benutzer die Gruppendimension für die Prozesszuordnung ist. Wenn Sie eine Auswahl aus einem Knoten für einen bestimmten Film treffen, erstellen Sie einen Filter, der Daten für die Benutzer anzeigt, die diesen Film bewertet haben oder nicht.
* Website-Seiten können nach den Sitzungen gruppiert werden, in denen sie angezeigt wurden. Jede Sitzung ist ein Element der Dimension Sitzung , daher wäre die Dimension Sitzung die Gruppendimension für die Prozesszuordnung. Wenn Sie eine Auswahl aus einem Knoten für eine bestimmte Seite treffen, erstellen Sie einen Filter, der Daten zu den Sitzungen anzeigt, während denen die Seite angezeigt wurde oder nicht.

**So wählen Sie eine Auswahl aus**

1. Klicken Sie mit der rechten Maustaste auf einen beliebigen Knoten in einer Prozesszuordnung.
1. Klicken Sie auf eine der folgenden Optionen, um eine Auswahl basierend auf dem Knoten vorzunehmen:

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**: Filtert die Daten, um alle Elemente der Gruppendimension einzuschließen, die über den Knoten weitergegeben wurden, indem alle Sitzungen herausgefiltert werden, die nicht über den Knoten weitergegeben wurden.

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**: Filtert die Daten, um alle Elemente der Gruppendimension einzuschließen, die nicht durch den Knoten weitergegeben wurden, indem alle Sitzungen herausgefiltert werden, die über den Knoten weitergeleitet wurden.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Wenn Sie eine Auswahl in einer 3D-Prozesskarte treffen, wird der Knoten, für den die Auswahl getroffen wird, umkreist. In jedem Balken werden Benchmarks angezeigt, die Ihnen helfen, Metrikwerte mit und ohne Auswahl zu vergleichen. Siehe [Grundlegendes zu Benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)
