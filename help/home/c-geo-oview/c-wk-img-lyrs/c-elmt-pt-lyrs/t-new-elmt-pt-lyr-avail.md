---
description: Schritte, um eine Elementpunktebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
title: Verfügbar machen von neuen Elementpunktebenen
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Verfügbar machen von neuen Elementpunktebenen{#making-a-new-element-point-layer-available}

Schritte, um eine Elementpunktebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profils\*Profil name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die zugehörige Lookup-Datei.
1. Wenn Sie eine neue Dimension für Ihre Elementpunktebene definiert haben und Ihren Datensatz noch nicht umgestaltet haben, können Sie den Datensatz jetzt neu transformieren.
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner &quot;Profils\*Profil*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie im Kapitel Configuring Interface and Analyse Features im *Data Workbench Benutzerhandbuch*.

1. Wählen Sie in der Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben [!DNL Work Online] wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
