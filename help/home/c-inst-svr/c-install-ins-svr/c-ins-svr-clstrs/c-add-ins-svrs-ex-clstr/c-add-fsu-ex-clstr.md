---
description: Sie können eine Insight Server-FSU zu einem vorhandenen Cluster hinzufügen, wenn Sie Quelldaten auf einem zusätzlichen Dateiserver speichern oder eine Sicherung für Ihren Übergeordneten Insight Server einrichten möchten.
title: Hinzufügen einer Insight Server-FSU zu einem vorhandenen Cluster
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Hinzufügen einer Insight Server-FSU zu einem vorhandenen Cluster{#adding-an-insight-server-fsu-to-an-existing-cluster}

{{eol}}

Sie können eine Insight Server-FSU zu einem vorhandenen Cluster hinzufügen, wenn Sie Quelldaten auf einem zusätzlichen Dateiserver speichern oder eine Sicherung für Ihren Übergeordneten Insight Server einrichten möchten.

So fügen Sie eine [!DNL Insight Server] FSU zu einem vorhandenen Cluster müssen Sie die folgenden Schritte ausführen:

1. [Aktualisieren der Konfigurationsdateien auf dem Übergeordneten Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Installieren der neuen Insight Server-FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Konfigurieren der neuen Insight Server-FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Aktualisieren der Konfigurationsdateien auf dem Übergeordneten Server {#section-b5f21f2edb35493da4475de2cdeefca1}

In [!DNL Insight], öffnen Sie die [!DNL Server Files Manager] für Übergeordnete [!DNL Insight Server] (gewöhnlich ist [!DNL Insight Server] FSU) und führen Sie für jede FSU, die Sie zum Cluster hinzufügen möchten, Folgendes aus:

1. Bearbeiten Sie die Adressdatei auf Übergeordneten [!DNL Insight Server] den Namen und die Adresse des neuen FSU, wie in [Hinzufügen der verarbeitenden Insight Server zur Adressdatei](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Fügen Sie den Namen und die Adresse der neuen FSU der Gruppe hinzu, in der der aktuelle Cluster [!DNL Insight Servers] aufgelistet sind.

1. Bearbeiten Sie die Zugriffssteuerungsdatei auf dem Übergeordneten [!DNL Insight Server] , um die IP-Adresse des neuen FSU wie in [Aktualisieren der Datei &quot;Zugriffskontrolle&quot;für ein Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installieren der neuen Insight Server-FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Erstellen Sie auf Ihrer aktuellen FSU eine ZIP-Datei der [!DNL Insight Server] Installationsverzeichnis und kopieren Sie die Datei in die neue FSU.
1. Entpacken Sie die Datei an die Stelle, an der Sie die [!DNL Insight Server] Software.
1. Laden Sie das digitale Zertifikat für die neue FSU herunter und installieren Sie es wie in [Herunterladen und Installieren der digitalen Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Legen Sie die Windows-Speicherauslastungsparameter auf der neuen FSU fest.
1. Ändern Sie den Namen der [!DNL .address] -Datei, die den Namen des FSU widerspiegelt, wie unter [Definieren des Netzwerkstandorts des Servers](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Wenn sich die Laufwerkstruktur der neuen FSU von der der primären FSU unterscheidet, müssen Sie die [!DNL Disk Files.cfg] -Datei.

   1. Öffnen Sie die [!DNL Disk Files.cfg] -Datei auf der neuen FSU.
   1. Aktualisieren Sie die Einstellungen so, dass sie mit den Laufwerken der primären FSU übereinstimmen, wie unter [Überwachen des Festplattenspeichers für Datensatzdaten](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Speichern Sie die Datei lokal und auf dem Server.

1. registrieren [!DNL Insight Server] als Windows-Dienst auf dem neuen FSU-Computer, wie unter [Registrieren von Insight Server als Windows-Dienst](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Wiederholen Sie die Schritte 1 bis 6 für jede zusätzliche FSU, die Sie zum Cluster hinzufügen.

## Konfigurieren der neuen Insight Server-FSU {#section-c39334c5bd754d5b98d41ad094333108}

Die folgenden Verfahren enthalten Anweisungen für bestimmte Konfigurationsaufgaben. Befolgen Sie die Anweisungen, die für Ihre Implementierung des neuen FSU geeignet sind.

**So konfigurieren Sie die FSU für die Quelldatenspeicherung**

Wenn die neue FSU zusätzliche Quelldaten für den Datensatz speichert, der auf dem Cluster ausgeführt wird, müssen Sie den Dateiserver-Konfigurationsprozess wie unter Konfigurieren eines [!DNL Insight Server] File Server Unit im Kapitel &quot;Log Processing Configuration File&quot;des Kapitels *Anleitung zur Datensatzkonfiguration*.

**So erstellen Sie das Backup für die Übergeordnete FSU [!DNL Insight Server] FSU**

Wenn Sie die neue FSU zum Backup für die Übergeordneten machen möchten [!DNL Insight Server] (die als FSU für den Cluster dient), müssen Sie die Synchronisierungsdatei auf der neuen (Backup-) FSU so ändern, dass sie mit der Übergeordneten FSU synchronisiert wird.

1. Beim Backup [!DNL Insight Server] FSU, verwenden Sie die [!DNL Server Files Manager] , um die [!DNL Synchronize.cfg] in der Datei [!DNL Components for Processing Servers] Ordner in [!DNL Components] Ordner.

1. Öffnen Sie die [!DNL Synchronize.cfg] -Datei (in der [!DNL Components] Ordner) in [!DNL Insight].

1. Suchen Sie nach SynchronizeDir , der den Speicherort des Komponentenordners angibt. Unter Verzeichnisse sind möglicherweise mehrere Synchronisierungsordner aufgeführt. Daher müssen Sie möglicherweise die Inhalte für viele dieser Ordner anzeigen (indem Sie auf die Servernummer klicken), um den gewünschten Server zu finden.
1. Bearbeiten Sie den Eintrag SynchronizeDir und fügen Sie einen zweiten Eintrag SynchronizeDir hinzu, wie im folgenden Beispiel gezeigt.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Speichern Sie die geänderte Datei mit einem neuen Namen, z. B. [!DNL FSU_Synchronize.cfg] damit Sie es nicht mit der [!DNL Synchronize.cfg] Dateien auf den DPUs im Cluster.

1. Verwenden Sie die [!DNL Server Files Manager] , um die lokale Kopie der umbenannten Datei auf dem Server zu speichern. Die Backup-FSU lädt die Dateien in den identifizierten Verzeichnissen von den Übergeordneten herunter [!DNL Insight Server] FSU und ruft aktualisierte Kopien dieser Dateien dynamisch aus dem Übergeordneten ab [!DNL Insight Server] FSU, wenn sie sich ändern.
