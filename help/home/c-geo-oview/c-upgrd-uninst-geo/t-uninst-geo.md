---
description: Schritte zum Deinstallieren von Data WorkbenchGeography.
title: Deinstallieren von Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Deinstallieren von Data Workbench Geography{#uninstalling-data-workbench-geography}

{{eol}}

Schritte zum Deinstallieren von Data WorkbenchGeography.

>[!NOTE]
>
>Wenn das Profil, mit dem Sie Data Workbench verwenden [!DNL Geography] auf einem Data Workbench-Servercluster ausgeführt wird, deinstallieren Sie die [!DNL Geography] Profil vom Übergeordneten Data Workbench-Server im Cluster.

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil, mit dem Sie Data Workbench verwenden [!DNL Geography].

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL profile.cfg] angezeigt.

   1. Im [!DNL profile.cfg] -Fenster, löschen Sie die [!DNL Geography] Profileintrag aus [!DNL Directories] vektor.

   1. Wenn Sie einen Datendienst verwendet haben, löschen Sie die [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] Profileintrag aus [!DNL Directories] vektor.

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Löschen Sie den Ordner Geografie aus dem Ordner Profile in Ihrem Installationsordner für den Data Workbench-Server.
1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Ordner &quot;IP Geo-Intelligence&quot;oder &quot;IP-Geolocation&quot;aus dem Ordner &quot;Profile&quot;in Ihrem Installationsordner für den Data Workbench-Server.
1. Löschen Sie den Ordner Geografie aus dem Ordner Suchen in Ihrem Installationsordner für den Data Workbench-Server.
1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Ordner &quot;IP Geo-Intelligence&quot;oder &quot;IP-Geolocation&quot;aus dem Ordner &quot;Suchen&quot;in Ihrem Installationsordner für den Data Workbench-Server.
1. Wenn Sie neue Topografiebilder erstellt haben, löschen Sie die [!DNL Terrain Images.cfg] -Datei aus dem Ordner &quot;Components&quot;im Installationsordner des Data Workbench-Servers.
