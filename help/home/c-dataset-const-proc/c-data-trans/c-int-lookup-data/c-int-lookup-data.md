---
description: Data Workbench stellt eine Reihe von Transformationen bereit, die es dem Data Workbench-Server ermöglichen, Suchdaten in den Datensatz zu integrieren.
solution: Analytics
title: Integration von Suchdaten
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integration von Suchdaten{#integrating-lookup-data}

Data Workbench stellt eine Reihe von Transformationen bereit, die es dem Data Workbench-Server ermöglichen, Suchdaten in den Datensatz zu integrieren.

Suchdaten sind externe Daten aus Unternehmensdatenbanken oder Lookup-Dateien, die Sie mit Ereignisdaten kombinieren können, um den Datensatz zu erstellen. Im Allgemeinen verwenden Sie Suchdaten, um die Ereignisdaten aus Ihren Protokollquellen zu erweitern. Es ist denkbar, dass Sie mithilfe von Suchdaten Ereignisdatensätze mit zusätzlichen Informationsspalten füllen können.

Wenn Sie Nachschlagedaten verwenden, laden Sie die Daten in eine speicherresidente Nachschlagetabelle. Eine Spalte in der Tabelle muss einen gemeinsamen Schlüssel enthalten, der auch in den Ereignisdatensätzen vorhanden ist. Die Daten in der Suchtabelle können aus einer einfachen Datei oder aus einer ODBC-Datenquelle geladen werden. Suchdaten können während der Protokollverarbeitung oder Umwandlungsphase des Datensatzentwurfs in den Datensatz aufgenommen werden.

Zur Integration von Nachschlagedaten müssen Sie zunächst eine Nachschlagedatei erstellen oder über die für den Zugriff auf eine SQL-Datenbank erforderlichen Informationen verfügen. Anschließend müssen Sie eine oder mehrere der folgenden Transformationen in den Konfigurationsdateien des Datensatzes für die Protokollverarbeitung und -verarbeitung definieren.

**So integrieren Sie Suchdaten in den Datensatz**

1. Erstellen Sie Ihre Lookup-Datei. Siehe [Füllen der Suchtabelle](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Definieren Sie eine der folgenden Arten von Transformationen im Parameter &quot;Transformations&quot;in der entsprechenden Datensatzkonfigurationsdatei:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Beachten Sie, dass die [!DNL ODBCLookup] Transformation nur funktioniert, wenn sie in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definiert ist.

