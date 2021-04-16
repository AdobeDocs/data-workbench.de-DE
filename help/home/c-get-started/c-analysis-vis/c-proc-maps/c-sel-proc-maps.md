---
description: Sie können in Prozesszuordnungen eine Auswahl treffen, um Filter zu erstellen, die mit einer bestimmten Node verknüpfte Daten ein- oder ausschließen.
title: Auswahl von Elementen aus Prozesskarten
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Auswahl von Elementen aus Prozesskarten{#make-a-selection-from-a-process-map}

Sie können in Prozesszuordnungen eine Auswahl treffen, um Filter zu erstellen, die mit einer bestimmten Node verknüpfte Daten ein- oder ausschließen.

Eine Auswahl innerhalb einer Prozesszuordnung erfolgt über die Gruppendimension der Map, die bestimmt, wie die Elemente der Basisdimension (d. h. die Knoten in Ihrer Map) gruppiert werden, um die Verbindungen zwischen Knoten zu bilden.

>[!NOTE]
>
>Sie können die standardmäßige Gruppendimension für eine Prozesszuordnung ändern. Siehe [Prozesszuordnungen konfigurieren](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

Wenn Sie eine Auswahl basierend auf einer Node in einer Prozesszuordnung treffen, wählen Sie alle Elemente der Gruppendimension aus, an der diese Node beteiligt war. Um die Rolle der Gruppendimension besser zu verstehen, sollten Sie die folgenden Beispiele beachten:

* Filme können von den Viewern gruppiert werden, die sie bewertet haben. Jeder Viewer ist ein Element der User-Dimension. Daher ist die User-Dimension die Gruppendimension für die Prozesszuordnung. Wenn Sie eine Auswahl aus einem Knoten für einen bestimmten Film treffen, erstellen Sie einen Filter, der Daten zu den Benutzern anzeigt, die den Film bewertet haben oder nicht.
* Webseiten können nach Sitzungen gruppiert werden, in denen sie angezeigt wurden. Jede Sitzung ist ein Element der Sitzungsdimension. Daher wäre die Sitzungsdimension die Gruppendimension für die Prozesszuordnung. Wenn Sie eine Auswahl aus einer Node für eine bestimmte Seite treffen, erstellen Sie einen Filter, der Daten zu den Sitzungen anzeigt, während denen diese Seite angezeigt wurde oder nicht.

**So treffen Sie eine Auswahl**

1. Klicken Sie mit der rechten Maustaste auf einen beliebigen Knoten in einer Prozesszuordnung.
1. Klicken Sie auf eine der folgenden Optionen, um eine Auswahl basierend auf der Node vorzunehmen:

   * **[!UICONTROL Select]***  **[!UICONTROL group dimension name +s]***  **[!UICONTROL through node name]**: Filter der Daten, um alle Elemente der Gruppendimension einzuschließen, die durch den Knoten weitergegeben wurden, indem alle Sitzungen herausgefiltert werden, die nicht durch den Knoten weitergereicht wurden.

   * **[!UICONTROL Select]***  **[!UICONTROL group dimension name +s]***  **[!UICONTROL NOT through node name]**: Filter der Daten, um alle Elemente der Gruppendimension einzuschließen, die nicht durch den Knoten hindurch gegangen sind, indem alle Sitzungen, die über den Knoten weitergereicht wurden, herausgefiltert werden.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Wenn Sie eine Auswahl in einer 3D-Prozesszuordnung vornehmen, wird der Knoten, für den die Auswahl getroffen wird, umkreist. Anhand von Benchmarks können Sie die einzelnen Balken miteinander vergleichen, um die Metrikwerte mit und ohne Auswahl zu vergleichen. Siehe [Grundlegendes zu Benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)
