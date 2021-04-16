---
description: Schritte, um jede Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
title: Verfügbar machen von neuen Vektorebenen
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Verfügbar machen von neuen Vektorebenen{#make-a-new-vector-layer-available}

Schritte, um jede Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Legen Sie im Ordner &quot;Profils\*Profil name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die [!DNL .vec]- oder [!DNL .tsv]-Dateien ab.
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner &quot;Profils\*Profil*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie unter [Menüs mithilfe von order.txt-Dateien anpassen](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. Wählen Sie in Insight das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und dann auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben &quot;Online arbeiten&quot;wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
