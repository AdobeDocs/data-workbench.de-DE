---
description: Schritte zum Bereitstellen einer neuen Topografieschicht zur Anzeige auf der globalen Visualisierung.
title: Verfügbar machen von neuen Topografiebildebenen
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# Verfügbar machen von neuen Topografiebildebenen{#making-a-new-terrain-image-layer-available}

{{eol}}

Schritte zum Bereitstellen einer neuen Topografieschicht zur Anzeige auf der globalen Visualisierung.

1. Im Ordner Profile\*profile name*\Maps im Ordner **[!UICONTROL Insight Server]** Installationsverzeichnis, platzieren Sie die Ebenendatei und die zugehörigen Bilddateien.
1. Bearbeiten Sie die [!DNL order.txt] im Ordner Profile\*Profilname*\Maps , um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen anhand ihres Namens in Wörterbuchreihenfolge angezeigt.

   >[!NOTE]
   >
   >Beim Bearbeiten der [!DNL order.txt] -Datei, achten Sie darauf, keine Kartenschichten zu verdecken, die Sie anzeigen möchten.

   Weitere Informationen zur Verwendung von [!DNL order.txt] -Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuch*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Ein X wird neben [!DNL Work Online].
1. Öffnen Sie einen Arbeitsbereich, klicken Sie mit der rechten Maustaste auf eine globale Visualisierung und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
