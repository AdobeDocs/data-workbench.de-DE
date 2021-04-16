---
description: Schritte, um eine beliebige Terrain-Ebene zur Anzeige auf der globalen Visualisierung verfügbar zu machen.
title: Verfügbar machen von neuen Topografiebildebenen
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# Verfügbar machen von neuen Topografiebildebenen{#make-a-new-terrain-image-layer-available}

Schritte, um eine beliebige Terrain-Ebene zur Anzeige auf der globalen Visualisierung verfügbar zu machen.

1. Legen Sie im Ordner &quot;Profils\*Profil name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die zugehörigen Bilddateien ab.
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner &quot;Profils\*Profil*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie im Kapitel Configuring Interface and Analyse Features im *Data Workbench Benutzerhandbuch*.

1. Wählen Sie in der Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und dann auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben &quot;Online arbeiten&quot;wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
