---
description: Schritte, um eine beliebige Elementpunktebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
title: Verfügbar machen von neuen Elementpunktebenen
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# Verfügbar machen von neuen Elementpunktebenen{#make-a-new-element-point-layer-available}

Schritte, um eine beliebige Elementpunktebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Platzieren Sie im Ordner &quot;Profils\*Profil name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die zugehörige Nachschlagedatei.
1. Wenn Sie eine neue Dimension für Ihre Elementpunktebene definiert haben und Ihren Datensatz noch nicht umgestaltet haben, können Sie den Datensatz jetzt neu transformieren.
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner &quot;Profils\*Profil*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie im Kapitel Configuring Interface and Analyse Features im *Data Workbench Benutzerhandbuch*.

1. Wählen Sie in der Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und dann auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben &quot;Online arbeiten&quot;wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
