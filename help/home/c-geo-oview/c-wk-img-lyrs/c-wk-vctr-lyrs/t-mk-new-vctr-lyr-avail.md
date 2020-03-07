---
description: Schritte, um eine Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
solution: Analytics
title: Verfügbarmachen einer neuen Vektorebene
topic: Data workbench
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verfügbarmachen einer neuen Vektorebene{#making-a-new-vector-layer-available}

Schritte, um eine Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profiles\*profile name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die [!DNL .vec] bzw. die [!DNL .tsv] Dateien.
1. Bearbeiten Sie die [!DNL order.txt] Datei im Ordner &quot;Profile\*Profilname*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der [!DNL order.txt] Datei darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt] Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuchs*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>* klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben [!DNL Work Online].
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
