---
description: Die Datei Transformation.cfg steuert die Umwandlungsphase der Datensatzerstellung, in der zusätzliche Datenumwandlungen auf Daten angewendet werden, die bereits während der Protokollverarbeitung verarbeitet werden, um erweiterte Dimensionen zur Verwendung in der Analyse zu erstellen.
title: Über die Konfigurationsdatei für Umwandlungen
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Über die Konfigurationsdatei für Umwandlungen{#about-the-transformation-configuration-file}

{{eol}}

Die Datei Transformation.cfg steuert die Umwandlungsphase der Datensatzerstellung, in der zusätzliche Datenumwandlungen auf Daten angewendet werden, die bereits während der Protokollverarbeitung verarbeitet werden, um erweiterte Dimensionen zur Verwendung in der Analyse zu erstellen.

Sie müssen die [!DNL Transformation.cfg] -Datei, um eine der folgenden Datensatzkonfigurationsaufgaben auszuführen:

* Filtern von Daten aus der Protokollverarbeitung durch Definieren der [!DNL log entry condition] zur Umwandlung.
* Festlegen der Zeitzone, die für die Erstellung von Zeitdimensionen und für die Durchführung von Zeitkonversionen verwendet werden soll. Siehe [Zeitzonen](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] -Dateien können zusätzliche Anweisungen für die Transformationsphase der Datensatzerstellung enthalten. Diese Dateien befinden sich im Ordner &quot;Datensatz\Transformation&quot;für jedes geerbte Profil und definieren normalerweise anwendungsspezifische Parameter (z. B. webspezifische Konfigurationsparameter für die [!DNL Site] Anwendung). Informationen zu [!DNL Transformation Dataset Include] -Dateien, siehe [Datensatzaufnahme-Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Informationen zu webspezifischen Konfigurationsparametern für Site finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
