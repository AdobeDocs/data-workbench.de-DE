---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.1 von 5.4
title: DWB Server-Upgrade 5.4 auf 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB-Server-Upgrade: 5.4 auf 5.5{#dwb-server-upgrade-to}

Aktualisieren von Serverkomponenten für Data Workbench 6.1 von 5.4

Daher ist die Aktualisierung von [!DNL Insight] 5.4 auf [!DNL Insight] 5.5 relativ einfach.

Sie können auch direkt von [!DNL Insight] 5.3 auf [!DNL Insight] 5.5 aktualisieren, indem Sie die folgenden Schritte durchführen. Stellen Sie sicher, dass Sie alle Upgrade-Aufgaben ausführen, die im Abschnitt [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) und im Abschnitt [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) aufgeführt sind.

1. Beenden Sie die [!DNL Insight Server]-Dienste auf allen Servern im Cluster mit Ausnahme von [!DNL Insight Master Server].

   1. Kopieren Sie die neuen Dateien [!DNL ReportServer.exe] und [!DNL Insight.exe] in den Ordner Software\Insight.

   1. Kopieren Sie nach der Aktualisierung des Clients die Dateien [!DNL InsightServer.exe] und [!DNL InsightServer64.exe] in den Ordner \Bin.[!DNL Insight]

   1. Warten Sie auf den Beginn [!DNL Insight Master Server] und überprüfen Sie dann die Version, die über die Visualisierung [!DNL Connections] ausgeführt wird.

1. Auf dem [!DNL Master Server]-Client des Clusters [!DNL Insight]:

   1. Erstellen Sie eine lokale Kopie des vorhandenen [!DNL Base]-Profils und benennen Sie es um (z. B. BaseBackup).
   1. Kopieren Sie das neue Profil [!DNL Base] in den Ordner &quot;Profils&quot;.
   1. Wiederholen Sie diese beiden Schritte für den Ordner &quot;Transform&quot;.

1. Kopieren Sie den Ordner &quot;Scripts&quot;aus dem Serverpaket in den Ordner [!DNL Master Server] in den Installationsordner des Servers.
1. Kopieren Sie die Datei [!DNL Terrain Images.cfg.off] in den Komponentenordner von [!DNL Master Server].
   **So aktualisieren Sie die Clientsoftware von  [!DNL Insight] 5.4 auf 5.5**

Stellen Sie in der Datei [!DNL Insight.cfg] sicher, dass die Einstellung &quot;Software aktualisieren&quot;auf TRUE eingestellt ist.
