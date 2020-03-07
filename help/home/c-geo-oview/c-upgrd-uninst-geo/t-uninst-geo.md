---
description: Schritte zum Deinstallieren von Data WorkbenchGeography.
solution: Analytics
title: Data Workbench-Geografie deinstallieren
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench-Geografie deinstallieren{#uninstalling-data-workbench-geography}

Schritte zum Deinstallieren von Data WorkbenchGeography.

>[!NOTE]
>
>Wenn das Profil, mit dem Sie Data Workbench verwenden, auf einem Data Workbench-Servercluster ausgeführt [!DNL Geography] [!DNL Geography] wird, deinstallieren Sie das Profil vom Master-Data Workbench-Server im Cluster.

1. Führen Sie die folgenden Schritte aus, um die [!DNL profile.cfg] Datei für jedes Profil zu aktualisieren, mit dem Sie Data Workbench verwendet haben [!DNL Geography].

   1. Öffnen Sie den [!DNL Profile Manager].
   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das [!DNL profile.cfg] Fenster wird angezeigt.

   1. Löschen Sie im [!DNL profile.cfg] Fenster den [!DNL Geography] Profileintrag aus dem [!DNL Directories] Vektor.

   1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den [!DNL IP Geo-intelligence] bzw. den [!DNL IP Geo-location] Profileintrag aus dem [!DNL Directories] Vektor.

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen für [!DNL profile.cfg] die [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Löschen Sie den Ordner &quot;Geografie&quot;aus dem Ordner &quot;Profile&quot;im Installationsordner des Data Workbench-Servers.
1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Ordner &quot;IP-Geo-Intelligence&quot;oder &quot;IP-Geo-Speicherort&quot;aus dem Ordner &quot;Profile&quot;im Installationsordner des Data Workbench-Servers.
1. Löschen Sie den Ordner &quot;Geografie&quot;aus dem Ordner &quot;Suchen&quot;im Installationsordner des Data Workbench-Servers.
1. Wenn Sie einen Datendienst verwendet haben, löschen Sie den Ordner &quot;IP-Geo-Intelligence&quot;oder &quot;IP-Geo-Speicherort&quot;aus dem Ordner &quot;Suchen&quot;im Installationsordner des Data Workbench-Servers.
1. Wenn Sie neue Terrain-Bilder erstellt haben, löschen Sie die [!DNL Terrain Images.cfg] Datei aus dem Ordner &quot;Komponenten&quot;im Installationsordner des Data Workbench-Servers.
