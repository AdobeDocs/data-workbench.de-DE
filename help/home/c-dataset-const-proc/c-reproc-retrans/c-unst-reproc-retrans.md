---
description: Während der Neuverarbeitung erstellt der Data Workbench-Server Ihren Datensatz wie in den Konfigurationsdateien für die Protokollverarbeitung und Transformation des Datensatzes angegeben.
solution: Analytics
title: Grundlagen der Wiederaufbereitung und Umgestaltung
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Grundlagen der Wiederaufbereitung und Umgestaltung{#understanding-reprocessing-and-retransformation}

Während der Neuverarbeitung erstellt der Data Workbench-Server Ihren Datensatz wie in den Konfigurationsdateien für die Protokollverarbeitung und Transformation des Datensatzes angegeben.

Dazu muss der Data Workbench-Server (InsightServer64.exe) sowohl die Phase der Protokollverarbeitung als auch die Transformationsphase der Datensatzkonstruktion abschließen. Nach Abschluss der Protokollverarbeitung wird die Konvertierung automatisch ausgelöst. Die Konvertierung kann jedoch auch unabhängig von der Protokollverarbeitung erfolgen.

Während der Phase der Protokollverarbeitung haben Benutzer von Data Workbench keinen Zugriff auf die Daten im Datensatz. Während der Transformationsphase haben Benutzer von Data Workbench Zugriff auf aktuelle Daten, aber die Daten werden nicht vollständig, sondern stichprobenartig gesampelt. Die Datenanalyse kann während der Transformation fortgesetzt werden, Abfragen werden jedoch nur so schnell abgeschlossen, wie die Transformation erfolgt.

## Wiederaufbereitung {#section-92f1e46bf1534b3dba39e9493190b8ab}

Bei jedem Ausführen einer der folgenden Aufgaben erfolgt die Protokollverarbeitung und daher die Konvertierung automatisch, um den Datensatz wie in den Datenset-Konfigurationsdateien angegeben zu rekonstruieren:

* Fügen Sie eine neue Datenquelle hinzu.
* Fügen Sie dem Cluster in der [!DNL Profile.cfg] Datei einen neuen Data Workbench-Server hinzu.
* Ändern Sie die [!DNL Cluster.cfg] Datei.
* Ändern Sie die [!DNL Log Processing.cfg] Datei oder eine [!DNL Log Processing Dataset Include] Datei, einschließlich, aber nicht beschränkt auf Folgendes:

   * Neuen Parameter hinzufügen
   * Ändern einer Transformation
   * Ändern der Parameter &quot;Startzeit&quot;oder &quot;Endzeit&quot;

* Aktualisieren Sie Ihre [!DNL Insight Server.exe] Datei.

Sie können die Neuverarbeitung auch jederzeit starten, indem Sie ein beliebiges Zeichen oder eine beliebige Kombination von Zeichen in den Parameter &quot;Neu verarbeiten&quot;der [!DNL Log Processing.cfg] Datei eingeben und die Datei speichern.

>[!NOTE]
>
>Damit eine erneute Verarbeitung erfolgt, muss der Parameter &quot;Pause&quot;in der [!DNL Log Processing Mode.cfg] Datei auf &quot;false&quot;gesetzt werden. Der Standardwert dieses Parameters ist &quot;false&quot;, sodass eine Änderung des Parameters möglicherweise nicht erforderlich ist. Weitere Informationen [!DNL Log Processing Mode.cfg]finden Sie unter [Zusätzliche Konfigurationsdateien](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Umwandlung {#section-02446744549940ada8eba0573ec5575f}

Jedes Mal, wenn Sie Informationen in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei ändern, z. B. eine Transformation oder eine neue Dimension definieren, erfolgt die Transformation automatisch.

Jedes Mal, wenn Sie Lookup-Dateien ändern, auf die in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] -Datei verwiesen wird (einschließlich Lookup-Dateien für [!DNL Categorize], [!DNL FlatFileLookup]und [!DNL ODBCLookup] Transformationen), müssen Sie eine Transformation starten, indem Sie ein beliebiges Zeichen oder eine beliebige Kombination von Zeichen im Parameter &quot;Neu verarbeiten&quot;der [!DNL Transformation.cfg] Datei eingeben und die Datei speichern.
