---
description: Die Datei "Log Processing.cfg"steuert die Phase der Protokollverarbeitung bei der Erstellung des Datensatzes, bei der ungeordnete Daten aus den Datenquellen (als Protokollquellen bezeichnet) gelesen werden und Filter und Transformationen auf die Daten angewendet werden.
solution: Analytics
title: Informationen zur Konfigurationsdatei für die Protokollverarbeitung
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informationen zur Konfigurationsdatei für die Protokollverarbeitung{#about-the-log-processing-configuration-file}

Die Datei &quot;Log Processing.cfg&quot;steuert die Phase der Protokollverarbeitung bei der Erstellung des Datensatzes, bei der ungeordnete Daten aus den Datenquellen (als Protokollquellen bezeichnet) gelesen werden und Filter und Transformationen auf die Daten angewendet werden.

Sie müssen die [!DNL Log Processing.cfg] Datei bearbeiten, um die folgenden Aufgaben zur Konfiguration des Datensatzes auszuführen:

* Protokollquellen angeben. Siehe [Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Bestimmen, welche Protokolleinträge während der Protokollverarbeitung in den Datensatz eingegeben werden. Siehe [Datenfilter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) und [Protokolleingabebedingung](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Aktivieren der Aufteilung von Tracking-IDs mit großen Mengen von Ereignisdaten. Siehe [Schlüsselaufteilung](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Konfigurieren eines Data Workbench-Servers für die Ausführung als Dateiservereinheit. Siehe [Konfigurieren einer Insight Server-Dateiservereinheit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Konfigurieren eines Data Workbench-Servers für die Ausführung als zentralisierter Normalisierungsserver. Siehe [Konfigurieren einer Insight Server-Dateiservereinheit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] -Dateien können zusätzliche Anweisungen für die Protokollverarbeitungsphase der Datensatzerstellung enthalten. Diese Dateien befinden sich im Ordner &quot;Dataset\Log Processing&quot;für ein beliebiges geerbtes Profil. Normalerweise definieren sie anwendungsspezifische Parameter (z. B. webspezifische Konfigurationsparameter für die Site-Anwendung). Informationen zu [!DNL Log Processing Dataset Include] Dateien finden Sie unter [DataSet Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Informationen zu webspezifischen Konfigurationsparametern für die Site finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).

