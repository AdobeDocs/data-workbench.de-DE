---
description: Schritte, um eine beliebige Elementpunktebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
solution: Analytics
title: Verfügbarmachen einer neuen Elementpunktebene
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verfügbarmachen einer neuen Elementpunktebene{#make-a-new-element-point-layer-available}

Schritte, um eine beliebige Elementpunktebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profiles\*profile name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die zugehörige Nachschlagedatei.
1. Wenn Sie eine neue Dimension für Ihre Elementpunktebene definiert haben und Ihren Datensatz noch nicht umgestaltet haben, können Sie den Datensatz jetzt neu transformieren.
1. Bearbeiten Sie die [!DNL order.txt] Datei im Ordner &quot;Profile\*Profilname*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der [!DNL order.txt] Datei darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt] Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuchs*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>* klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben &quot;Online arbeiten&quot;wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
