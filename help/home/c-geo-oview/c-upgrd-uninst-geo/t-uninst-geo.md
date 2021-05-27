---
description: Schritte zum Deinstallieren von Data WorkbenchGeography.
title: Deinstallieren von Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Deinstallieren von Data Workbench Geography{#uninstalling-data-workbench-geography}

Schritte zum Deinstallieren von Data WorkbenchGeography.

>[!NOTE]
>
>Wenn das Profil, mit dem Sie Data Workbench [!DNL Geography] verwenden, auf einem Data Workbench-Servercluster ausgeführt wird, deinstallieren Sie das Profil [!DNL Geography] vom Übergeordneten Data Workbench-Server im Cluster.

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg]-Datei für jedes Profil zu aktualisieren, mit dem Sie Data Workbench [!DNL Geography] verwendet haben.

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL profile.cfg] wird angezeigt.

   1. Löschen Sie im Fenster [!DNL profile.cfg] den Profileintrag [!DNL Geography] aus dem Vektor [!DNL Directories].

   1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Profileintrag [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] aus dem Vektor [!DNL Directories] .

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

1. Löschen Sie den Ordner Geografie aus dem Ordner Profile in Ihrem Installationsordner für den Data Workbench-Server.
1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Ordner &quot;IP Geo-Intelligence&quot;oder &quot;IP-Geolocation&quot;aus dem Ordner &quot;Profile&quot;in Ihrem Installationsordner für den Data Workbench-Server.
1. Löschen Sie den Ordner Geografie aus dem Ordner Suchen in Ihrem Installationsordner für den Data Workbench-Server.
1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Ordner &quot;IP Geo-Intelligence&quot;oder &quot;IP-Geolocation&quot;aus dem Ordner &quot;Suchen&quot;in Ihrem Installationsordner für den Data Workbench-Server.
1. Wenn Sie neue Topografiebilder erstellt haben, löschen Sie die Datei [!DNL Terrain Images.cfg] aus dem Ordner Komponenten in Ihrem Installationsordner für den Data Workbench-Server.
