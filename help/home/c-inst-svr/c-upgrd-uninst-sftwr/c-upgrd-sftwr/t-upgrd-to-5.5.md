---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.1 von 5.4
solution: Analytics
title: DWB Server-Upgrade 5.4 auf 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---


# DWB-Server-Upgrade: 5.4 auf 5.5{#dwb-server-upgrade-to}

Aktualisieren von Serverkomponenten für Data Workbench 6.1 von 5.4

Die Aktualisierung von [!DNL Insight] 5.4 auf [!DNL Insight] 5.5 ist daher relativ einfach.

Sie können auch direkt von [!DNL Insight] 5.3 auf [!DNL Insight] 5.5 aktualisieren, indem Sie die unten stehenden Schritte durchführen. Vergewissern Sie sich, dass Sie alle Upgrade-Aufgaben ausführen, die im Abschnitt [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) und [Upgrade von Insight 5.4 auf 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) aufgeführt sind.

1. Beenden Sie die [!DNL Insight Server] Dienste auf allen Servern im Cluster mit Ausnahme der [!DNL Insight Master Server].

   1. Kopieren Sie die neuen Dateien [!DNL ReportServer.exe] und [!DNL Insight.exe] Dateien in den Ordner Software\Insight.

   1. Kopieren Sie nach der Aktualisierung des [!DNL Insight] Clients die Dateien [!DNL InsightServer.exe] und [!DNL InsightServer64.exe] in den Ordner \Bin.

   1. Warten Sie, bis der Beginn [!DNL Insight Master Server] vorliegt, und überprüfen Sie dann, welche Version über die [!DNL Connections] Visualisierung ausgeführt wird.

1. Auf dem Cluster [!DNL Master Server] im [!DNL Insight] Client:

   1. Erstellen Sie eine lokale Kopie des vorhandenen [!DNL Base] Profils und benennen Sie es um (z. B. BaseBackup).
   1. Kopieren Sie das neue [!DNL Base] Profil in den Ordner &quot;Profils&quot;.
   1. Wiederholen Sie diese beiden Schritte für den Ordner &quot;Transform&quot;.

1. Kopieren Sie den Ordner &quot;Scripts&quot;aus dem Serverpaket in den Installationsordner [!DNL Master Server] des Servers.
1. Kopieren Sie die [!DNL Terrain Images.cfg.off] Datei in den Ordner Komponenten des [!DNL Master Server].
   **So aktualisieren Sie die Clientsoftware von[!DNL Insight]5.4 auf 5.5**

Vergewissern Sie sich in der [!DNL Insight.cfg] Datei, dass die Einstellung &quot;Software aktualisieren&quot;auf TRUE eingestellt ist.
