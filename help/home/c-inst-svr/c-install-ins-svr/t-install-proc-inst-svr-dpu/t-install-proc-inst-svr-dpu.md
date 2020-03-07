---
description: Detaillierte Anweisungen zum Installieren einer Insight Server-DPU und zum Konfigurieren dieser für administrative Zwecke.
solution: Insight
title: Installationsanweisungen für eine Insight Server-DPU
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installationsanweisungen für eine Insight Server-DPU{#installation-procedures-for-an-insight-server-dpu}

Detaillierte Anweisungen zum Installieren einer Insight Server-DPU und zum Konfigurieren dieser für administrative Zwecke.

Um eine [!DNL Insight Server] DPU zu installieren und zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen, um die richtige Reihenfolge zu erreichen:

1. Installieren Sie die [!DNL Insight Server] Programmdateien. Siehe [Installieren der Insight Server-Programmdateien](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Download and install the [!DNL Insight Server] digital certificate. Siehe [Herunterladen und Installieren der digitalen Zertifikate](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Überprüfen Sie die Anschlusseinstellungen in der [!DNL Communications.cfg] Datei. Siehe [Überprüfen der Port-Einstellungen](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Ändern Sie die [!DNL Access Control.cfg] Datei, um den administrativen Zugriff [!DNL Insight Server] von zu ermöglichen [!DNL Insight]. Siehe [Aktualisieren der Zugriffssteuerungsdatei](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Ändern Sie die [!DNL server.address] Datei, um den Netzwerkspeicherort des Servers zu definieren. Siehe [Definieren des Netzwerkspeicherorts](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)des Servers.
1. (Optional) Ändern Sie die [!DNL Disk Files.cfg] Datei, um anzugeben, wo die verarbeiteten Daten gespeichert werden. Siehe [Speicherort des Datensatzes konfigurieren (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installieren Sie die Profile und Lookup-Dateien. Siehe [Installieren von Profilen und Suchdateien](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Legen Sie die Speicherauslastungsparameter für Microsoft Windows fest.
1. Registrieren Sie sich [!DNL Insight Server] als Windows-Dienst. Siehe [Registrieren von Insight Server als Windows-Dienst](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
