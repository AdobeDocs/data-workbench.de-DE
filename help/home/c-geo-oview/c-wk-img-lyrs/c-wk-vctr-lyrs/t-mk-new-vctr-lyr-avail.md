---
description: Schritte zum Bereitstellen einer Vektorebene zur Anzeige auf der globalen Visualisierung.
title: Verfügbar machen von neuen Vektorebenen
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# Verfügbar machen von neuen Vektorebenen{#making-a-new-vector-layer-available}

{{eol}}

Schritte zum Bereitstellen einer Vektorebene zur Anzeige auf der globalen Visualisierung.

1. Platzieren Sie im Ordner Profile\*profile name*\Maps im Installationsordner des Data Workbench-Servers die Ebenendatei und die [!DNL .vec] oder [!DNL .tsv] Dateien.
1. Bearbeiten Sie die [!DNL order.txt] im Ordner Profile\*Profilname*\Maps , um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen anhand ihres Namens in Wörterbuchreihenfolge angezeigt.

   >[!NOTE]
   >
   >Beim Bearbeiten der [!DNL order.txt] -Datei, achten Sie darauf, keine Kartenschichten zu verdecken, die Sie anzeigen möchten.

   Weitere Informationen zur Verwendung von [!DNL order.txt] -Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuch*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Ein X wird neben [!DNL Work Online].
1. Öffnen Sie einen Arbeitsbereich, klicken Sie mit der rechten Maustaste auf eine globale Visualisierung und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
