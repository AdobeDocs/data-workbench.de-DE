---
description: Schritte zum Bereitstellen einer Vektorebene zur Anzeige auf der globalen Visualisierung.
title: Verfügbar machen von neuen Vektorebenen
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# Verfügbar machen von neuen Vektorebenen{#making-a-new-vector-layer-available}

Schritte zum Bereitstellen einer Vektorebene zur Anzeige auf der globalen Visualisierung.

1. Platzieren Sie im Ordner Profile\*Profilname*\Maps im Installationsordner des Data Workbench-Servers die Ebenendatei und die Dateien [!DNL .vec] oder [!DNL .tsv].
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner Profile\*Profilname*\Maps , um die Reihenfolge widerzuspiegeln, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen anhand ihres Namens in Wörterbuchreihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, keine Landkartenschichten zu verdecken, die angezeigt werden sollen.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuchs*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben [!DNL Work Online] wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich, klicken Sie mit der rechten Maustaste auf eine globale Visualisierung und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
