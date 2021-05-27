---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.1 von der Installation 5.4.
title: DWB-Server-Upgrade 5.4 auf 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB-Server-Upgrade: 5.4 auf 5.5{#dwb-server-upgrade-to}

Aktualisieren von Serverkomponenten für Data Workbench 6.1 von der Installation 5.4.

Daher ist die Aktualisierung von [!DNL Insight] 5.4 auf [!DNL Insight] 5.5 relativ einfach.

Sie können auch direkt von [!DNL Insight] 5.3 auf [!DNL Insight] 5.5 aktualisieren, indem Sie die folgenden Schritte ausführen. Stellen Sie sicher, dass Sie alle im Abschnitt [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) und im Abschnitt [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) aufgeführten Aktualisierungsaufgaben ausführen.

1. Beenden Sie die [!DNL Insight Server]-Dienste auf allen Servern im Cluster mit Ausnahme von [!DNL Insight Master Server].

   1. Kopieren Sie die neuen Dateien [!DNL ReportServer.exe] und [!DNL Insight.exe] in den Ordner Software\Insight .

   1. Nachdem der Client [!DNL Insight] aktualisiert wurde, kopieren Sie die Dateien [!DNL InsightServer.exe] und [!DNL InsightServer64.exe] in den Ordner \Bin .

   1. Warten Sie, bis [!DNL Insight Master Server] gestartet ist, und überprüfen Sie dann die Version, die über die Visualisierung [!DNL Connections] ausgeführt wird.

1. Auf dem Cluster [!DNL Master Server] im Client [!DNL Insight]:

   1. Erstellen Sie eine lokale Kopie des vorhandenen Profils [!DNL Base] und benennen Sie es um (z. B. BaseBackup).
   1. Kopieren Sie das neue Profil [!DNL Base] in den Ordner Profile .
   1. Wiederholen Sie diese beiden Schritte für den Ordner &quot;Transform&quot;.

1. Kopieren Sie den Ordner Scripts aus dem Serverpaket in den Ordner [!DNL Master Server] in den Installationsordner für Server.
1. Kopieren Sie die Datei [!DNL Terrain Images.cfg.off] in den Ordner &quot;Components&quot;von [!DNL Master Server].
   **Aktualisierung der Clientsoftware von  [!DNL Insight] 5.4 auf 5.5**

Stellen Sie in der Datei [!DNL Insight.cfg] sicher, dass die Einstellung Software aktualisieren auf TRUE gesetzt ist.
