---
description: In der Regel möchten Sie einem vorhandenen Cluster eine Insight Server-DPU hinzufügen, wenn die Menge der Daten, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität der aktuellen Konfiguration Ihres Clusters übersteigt.
title: Hinzufügen einer Insight Server-DPU zu einem vorhandenen Cluster
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# Hinzufügen einer Insight Server-DPU zu einem vorhandenen Cluster{#adding-an-insight-server-dpu-to-an-existing-cluster}

In der Regel möchten Sie einem vorhandenen Cluster eine Insight Server-DPU hinzufügen, wenn die Menge der Daten, die Sie verarbeiten und für Ihre Benutzer von Insight und Report verfügbar machen möchten, die Kapazität der aktuellen Konfiguration Ihres Clusters übersteigt.

## Aktualisieren der Konfigurationsdateien auf dem Übergeordneten Server {#section-7c9a23754a994d73b722d53f999f0e82}

Öffnen Sie in [!DNL Insight] die [!DNL Server Files Manager] für Ihre Übergeordnete [!DNL Insight Server] (normalerweise eine [!DNL Insight Server]-FSU) und führen Sie für jede DPU, die Sie zum Cluster hinzufügen möchten, Folgendes aus:

1. Bearbeiten Sie die Adressdatei auf dem Übergeordneten [!DNL Insight Server], um den Namen und die Adresse der neuen DPU einzuschließen, wie unter [Hinzufügen der verarbeitenden Insight Server zur Adressdatei](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d) beschrieben. Fügen Sie den Namen und die Adresse der neuen DPU der Gruppe hinzu, in der die aktuelle [!DNL Insight Servers] Ihres Clusters aufgeführt ist.

1. Bearbeiten Sie die Zugriffssteuerungsdatei auf dem Übergeordneten [!DNL Insight Server], um die IP-Adresse der neuen DPU einzuschließen, wie unter [Aktualisieren der Zugriffssteuerungsdatei für einen Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b) beschrieben.

## Installieren der neuen Insight Server-DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Diese Aufgabe gilt nur für Windows 32 Bit.

1. Kopieren Sie die folgenden Ordner von einer der aktuellen DPUs in Ihrem Cluster in die neue DPU:

   * [!DNL Insight Server] Installationsverzeichnis/bin/
   * [!DNL Insight Server] Installationsverzeichnis/Zertifikate/
   * [!DNL Insight Server] Installationsordner/Komponenten/

1. Laden Sie das digitale Zertifikat für die neue DPU herunter und installieren Sie es wie unter [Herunterladen und Installieren der digitalen Zertifikate](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) beschrieben.
1. Legen Sie die Windows-Speicherauslastungsparameter auf der neuen DPU fest.
1. Registrieren Sie [!DNL Insight Server] als Windows-Dienst auf dem neuen DPU-Computer, wie unter [Registrieren von Insight Server als Windows-Dienst](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540) beschrieben.

1. Überprüfen Sie die Ablaufprotokolle, um sicherzustellen, dass die DPU mit dem Übergeordneten [!DNL Insight Server] synchronisiert wird.
1. Wiederholen Sie die Schritte 1 bis 6 für jede zusätzliche DPU, die Sie zum Cluster hinzufügen.

## Hinzufügen der neuen Insight Server-DPU zu den Verarbeitungsservern des Datensatzprofils {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Wenn die neue DPU denselben Datensatz wie die anderen DPUs im Cluster verarbeitet, fügen Sie den gemeinsamen Namen der neuen DPU zur [!DNL profile.cfg]-Datei unter Übergeordnet [!DNL Insight Server] hinzu, wie unter [Festlegen der Verarbeitungsserver in Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9) beschrieben.
