---
description: Wenn Sie die Kategorize- oder FlatFileLookup-Transformationen verwenden, wird die Suchtabelle im Arbeitsspeicher geladen und aus einer reduzierten Datei gefüllt, deren Speicherort Sie bei der Definition der Transformation angeben.
title: Befüllen der Lookup-Tabelle
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Befüllen der Lookup-Tabelle{#populating-the-lookup-table}

Wenn Sie die Kategorize- oder FlatFileLookup-Transformationen verwenden, wird die Suchtabelle im Arbeitsspeicher geladen und aus einer reduzierten Datei gefüllt, deren Speicherort Sie bei der Definition der Transformation angeben.

Die angegebene einfache Datei muss die folgenden Anforderungen erfüllen:

* Jede Zeile in der Datei muss eine Zeile in der Suchtabelle darstellen.
* Spalten in der Datei müssen durch ein ASCII-Trennzeichen getrennt werden. Sie können jedes Zeichen verwenden, das kein Zeilenendezeichen ist und nicht an einer beliebigen Stelle in den Ereignis-Daten angezeigt wird. Wenn Sie die Transformation definieren, geben Sie an, welches Zeichen verwendet wurde, um die Spalten in der flachen Datei zu trennen.

Wenn Sie eine [!DNL ODBCLookup]-Transformation verwenden, wird die Suchtabelle in den Speicher geladen und aus einer Tabelle oder Ansicht in einer von Ihnen angegebenen [!DNL ODBC]-Datenbank gefüllt. Wenn Sie die Transformation definieren, müssen Sie auch die Datenquelle, den Benutzernamen und das Kennwort angeben, die der Data Workbench-Server verwenden muss, um eine Verbindung zur Datenbank herzustellen.

>[!NOTE]
>
>Suchtabellen werden geladen, wenn der Data Workbench-Server anfänglich mit der Erstellung des Datensatzes beginnt. Nach der Einrichtung sollen Lookup-Dateien nicht mehr geändert werden. Wenn Sie die reduzierte Datei oder die [!DNL ODBC]-Tabelle ändern, die für die Konvertierungsphase verwendet wird, müssen Sie den gesamten Datensatz neu transformieren. Wenn Sie eine einfache Datei ändern, die während der Protokollverarbeitung verwendet wird, werden die neuen Suchdaten auf alle neuen Datensätze angewendet, die den Datensatz eingeben. Die Änderungen werden jedoch nicht rückwirkend angewendet.
