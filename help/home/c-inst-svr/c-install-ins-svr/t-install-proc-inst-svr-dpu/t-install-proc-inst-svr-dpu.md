---
description: Detaillierte Anweisungen zum Installieren einer Insight Server-DPU und dessen Konfiguration für die administrative Verwendung.
title: Installationsverfahren für eine Insight Server-DPU
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Installationsverfahren für eine Insight Server-DPU{#installation-procedures-for-an-insight-server-dpu}

{{eol}}

Detaillierte Anweisungen zum Installieren einer Insight Server-DPU und dessen Konfiguration für die administrative Verwendung.

So installieren und konfigurieren Sie eine [!DNL Insight Server] DPU: Sie müssen die folgenden Aufgaben in der richtigen Reihenfolge ausführen:

1. Installieren Sie die [!DNL Insight Server] Programmdateien. Siehe [Installieren der Insight Server-Programmdateien](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Laden Sie die [!DNL Insight Server] digitales Zertifikat. Siehe [Herunterladen und Installieren der digitalen Zertifikate](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Überprüfen Sie die Port-Einstellungen in der [!DNL Communications.cfg] -Datei. Siehe [Überprüfen der Port-Einstellungen](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Ändern Sie die [!DNL Access Control.cfg] -Datei, um Administratorzugriff zu ermöglichen [!DNL Insight Server] von [!DNL Insight]. Siehe [Aktualisieren der Datei &quot;Zugriffskontrolle&quot;](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Ändern Sie die [!DNL server.address] -Datei, um den Netzwerkspeicherort des Servers zu definieren. Siehe [Definieren des Netzwerkstandorts des Servers](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Optional) Ändern Sie die [!DNL Disk Files.cfg] -Datei, um anzugeben, wo die verarbeiteten Daten gespeichert werden. Siehe [Konfigurieren des Datensatzstandorts (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installieren Sie die Profile und Lookup-Dateien. Siehe [Installieren von Profilen und Lookup-Dateien](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Legen Sie die Parameter für die Microsoft Windows-Speicherauslastung fest.
1. registrieren [!DNL Insight Server] als Windows-Dienst. Siehe [Registrieren von Insight Server als Windows-Dienst](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
