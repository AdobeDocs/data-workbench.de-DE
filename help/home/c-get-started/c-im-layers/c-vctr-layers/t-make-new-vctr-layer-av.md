---
description: Schritte, um jede Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
solution: Analytics
title: Verfügbarmachen einer neuen Vektorebene
topic: Data workbench
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verfügbarmachen einer neuen Vektorebene{#make-a-new-vector-layer-available}

Schritte, um jede Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profiles\*profile name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die [!DNL .vec] bzw. die [!DNL .tsv] Dateien.
1. Bearbeiten Sie die [!DNL order.txt] Datei im Ordner &quot;Profile\*Profilname*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der [!DNL order.txt] Datei darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt] Dateien finden Sie unter [Anpassen von Menüs mithilfe von &quot;order.txt&quot;-Dateien](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. Wählen Sie in Insight das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>* klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben &quot;Online arbeiten&quot;wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
