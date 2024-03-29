---
description: Während der Wiederaufbereitung rekonstruiert der Data Workbench-Server Ihren Datensatz wie in den Konfigurationsdateien für die Protokollverarbeitung und Umwandlung von Datensätzen angegeben.
title: Grundlagen zur Wiederaufbereitung und erneuten Umwandlung
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Grundlagen zur Wiederaufbereitung und erneuten Umwandlung{#understanding-reprocessing-and-retransformation}

{{eol}}

Während der Wiederaufbereitung rekonstruiert der Data Workbench-Server Ihren Datensatz wie in den Konfigurationsdateien für die Protokollverarbeitung und Umwandlung von Datensätzen angegeben.

Dazu muss der Data Workbench-Server (InsightServer64.exe) sowohl die Protokollverarbeitungsphase als auch die Transformationsphase der Datensatzerstellung abschließen. Wenn die Protokollverarbeitung abgeschlossen ist, erfolgt die Umwandlung des Triggers automatisch, die Umwandlung kann jedoch auch unabhängig von der Protokollverarbeitung erfolgen.

Während der Protokollverarbeitungsphase haben Benutzer von Data Workbench keinen Zugriff auf die Daten im Datensatz. Während der Transformationsphase haben Benutzer von Data Workbench Zugriff auf aktuelle Daten, aber die Daten werden gesampelt und nicht vollständig. Die Datenanalyse kann während der Transformation fortgesetzt werden, Abfragen werden jedoch nur so schnell abgeschlossen, wie die Transformation erfolgt.

## Wiederaufbereitung {#section-92f1e46bf1534b3dba39e9493190b8ab}

Jedes Mal, wenn Sie eine der folgenden Aufgaben ausführen, erfolgt die Protokollverarbeitung und daher die Transformation automatisch, um Ihren Datensatz wie in den Datensatzkonfigurationsdateien angegeben neu zu konstruieren:

* Fügen Sie eine neue Datenquelle hinzu.
* Fügen Sie Ihrem Cluster im Ordner [!DNL Profile.cfg] -Datei.
* Ändern Sie die [!DNL Cluster.cfg] -Datei.
* Ändern Sie die [!DNL Log Processing.cfg] oder [!DNL Log Processing Dataset Include] -Datei, einschließlich, aber nicht beschränkt auf Folgendes:

   * Neuen Parameter hinzufügen
   * Umwandlung ändern
   * Ändern der Parameter &quot;Startzeit&quot;oder &quot;Endzeit&quot;

* Upgrade durchführen [!DNL Insight Server.exe] -Datei.

Sie können die Neuverarbeitung auch jederzeit starten, indem Sie ein beliebiges Zeichen oder eine beliebige Zeichenkombination in den Parameter Neuverarbeitung der [!DNL Log Processing.cfg] und speichern Sie die Datei.

>[!NOTE]
>
>Damit eine erneute Verarbeitung erfolgt, muss der Parameter Pause im [!DNL Log Processing Mode.cfg] muss auf false gesetzt werden. Der Standardwert dieses Parameters lautet &quot;false&quot;(falsch). Daher ist eine Änderung des Parameters möglicherweise nicht erforderlich. Weitere Informationen finden Sie unter [!DNL Log Processing Mode.cfg], siehe [Zusätzliche Konfigurationsdateien](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Umwandlung {#section-02446744549940ada8eba0573ec5575f}

Jedes Mal, wenn Sie Informationen in [!DNL Transformation.cfg] oder in einer [!DNL Transformation Dataset Include] -Datei, z. B. eine Umwandlung ändern oder eine neue Dimension definieren, erfolgt die Umwandlung automatisch.

Jedes Mal, wenn Sie Lookup-Dateien ändern, auf die im [!DNL Transformation.cfg] oder in einer [!DNL Transformation Dataset Include] -Datei (einschließlich Lookup-Dateien für [!DNL Categorize], [!DNL FlatFileLookup]und [!DNL ODBCLookup] Transformationen), müssen Sie die Transformation initiieren, indem Sie ein beliebiges Zeichen oder eine beliebige Zeichenkombination in den Parameter Neuverarbeitung des [!DNL Transformation.cfg] und speichern Sie die Datei.
