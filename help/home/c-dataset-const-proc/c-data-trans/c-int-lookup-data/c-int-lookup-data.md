---
description: Data Workbench stellt eine Reihe von Transformationen bereit, die es dem Data Workbench-Server ermöglichen, Suchdaten in den Datensatz zu integrieren.
title: Integration von Lookup-Daten
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Integration von Lookup-Daten{#integrating-lookup-data}

Data Workbench stellt eine Reihe von Transformationen bereit, die es dem Data Workbench-Server ermöglichen, Suchdaten in den Datensatz zu integrieren.

Nachschlagedaten sind externe Daten aus Unternehmensdatenbanken oder Nachschlagedateien, die Sie mit Ereignis-Daten kombinieren können, um den Datensatz zu erstellen. Im Allgemeinen verwenden Sie Suchdaten, um die Ereignis-Daten aus Ihren Protokollquellen zu erweitern. Grundsätzlich können Sie sich vorstellen, mithilfe von Suchdaten Ereignis-Datendatensätze mit zusätzlichen Informationsspalten zu füllen.

Wenn Sie Nachschlagedaten verwenden, laden Sie die Daten in eine speicherresidente Nachschlagetabelle. Eine Tabellenspalte muss einen gemeinsamen Schlüssel enthalten, der auch in den Ereignis-Datendatensätzen vorhanden ist. Die Daten in der Suchtabelle können aus einer einfachen Datei oder aus einer ODBC-Datenquelle geladen werden. Suchdaten können während der Protokollverarbeitung oder Umwandlungsphase des Datensatzentwurfs in den Datensatz aufgenommen werden.

Zur Integration von Nachschlagedaten müssen Sie zunächst eine Nachschlagedatei erstellen oder über die für den Zugriff auf eine SQL-Datenbank erforderlichen Informationen verfügen. Anschließend müssen Sie eine oder mehrere der folgenden Transformationen in den Konfigurationsdateien des Datensatzes für die Protokollverarbeitung und -verarbeitung definieren.

**So integrieren Sie Suchdaten in den Datensatz**

1. Erstellen Sie Ihre Lookup-Datei. Siehe [Ausfüllen der Suchtabelle](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Definieren Sie eine der folgenden Arten von Transformationen im Parameter &quot;Transformations&quot;in der entsprechenden Datensatzkonfigurationsdatei:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Beachten Sie, dass die Transformation [!DNL ODBCLookup] nur funktioniert, wenn sie in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] definiert ist.
