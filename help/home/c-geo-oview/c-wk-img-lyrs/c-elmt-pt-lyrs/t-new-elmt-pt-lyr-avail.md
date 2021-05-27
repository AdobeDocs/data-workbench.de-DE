---
description: Schritte, um eine Elementpunktebene zur Anzeige auf der globalen Visualisierung verfügbar zu machen.
title: Verfügbar machen von neuen Elementpunktebenen
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Verfügbar machen von neuen Elementpunktebenen{#making-a-new-element-point-layer-available}

Schritte, um eine Elementpunktebene zur Anzeige auf der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner Profile\*profile name*\Maps im Installationsordner des Data Workbench-Servers die Ebenendatei und die zugehörige Lookup-Datei.
1. Wenn Sie eine neue Dimension für Ihre Elementpunktebene definiert haben und den Datensatz noch nicht umtransformiert haben, müssen Sie den Datensatz jetzt neu transformieren.
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner Profile\*Profilname*\Maps , um die Reihenfolge widerzuspiegeln, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen anhand ihres Namens in Wörterbuchreihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, keine Landkartenschichten zu verdecken, die angezeigt werden sollen.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie im Kapitel &quot;Configuring Interface and Analysis Features&quot;des *Data Workbench-Benutzerhandbuchs*.

1. Wählen Sie in Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben [!DNL Work Online] wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich, klicken Sie mit der rechten Maustaste auf eine globale Visualisierung und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
