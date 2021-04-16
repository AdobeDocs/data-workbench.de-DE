---
description: Die Datei "Transformation.cfg"steuert die Umwandlungsphase der Datensatzerstellung, während der zusätzliche Datentransformationen auf bereits während der Protokollverarbeitung verarbeitete Daten angewendet werden, um erweiterte Dimensionen zur Verwendung in der Analyse zu erstellen.
title: Über die Konfigurationsdatei für Umwandlungen
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Über die Konfigurationsdatei für Umwandlungen{#about-the-transformation-configuration-file}

Die Datei &quot;Transformation.cfg&quot;steuert die Umwandlungsphase der Datensatzerstellung, während der zusätzliche Datentransformationen auf bereits während der Protokollverarbeitung verarbeitete Daten angewendet werden, um erweiterte Dimensionen zur Verwendung in der Analyse zu erstellen.

Sie müssen die Datei [!DNL Transformation.cfg] bearbeiten, um eine der folgenden Aufgaben der Datensatzkonfiguration auszuführen:

* Filtern von Daten aus der Protokollverarbeitung durch Definieren der [!DNL log entry condition] zur Transformation.
* Festlegen der Zeitzone, die für die Erstellung von Zeitdimensionen und die Durchführung von Zeitkonvertierungen verwendet werden soll. Siehe [Zeitzonen](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] -Dateien können zusätzliche Anweisungen für die Umwandlungsphase der Datensatzerstellung enthalten. Diese Dateien befinden sich im Ordner &quot;Dataset\Transformation&quot;für ein beliebiges geerbtes Profil und definieren in der Regel anwendungsspezifische Parameter (z. B. webspezifische Konfigurationsparameter für die [!DNL Site]-Anwendung). Weitere Informationen zu den [!DNL Transformation Dataset Include]-Dateien finden Sie unter [Dateninklusive Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Informationen zu webspezifischen Konfigurationsparametern für die Site finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
