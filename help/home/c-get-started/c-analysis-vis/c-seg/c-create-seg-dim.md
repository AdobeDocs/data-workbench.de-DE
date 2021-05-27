---
description: Um eine Segmentdimension zu erstellen, wählen Sie zunächst eine Auswahl in einem Arbeitsbereich aus und fügen dann das Segment einer Visualisierung hinzu.
title: Erstellen von Segmentdimensionen
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# Erstellen von Segmentdimensionen{#create-a-segment-dimensions}

Um eine Segmentdimension zu erstellen, wählen Sie zunächst eine Auswahl in einem Arbeitsbereich aus und fügen dann das Segment einer Visualisierung hinzu.

**So erstellen Sie eine Segmentdimension**

1. Fügen Sie dem Arbeitsbereich eine Segmentvisualisierung hinzu. Beispiel:

   ![](assets/vis_Segment.png)

1. Fügen Sie Ihrem Arbeitsbereich Visualisierungen hinzu, die Sie zum Definieren Ihres Segments verwenden möchten, und wählen Sie dann das gewünschte Segment aus, um es zu definieren.
1. Klicken Sie in der Segmentvisualisierung mit der rechten Maustaste auf den Titel des Segments, nach dem das neue Segment hinzugefügt werden soll, und klicken Sie auf **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Um ein neues erstes Segment zu erstellen, klicken Sie mit der rechten Maustaste auf die Bezeichnung **[!UICONTROL Segments]** und dann auf **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   In der Visualisierung wird ein neues Segment (mit dem Namen Neues Segment) angezeigt. Das Segment Sonstige stellt alle Daten dar, die nicht in Ihren definierten Segmenten enthalten sind: Dies ist effektiv der Unterschied zwischen Ihren Datensatzdaten und Ihren Segmentdaten.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Segment und klicken Sie auf **[!UICONTROL Rename Segment]**.
1. Geben Sie einen beschreibenden Namen für Ihr neues Segment in das Namensfeld ein.

   >[!NOTE]
   >
   >Wenn ein Metrikwert, z. B. ein bestimmter Besucher in [!DNL Site], die Kriterien mehrerer Segmente erfüllt, wird der Metrikwert nur in das erste aufgelistete Segment aufgenommen, mit dem er übereinstimmt.

**So speichern Sie die Segmentdimension**

1. Klicken Sie mit der rechten Maustaste auf den Titel Segmente und klicken Sie auf **[!UICONTROL Save Dimension]**. Das Fenster [!DNL Save Dimension As] wird angezeigt. Der standardmäßige Speicherort ist der Ordner &quot;User\*profile name*\Dimension&quot;.
1. Geben Sie im Feld [!DNL File name] einen beschreibenden Namen für die Segmente ein, die Sie als Dimension speichern, und klicken Sie auf **[!UICONTROL Save]**.

Sie können auf die Segmentdimension zugreifen, sobald Sie mit einer Visualisierung arbeiten. Sie können auch Daten exportieren, die mit den Elementen in Ihrer gespeicherten Dimension verknüpft sind, indem Sie die Segmentexportfunktion verwenden.

Weitere Informationen zur Segmentexportfunktion und Anweisungen zum Konfigurieren für Ihre Anforderungen finden Sie unter [Konfigurieren von Segmenten für den Export](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
