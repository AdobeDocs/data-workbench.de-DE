---
description: Data Workbench bietet eine Reihe von Umwandlungen, mit denen der Data Workbench-Server Suchdaten in den Datensatz integrieren kann.
title: Integration von Lookup-Daten
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Integration von Lookup-Daten{#integrating-lookup-data}

Data Workbench bietet eine Reihe von Umwandlungen, mit denen der Data Workbench-Server Suchdaten in den Datensatz integrieren kann.

Suchdaten sind externe Daten aus Unternehmensdatenbanken oder Lookup-Dateien, die Sie mit Ereignisdaten kombinieren können, um den Datensatz zu erstellen. Im Allgemeinen verwenden Sie Suchdaten, um die Ereignisdaten aus Ihren Protokollquellen zu erweitern. Grundsätzlich können Sie sich vorstellen, mithilfe von Lookup-Daten Ereignisdatensätze mit zusätzlichen Informationsspalten zu füllen.

Wenn Sie Suchdaten verwenden, laden Sie die Daten in eine speicherresidente Suchtabelle. Eine Spalte in der Tabelle muss einen gemeinsamen Schlüssel enthalten, der auch in den Ereignisdatensätzen vorhanden ist. Die Daten in der Suchtabelle selbst können aus einer reduzierten Datei oder aus einer ODBC-Datenquelle geladen werden. Suchdaten können während der Protokollverarbeitungs- oder Transformationsphase des Datensatzerstellungsprozesses in den Datensatz integriert werden.

Um Lookup-Daten zu integrieren, müssen Sie zunächst eine Lookup-Datei generieren oder über die für den Zugriff auf eine SQL-Datenbank erforderlichen Informationen verfügen und dann eine oder mehrere der folgenden Transformationen in den Datensatzkonfigurationsdateien für die Protokollverarbeitung und -umwandlung definieren.

**So integrieren Sie Suchdaten in den Datensatz**

1. Erstellen Sie Ihre Lookup-Datei. Siehe [Ausfüllen der Suchtabelle](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Definieren Sie einen der folgenden Umwandlungstypen im Parameter &quot;Umwandlungen&quot;in der entsprechenden Datensatzkonfigurationsdatei:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Beachten Sie, dass die Umwandlung von [!DNL ODBCLookup] nur funktioniert, wenn sie in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] definiert ist.
