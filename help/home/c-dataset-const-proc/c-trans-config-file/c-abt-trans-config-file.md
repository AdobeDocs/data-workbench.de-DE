---
description: Die Datei "Transformation.cfg"steuert die Umwandlungsphase der Datensatzkonstruktion, während der zusätzliche Datentransformationen auf Daten angewendet werden, die bereits während der Protokollverarbeitung verarbeitet werden, um erweiterte Dimensionen zur Verwendung in der Analyse zu erstellen.
solution: Analytics
title: Informationen zur Konfigurationsdatei für Transformationen
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informationen zur Konfigurationsdatei für Transformationen{#about-the-transformation-configuration-file}

Die Datei &quot;Transformation.cfg&quot;steuert die Umwandlungsphase der Datensatzkonstruktion, während der zusätzliche Datentransformationen auf Daten angewendet werden, die bereits während der Protokollverarbeitung verarbeitet werden, um erweiterte Dimensionen zur Verwendung in der Analyse zu erstellen.

Sie müssen die [!DNL Transformation.cfg] Datei bearbeiten, um die folgenden Aufgaben zur Konfiguration des Datensatzes auszuführen:

* Filtern von Daten aus der Protokollverarbeitung durch Definieren der [!DNL log entry condition] zur Konvertierung.
* Festlegen der Zeitzone, die für die Erstellung von Zeitdimensionen und die Durchführung von Zeitkonvertierungen verwendet werden soll. Siehe [Zeitzonen](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] -Dateien können zusätzliche Anweisungen für die Umwandlungsphase der Datensatzerstellung enthalten. Diese Dateien befinden sich im Ordner &quot;DataSet\Transformation&quot;für ein beliebiges geerbtes Profil und definieren in der Regel anwendungsspezifische Parameter (z. B. webspezifische Konfigurationsparameter für die [!DNL Site] Anwendung). Informationen zu [!DNL Transformation Dataset Include] Dateien finden Sie unter [DataSet Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Informationen zu webspezifischen Konfigurationsparametern für die Site finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

