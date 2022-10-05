---
description: Die Datei "Log Processing.cfg"steuert die Protokollverarbeitungsphase der Datensatzerstellung, in der ungeordnete Daten aus den Datenquellen (als Protokollquellen bezeichnet) gelesen und Filter und Transformationen auf die Daten angewendet werden.
title: Über die Konfigurationsdatei für die Protokollverarbeitung
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# Über die Konfigurationsdatei für die Protokollverarbeitung{#about-the-log-processing-configuration-file}

{{eol}}

Die Datei &quot;Log Processing.cfg&quot;steuert die Protokollverarbeitungsphase der Datensatzerstellung, in der ungeordnete Daten aus den Datenquellen (als Protokollquellen bezeichnet) gelesen und Filter und Transformationen auf die Daten angewendet werden.

Sie müssen die [!DNL Log Processing.cfg] -Datei, um eine der folgenden Datensatzkonfigurationsaufgaben auszuführen:

* Festlegen von Protokollquellen. Siehe [Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Bestimmen, welche Protokolleinträge den Datensatz während der Protokollverarbeitung eingeben. Siehe [Datenfilter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) und [Protokolleintragsbedingung](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Aktivierung der Aufteilung von Tracking-IDs mit großen Mengen von Ereignisdaten. Siehe [Schlüsselaufteilung](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Konfigurieren eines Data Workbench-Servers für die Ausführung als Dateiservereinheit. Siehe [Konfigurieren einer Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Konfiguration eines Data Workbench-Servers für die Ausführung als zentralisierter Normalisierungsserver. Siehe [Konfigurieren einer Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] -Dateien können zusätzliche Anweisungen für die Protokollverarbeitungsphase der Datensatzerstellung enthalten. Diese Dateien befinden sich im Ordner &quot;Datensatz-/Protokollverarbeitung&quot;für alle geerbten Profile. Sie definieren normalerweise anwendungsspezifische Parameter (z. B. webspezifische Konfigurationsparameter für die Site-Anwendung). Informationen zu [!DNL Log Processing Dataset Include] -Dateien, siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Informationen zu webspezifischen Konfigurationsparametern für Site finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
