---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.1 von der Installation 5.4.
title: DWB-Server-Upgrade 5.4 auf 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB-Server-Upgrade: 5.4 auf 5.5{#dwb-server-upgrade-to}

{{eol}}

Aktualisieren von Serverkomponenten für Data Workbench 6.1 von der Installation 5.4.

Daher wird die Aktualisierung von [!DNL Insight] 5.4 bis [!DNL Insight] 5.5 ist relativ einfach.

Sie können auch direkt von [!DNL Insight] 5.3 bis [!DNL Insight] 5.5 mithilfe der folgenden Schritte. Stellen Sie sicher, dass alle in der [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) und [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) Abschnitt.

1. Stoppen Sie die [!DNL Insight Server] Dienste auf allen Servern im Cluster außer [!DNL Insight Master Server].

   1. Neue kopieren [!DNL ReportServer.exe] und [!DNL Insight.exe] Dateien in den Ordner Software\Insight.

   1. Nach dem [!DNL Insight] Client aktualisiert hat, kopieren Sie die [!DNL InsightServer.exe] und [!DNL InsightServer64.exe] Dateien in den Ordner &quot;\Bin&quot;.

   1. Warten Sie auf die [!DNL Insight Master Server] , um zu starten, und überprüfen Sie dann die Version, die über das [!DNL Connections] Visualisierung.

1. Auf dem Cluster [!DNL Master Server] im [!DNL Insight] client:

   1. Erstellen Sie eine lokale Kopie der vorhandenen [!DNL Base] Profil erstellen und es umbenennen (z. B. BaseBackup).
   1. Neue kopieren [!DNL Base] Profil in den Ordner Profile .
   1. Wiederholen Sie diese beiden Schritte für den Ordner &quot;Transform&quot;.

1. Kopieren Sie den Ordner &quot;Scripts&quot;aus dem Serverpaket in den Ordner [!DNL Master Server] in den Installationsordner des Servers.
1. Kopieren Sie die [!DNL Terrain Images.cfg.off] in den Ordner &quot;Components&quot;der [!DNL Master Server].
   **Aktualisieren der Clientsoftware von [!DNL Insight] 5.4 bis 5.5**

Im [!DNL Insight.cfg] müssen Sie sicherstellen, dass die Einstellung Software aktualisieren auf TRUE gesetzt ist.
