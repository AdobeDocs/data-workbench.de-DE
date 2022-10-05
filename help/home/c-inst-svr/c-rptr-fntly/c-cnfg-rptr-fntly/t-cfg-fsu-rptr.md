---
description: Anweisungen zum Installieren und Konfigurieren einer Insight Server-FSU für die Verwendung mit Repeater.
title: Konfigurieren einer Insight Server-FSU für Repeater
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Konfigurieren einer Insight Server-FSU für Repeater{#configuring-an-insight-server-fsu-for-repeater}

{{eol}}

Anweisungen zum Installieren und Konfigurieren einer Insight Server-FSU für die Verwendung mit Repeater.

Führen Sie die folgenden Aufgaben in der angegebenen Reihenfolge aus. Alle Ausnahmen oder Änderungen, die Sie vornehmen müssen, damit die Variable [!DNL Insight Server] FSU kann als Repeater-Server verwendet werden, werden nach jedem Schritt notiert.

1. Installieren Sie die [!DNL Insight Server] Programmdateien, wie unter [Installieren von Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Da der Computer, auf dem Sie diese Dateien installieren, zum Ausführen von Repeater verwendet wird, ist es hilfreich, dem Installationsordner einen beschreibenden Namen zu geben, z. B. [!DNL D:\Adobe\Repeater].

1. Installieren Sie die [!DNL Insight Server] digitales Zertifikat wie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Nachdem Sie sich beim Adobe License Server angemeldet haben, suchen Sie nach dem Zertifikatnamen, der dem gemeinsamen Servernamen des angegebenen Repeater-Computers entspricht.

1. Überprüfen Sie die Port-Einstellungen in der [!DNL Communications.cfg] Datei wie unter [Überprüfen der Port-Einstellungen](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Wenn die zugewiesenen Ports (Port und SSL-Anschluss) von einem anderen Prozess verwendet werden, der auf demselben Computer ausgeführt wird, müssen Sie die Portzuweisungen in ein nicht verwendetes Paar ändern.

1. Ändern Sie bei Bedarf den Protokollordner für die [!DNL Sensor] Daten, die auf diesem Computer erfasst und gespeichert werden sollen. Anweisungen finden Sie unter [Überwachen des Festplattenspeichers für Ereignisdaten](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Ändern Sie die [!DNL Access Control.cfg] -Datei, um Administratorzugriff zu ermöglichen [!DNL Insight Server] von [!DNL Insight] wie in [Aktualisieren der Datei &quot;Zugriffskontrolle&quot;](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Ändern Sie die [!DNL server.address] -Datei, um den Netzwerkspeicherort des Servers gemäß Definition in [Definieren des Netzwerkstandorts des Servers](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Legen Sie die Parameter für die Windows-Speicherauslastung fest.
1. registrieren [!DNL Insight Server] als Windows-Dienst, wie unter [Registrieren von Insight Server als Windows-Dienst](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
