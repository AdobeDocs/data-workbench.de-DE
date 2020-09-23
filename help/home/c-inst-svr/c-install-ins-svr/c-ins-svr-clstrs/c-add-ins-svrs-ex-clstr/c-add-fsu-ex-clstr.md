---
description: Möglicherweise möchten Sie einem vorhandenen Cluster eine Insight Server-FSU hinzufügen, wenn Sie Quelldaten auf einem zusätzlichen Dateiserver speichern oder eine Sicherung für Ihren Übergeordnet Insight Server einrichten möchten.
solution: Analytics
title: Hinzufügen einer Insight Server-FSU zu einem vorhandenen Cluster
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---


# Hinzufügen einer Insight Server-FSU zu einem vorhandenen Cluster{#adding-an-insight-server-fsu-to-an-existing-cluster}

Möglicherweise möchten Sie einem vorhandenen Cluster eine Insight Server-FSU hinzufügen, wenn Sie Quelldaten auf einem zusätzlichen Dateiserver speichern oder eine Sicherung für Ihren Übergeordnet Insight Server einrichten möchten.

Um einem vorhandenen Cluster eine [!DNL Insight Server] FSU hinzuzufügen, müssen Sie die folgenden Schritte ausführen:

1. [Konfigurationsdateien auf dem Übergeordnet Server aktualisieren](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [New Insight Server FSU installieren](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [New Insight Server FSU konfigurieren](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Konfigurationsdateien auf dem Übergeordnet Server aktualisieren {#section-b5f21f2edb35493da4475de2cdeefca1}

Öffnen Sie [!DNL Insight]die [!DNL Server Files Manager] für Ihren Übergeordnet [!DNL Insight Server] (normalerweise ein [!DNL Insight Server] FSU) und führen Sie für jede FSU, die Sie dem Cluster hinzufügen möchten, die folgenden Schritte aus:

1. Bearbeiten Sie die Adressdatei auf dem Übergeordnete, [!DNL Insight Server] um den Namen und die Adresse des neuen FSU einzuschließen, wie unter [Hinzufügen der Processing Insight-Server zur Adressdatei](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)beschrieben. hinzufügen Sie den Namen und die Adresse des neuen FSU zu der Gruppe, in der der aktuelle Cluster aufgeführt [!DNL Insight Servers] ist.

1. Bearbeiten Sie die Zugriffskontrollen-Datei auf dem Übergeordnete, [!DNL Insight Server] um die IP-Adresse des neuen FSU einzuschließen, wie unter [Aktualisieren der Zugriffskontrolle-Datei für einen Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)beschrieben.

## New Insight Server FSU installieren {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Erstellen Sie auf Ihrem aktuellen FSU eine ZIP-Datei des [!DNL Insight Server] Installationsordners und kopieren Sie die Datei in das neue FSU.
1. Dekomprimieren Sie die Datei an den Speicherort, an dem Sie die [!DNL Insight Server] Software ablegen möchten.
1. Laden Sie das digitale Zertifikat für die neue FSU herunter und installieren Sie es wie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)beschrieben.
1. Legen Sie die Windows-Speichernutzungsparameter auf dem neuen FSU fest.
1. Ändern Sie den Namen der [!DNL .address] Datei entsprechend dem Namen des FSU, wie unter [Definieren des Netzwerkspeicherorts](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)des Servers beschrieben.

1. Wenn sich die Laufwerkstruktur des neuen FSU von der primären FSU unterscheidet, müssen Sie die [!DNL Disk Files.cfg] Datei bearbeiten.

   1. Öffnen Sie die [!DNL Disk Files.cfg] Datei auf dem neuen FSU.
   1. Aktualisieren Sie die Einstellungen entsprechend den Laufwerken des primären FSU, wie unter Dataset-Datenraum [überwachen beschrieben](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Speichern Sie die Datei lokal und auf dem Server.

1. Registrieren Sie sich [!DNL Insight Server] als Windows-Dienst auf dem neuen FSU-Computer, wie unter [Registering Insight Server as a Windows Service](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)beschrieben.

1. Wiederholen Sie die Schritte 1 bis 6 für jede zusätzliche FSU, die Sie dem Cluster hinzufügen.

## New Insight Server FSU konfigurieren {#section-c39334c5bd754d5b98d41ad094333108}

Die folgenden Verfahren enthalten Anweisungen für bestimmte Aufgaben der Konfiguration. Befolgen Sie die Anweisungen, die für Ihre Implementierung des neuen FSU geeignet sind.

**So konfigurieren Sie die FSU für die Datenspeicherung von Quelldaten**

Wenn das neue FSU zusätzliche Quelldaten für das auf dem Cluster ausgeführte Dataset speichert, müssen Sie den Dateiserverkonfigurationsprozess durchführen, wie im Kapitel &quot;Konfigurationsdatei für die Protokollverarbeitung&quot;des [!DNL Insight Server] Datensatzkonfigurationshandbuchs *unter &quot;Eine* Dateiservereinheit konfigurieren&quot;beschrieben.

**So erstellen Sie für neue FSU die Sicherung für die Übergeordnet[!DNL Insight Server]FSU**

Wenn Sie die neue FSU als Sicherung für das Übergeordnet verwenden möchten [!DNL Insight Server] (das als FSU für den Cluster dient), müssen Sie die Synchronisierungsdatei für das neue (Backup-) FSU so ändern, dass sie mit dem Übergeordnet-FSU synchronisiert wird.

1. Verwenden Sie auf dem Backup- [!DNL Insight Server] FSU die [!DNL Server Files Manager] , um die [!DNL Synchronize.cfg] Datei im [!DNL Components for Processing Servers] Ordner in den [!DNL Components] Ordner zu kopieren.

1. Öffnen Sie die [!DNL Synchronize.cfg] Datei (im [!DNL Components] Ordner) in [!DNL Insight].

1. Suchen Sie den SynchronizeDir, der den Speicherort des Komponentenordners angibt. Unter Verzeichnisse sind möglicherweise mehrere Synchronisierungsordner aufgeführt. Daher müssen Sie die Inhalte für viele dieser Ordner (durch Klicken auf die Servernummer) Ansicht vornehmen, um den gewünschten Server zu finden.
1. Bearbeiten Sie den Eintrag SynchronizeDir und fügen Sie einen zweiten Eintrag SynchronizeDir hinzu, wie im Beispiel unten gezeigt.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Speichern Sie die geänderte Datei unter einem neuen Namen, [!DNL FSU_Synchronize.cfg] sodass Sie sie nicht mit den Dateien auf den [!DNL Synchronize.cfg] DPUs im Cluster verwechseln.

1. Speichern Sie die lokale Kopie der umbenannten Datei mit dem [!DNL Server Files Manager] Befehl auf dem Server. Das Backup-FSU lädt die Dateien in den identifizierten Verzeichnissen vom Übergeordnet [!DNL Insight Server] FSU herunter und ruft dynamisch aktualisierte Kopien dieser Dateien vom Übergeordnet [!DNL Insight Server] FSU ab, wenn sie sich ändern.

