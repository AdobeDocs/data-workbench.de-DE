---
description: Normalerweise möchten Sie einem vorhandenen Cluster eine Insight Server-DPU hinzufügen, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität der aktuellen Konfiguration des Clusters übersteigt.
solution: Insight
title: Hinzufügen einer Insight Server-DPU zu einem vorhandenen Cluster
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hinzufügen einer Insight Server-DPU zu einem vorhandenen Cluster{#adding-an-insight-server-dpu-to-an-existing-cluster}

Normalerweise möchten Sie einem vorhandenen Cluster eine Insight Server-DPU hinzufügen, wenn die Datenmenge, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität der aktuellen Konfiguration des Clusters übersteigt.

## Aktualisieren der Konfigurationsdateien auf dem Master-Server {#section-7c9a23754a994d73b722d53f999f0e82}

Öffnen Sie [!DNL Insight]die [!DNL Server Files Manager] für Ihren Master [!DNL Insight Server] (normalerweise eine [!DNL Insight Server] FSU) und führen Sie für jede DPU, die Sie dem Cluster hinzufügen möchten, die folgenden Schritte aus:

1. Bearbeiten Sie die Adressdatei auf dem Master, [!DNL Insight Server] um den Namen und die Adresse der neuen DPU einzuschließen, wie unter [Hinzufügen der Processing Insight-Server zur Adressdatei](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)beschrieben. Fügen Sie den Namen und die Adresse der neuen DPU der Gruppe hinzu, in der die aktuelle Clusterposition aufgeführt [!DNL Insight Servers] ist.

1. Bearbeiten Sie die Zugriffssteuerungsdatei auf dem Master, [!DNL Insight Server] um die IP-Adresse der neuen DPU einzuschließen, wie unter [Aktualisieren der Zugriffssteuerungsdatei für einen Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)beschrieben.

## Installieren der New Insight Server-DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Diese Aufgabe gilt nur für Windows 32 Bit.

1. Kopieren Sie die folgenden Ordner von einer der aktuellen DPUs in Ihrem Cluster in die neue DPU:

   * [!DNL Insight Server] installdirectory/bin/
   * [!DNL Insight Server] Installationsverzeichnis/Zertifikate/
   * [!DNL Insight Server] Installationsordner/Komponenten/

1. Laden Sie das digitale Zertifikat für die neue DPU herunter und installieren Sie es wie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)beschrieben.
1. Legen Sie die Windows-Speichernutzungsparameter auf der neuen DPU fest.
1. Registrieren Sie sich [!DNL Insight Server] als Windows-Dienst auf dem neuen DPU-Computer, wie unter [Registrieren von Insight Server als Windows-Dienst](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)beschrieben.

1. Überprüfen Sie die Trace-Protokolle, um sicherzustellen, dass die DPU mit dem Master synchronisiert wird [!DNL Insight Server].
1. Wiederholen Sie die Schritte 1 bis 6 für jede zusätzliche DPU, die Sie dem Cluster hinzufügen.

## Hinzufügen der DPU &quot;New Insight Server&quot;zu den Verarbeitungsservern des Datenblattprofils {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Wenn die neue DPU denselben Datensatz verarbeitet wie die anderen DPUs im Cluster, fügen Sie den gemeinsamen Namen der neuen DPU der [!DNL profile.cfg] Datei auf dem Master hinzu, [!DNL Insight Server] wie unter Angabe der Verarbeitungsserver in Profile.cfg [](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)beschrieben.
