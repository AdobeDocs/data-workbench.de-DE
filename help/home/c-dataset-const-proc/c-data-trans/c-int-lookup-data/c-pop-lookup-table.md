---
description: Wenn Sie die Transformationen Kategorize oder FlatFileLookup verwenden, wird die Suchtabelle im Speicher geladen und aus einer flachen Datei gefüllt, deren Speicherort Sie beim Definieren der Transformation angeben.
title: Befüllen der Lookup-Tabelle
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Befüllen der Lookup-Tabelle{#populating-the-lookup-table}

{{eol}}

Wenn Sie die Transformationen Kategorize oder FlatFileLookup verwenden, wird die Suchtabelle im Speicher geladen und aus einer flachen Datei gefüllt, deren Speicherort Sie beim Definieren der Transformation angeben.

Die von Ihnen angegebene reduzierte Datei muss die folgenden Anforderungen erfüllen:

* Jede Zeile in der Datei muss eine Zeile in der Suchtabelle darstellen.
* Die Spalten in der Datei müssen durch ein ASCII-Trennzeichen getrennt werden. Sie können beliebige Zeichen verwenden, die kein Zeilenendezeichen sind und an keiner Stelle in den Ereignisdaten selbst erscheinen. Wenn Sie die Umwandlung definieren, geben Sie an, mit welchem Zeichen die Spalten in der flachen Datei getrennt werden sollen.

Wenn Sie [!DNL ODBCLookup] Transformation, wird die Suchtabelle in den Speicher geladen und aus einer Tabelle oder Ansicht in einer [!DNL ODBC] -Datenbank, die Sie angeben. Bei der Definition der Transformation müssen Sie auch die Datenquelle, den Benutzernamen und das Kennwort angeben, die der Data Workbench-Server verwenden muss, um eine Verbindung zur Datenbank herzustellen.

>[!NOTE]
>
>Suchtabellen werden geladen, wenn der Data Workbench-Server mit der Erstellung des Datensatzes anfänglich beginnt. Nach der Erstellung sollen Lookup-Dateien nicht mehr geändert werden. Wenn Sie die reduzierte Datei ändern, oder [!DNL ODBC] -Tabelle, die für die Transformationsphase verwendet wird, müssen Sie den gesamten Datensatz umtransformieren. Wenn Sie eine flache Datei ändern, die während der Protokollverarbeitungsphase verwendet wird, werden die neuen Lookup-Daten auf alle neuen Datensätze angewendet, die in den Datensatz eingegeben werden. Die Änderungen werden jedoch nicht rückwirkend angewendet.
