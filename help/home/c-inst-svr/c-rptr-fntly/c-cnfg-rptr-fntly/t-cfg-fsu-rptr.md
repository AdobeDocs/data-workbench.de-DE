---
description: Anweisungen zum Installieren und Konfigurieren eines Insight Server-FSU für die Verwendung mit Repeater.
title: Konfigurieren einer Insight Server-FSU für Repeater
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Konfigurieren einer Insight Server-FSU für Repeater{#configuring-an-insight-server-fsu-for-repeater}

Anweisungen zum Installieren und Konfigurieren eines Insight Server-FSU für die Verwendung mit Repeater.

Führen Sie die folgenden Aufgaben in der richtigen Reihenfolge durch. Alle Ausnahmen oder Änderungen, die Sie vornehmen müssen, damit die [!DNL Insight Server]-FSU als Repeater-Server verwendet werden kann, werden nach jedem Schritt vermerkt.

1. Installieren Sie die [!DNL Insight Server]-Programm-Dateien, wie unter [Installieren des Insight-Servers](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd) beschrieben.

   Da der Computer, auf dem Sie diese Dateien installieren, zum Ausführen von Repeater verwendet wird, ist es hilfreich, dem Installationsordner einen beschreibenden Namen wie [!DNL D:\Adobe\Repeater] zu geben.

1. Installieren Sie das digitale Zertifikat [!DNL Insight Server] wie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) beschrieben.

   Nachdem Sie sich beim Adobe License Server angemeldet haben, suchen Sie nach dem Zertifikatnamen, der dem gemeinsamen Servernamen des angegebenen Repeater-Computers entspricht.

1. Überprüfen Sie die Anschlusseinstellungen in der Datei [!DNL Communications.cfg], wie unter [Überprüfen der Anschlusseinstellungen](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64) beschrieben.

   Wenn die zugewiesenen Anschlüsse (Port und SSL Port) von einem anderen Prozess verwendet werden, der auf demselben Computer ausgeführt wird, müssen Sie die Anschlusszuweisungen in ein nicht verwendetes Paar ändern.

1. Ändern Sie bei Bedarf den Protokollordner für die [!DNL Sensor]-Daten, die auf diesem Computer erfasst und gespeichert werden sollen. Anweisungen hierzu finden Sie unter [Ereignis-Datenraum überwachen](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Ändern Sie die [!DNL Access Control.cfg]-Datei, um den administrativen Zugriff auf [!DNL Insight Server] von [!DNL Insight] zuzulassen, wie unter [Aktualisieren der Zugriffskontrolle-Datei](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d) beschrieben.
1. Ändern Sie die Datei [!DNL server.address], um den Netzwerkspeicherort des Servers wie unter [Definieren des Netzwerkspeicherorts des Servers](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) definiert zu definieren.
1. Legen Sie die Parameter für die Speichernutzung von Windows fest.
1. Registrieren Sie [!DNL Insight Server] als Windows-Dienst, wie unter [Registering Insight Server as a Windows Service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540) beschrieben.
