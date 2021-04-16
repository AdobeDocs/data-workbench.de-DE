---
description: Schritte, um eine Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.
title: Verfügbar machen von neuen Vektorebenen
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# Verfügbar machen von neuen Vektorebenen{#making-a-new-vector-layer-available}

Schritte, um eine Vektorebene für die Anzeige in der globalen Visualisierung verfügbar zu machen.

1. Legen Sie im Ordner &quot;Profils\*Profil name*\Maps&quot;im Installationsordner des Data Workbench-Servers die Ebenendatei und die [!DNL .vec]- oder [!DNL .tsv]-Dateien ab.
1. Bearbeiten Sie die Datei [!DNL order.txt] im Ordner &quot;Profils\*Profil*\Maps&quot;, um die Reihenfolge anzuzeigen, in der die Ebenen angezeigt werden sollen. Standardmäßig werden Ebenen nach ihrem Namen in lexikografischer Reihenfolge angezeigt.

   >[!NOTE]
   >
   >Achten Sie bei der Bearbeitung der Datei [!DNL order.txt] darauf, die anzuzeigenden Map-Ebenen nicht zu verdecken.

   Weitere Informationen zur Verwendung von [!DNL order.txt]-Dateien finden Sie im Kapitel Configuring Interface and Analyse Features im *Data Workbench Benutzerhandbuch*.

1. Wählen Sie in der Data Workbench das gewünschte Profil aus, indem Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs klicken und **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]*** klicken.
1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Work Online]**. Neben [!DNL Work Online] wird ein X angezeigt.
1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste und wählen Sie die neue Ebene aus. Neben dem Ebenennamen wird ein X angezeigt.
