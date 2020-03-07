---
description: Wenn Sie die Kategorize- oder FlatFileLookup-Transformationen verwenden, wird die Suchtabelle im Arbeitsspeicher geladen und aus einer reduzierten Datei gefüllt, deren Speicherort Sie bei der Definition der Transformation angeben.
solution: Analytics
title: Ausfüllen der Suchtabelle
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ausfüllen der Suchtabelle{#populating-the-lookup-table}

Wenn Sie die Kategorize- oder FlatFileLookup-Transformationen verwenden, wird die Suchtabelle im Arbeitsspeicher geladen und aus einer reduzierten Datei gefüllt, deren Speicherort Sie bei der Definition der Transformation angeben.

Die angegebene einfache Datei muss die folgenden Anforderungen erfüllen:

* Jede Zeile in der Datei muss eine Zeile in der Suchtabelle darstellen.
* Spalten in der Datei müssen durch ein ASCII-Trennzeichen getrennt werden. Sie können jedes Zeichen verwenden, das kein Zeilenendezeichen ist und nicht an einer beliebigen Stelle in den Ereignisdaten selbst erscheint. Wenn Sie die Transformation definieren, geben Sie an, welches Zeichen verwendet wurde, um die Spalten in der flachen Datei zu trennen.

Wenn Sie eine [!DNL ODBCLookup] Transformation verwenden, wird die Suchtabelle in den Speicher geladen und aus einer Tabelle oder Ansicht in einer von Ihnen angegebenen [!DNL ODBC] Datenbank gefüllt. Wenn Sie die Transformation definieren, müssen Sie auch die Datenquelle, den Benutzernamen und das Kennwort angeben, die der Data Workbench-Server verwenden muss, um eine Verbindung zur Datenbank herzustellen.

>[!NOTE]
>
>Suchtabellen werden geladen, wenn der Data Workbench-Server anfänglich mit der Erstellung des Datensatzes beginnt. Nach der Einrichtung sollen Lookup-Dateien nicht mehr geändert werden. Wenn Sie die für die Konvertierungsphase verwendete reduzierte Datei oder [!DNL ODBC] Tabelle ändern, müssen Sie den gesamten Datensatz retransformieren. Wenn Sie eine einfache Datei ändern, die während der Protokollverarbeitung verwendet wird, werden die neuen Suchdaten auf alle neuen Datensätze angewendet, die den Datensatz eingeben. Die Änderungen werden jedoch nicht rückwirkend angewendet.

