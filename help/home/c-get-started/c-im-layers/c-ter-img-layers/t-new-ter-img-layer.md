---
description: Schritte, um eine beliebige Terrain-Ebene zur Anzeige auf der globalen Visualisierung verfügbar zu machen.
solution: Analytics
title: Neue Terrain-Bildebene verfügbar machen
topic: Data workbench
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Neue Terrain-Bildebene verfügbar machen{#make-a-new-terrain-image-layer-available}

Schritte, um eine beliebige Terrain-Ebene zur Anzeige auf der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profiles\*profile name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die zugehörigen Bilddateien.
1. Bearbeiten Sie die [!DNL order.txt] Datei im Ordner &quot;Profile\*Profilname*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der [!DNL order.txt] Datei darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt] Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuchs*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>* klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben &quot;Online arbeiten&quot;wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
