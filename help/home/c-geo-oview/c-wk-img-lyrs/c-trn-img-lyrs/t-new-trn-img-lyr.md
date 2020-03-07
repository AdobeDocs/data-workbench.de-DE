---
description: Schritte, um eine neue Geländeschicht zur Anzeige auf der globalen Visualisierung verfügbar zu machen.
solution: Analytics
title: Bereitstellen einer neuen Terrain-Bildebene
topic: Data workbench
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bereitstellen einer neuen Terrain-Bildebene{#making-a-new-terrain-image-layer-available}

Schritte, um eine neue Geländeschicht zur Anzeige auf der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profiles\*profile name*\Maps&quot;im **[!UICONTROL Insight Server]** Installationsordner die Ebenendatei und die zugehörigen Bilddateien.
1. Bearbeiten Sie die [!DNL order.txt] Datei im Ordner &quot;Profile\*Profilname*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der [!DNL order.txt] Datei darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt] Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuchs*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>* klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben [!DNL Work Online].
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
