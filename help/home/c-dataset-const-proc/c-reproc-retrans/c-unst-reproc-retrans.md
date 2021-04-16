---
description: Während der Neuverarbeitung erstellt der Data Workbench-Server Ihren Datensatz wie in den Konfigurationsdateien für die Protokollverarbeitung und Transformation des Datensatzes angegeben.
title: Grundlagen zur Wiederaufbereitung und erneuten Umwandlung
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Grundlagen zur Wiederaufbereitung und erneuten Umwandlung{#understanding-reprocessing-and-retransformation}

Während der Neuverarbeitung erstellt der Data Workbench-Server Ihren Datensatz wie in den Konfigurationsdateien für die Protokollverarbeitung und Transformation des Datensatzes angegeben.

Dazu muss der Data Workbench-Server (InsightServer64.exe) sowohl die Phase der Protokollverarbeitung als auch die Transformationsphase der Datensatzkonstruktion abschließen. Nach Abschluss der Protokollverarbeitung erfolgt die Konvertierung durch Trigger automatisch, aber die Konvertierung kann auch unabhängig von der Protokollverarbeitung erfolgen.

Während der Phase der Protokollverarbeitung haben Benutzer von Data Workbench keinen Zugriff auf die Daten im Datensatz. Während der Transformationsphase haben Benutzer von Data Workbench Zugriff auf aktuelle Daten, aber die Daten werden nicht vollständig, sondern stichprobenartig gesampelt. Die Analyse von Daten kann während der Transformation fortgesetzt werden, aber die Abfragen werden erst so schnell abgeschlossen, wie die Transformation erfolgt.

## Wiederaufarbeitung {#section-92f1e46bf1534b3dba39e9493190b8ab}

Jedes Mal, wenn Sie eine der folgenden Aufgaben ausführen, erfolgt die Protokollverarbeitung und daher die Konvertierung automatisch, um den Datensatz wie in den Datenset-Konfigurationsdateien angegeben zu rekonstruieren:

* hinzufügen eine neue Datenquelle.
* hinzufügen Sie einen neuen Data Workbench-Server in Ihrem Cluster in der Datei [!DNL Profile.cfg].
* Ändern Sie die Datei [!DNL Cluster.cfg].
* Ändern Sie die Datei [!DNL Log Processing.cfg] oder eine [!DNL Log Processing Dataset Include]-Datei, einschließlich, aber nicht beschränkt auf Folgendes:

   * hinzufügen eines neuen Parameters
   * Ändern einer Transformation
   * Ändern der Parameter für die Beginn- oder Endzeit

* Aktualisieren Sie Ihre [!DNL Insight Server.exe]-Datei.

Sie können die Neuverarbeitung auch jederzeit starten, indem Sie ein beliebiges Zeichen oder eine beliebige Kombination von Zeichen in den Parameter &quot;Neu verarbeiten&quot;der Datei eingeben und die Datei speichern.[!DNL Log Processing.cfg]

>[!NOTE]
>
>Damit eine Neuverarbeitung erfolgt, muss der Parameter &quot;Pause&quot;in der Datei [!DNL Log Processing Mode.cfg] auf &quot;false&quot;gesetzt werden. Der Standardwert dieses Parameters ist &quot;false&quot;, sodass eine Änderung des Parameters möglicherweise nicht erforderlich ist. Weitere Informationen zu [!DNL Log Processing Mode.cfg] finden Sie unter [Zusätzliche Konfigurationsdateien](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Umwandlung {#section-02446744549940ada8eba0573ec5575f}

Jedes Mal, wenn Sie Informationen in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] ändern, z. B. eine Transformation ändern oder eine neue Dimension definieren, erfolgt die Transformation automatisch.

Jedes Mal, wenn Sie Lookup-Dateien ändern, auf die in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] (einschließlich Lookup-Dateien für [!DNL Categorize]-, [!DNL FlatFileLookup]- und [!DNL ODBCLookup]-Transformationen) verwiesen wird, müssen Sie die Transformation starten, indem Sie im Parameter &quot;Neu verarbeiten&quot;der Datei [!DNL Transformation.cfg] Zeichen oder Kombinationen von Zeichen eingeben und die Datei speichern.
