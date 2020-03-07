---
description: Links zu weiteren Informationen über bestimmte Parameter in der Datei "Log Processing.cfg".
solution: Analytics
title: Verarbeitungsparameter protokollieren
topic: Data workbench
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Verarbeitungsparameter protokollieren{#log-processing-parameters}

Links zu weiteren Informationen über bestimmte Parameter in der Datei &quot;Log Processing.cfg&quot;.

<!--
c_data_filters.xml
-->

## Datenfilter {#data-filters}

Die in der [!DNL Log Processing.cfg] Datei definierten Filter umfassen Folgendes:

* Endzeit
* Hashschwellenwert
* Startzeit

Die von diesen Parametern definierte Filterung erfolgt, nachdem Protokolleinträge die Dekodierer verlassen und nach Transformationen, aber vor deren Auswertung durch die [!DNL Log Entry Condition]. Im Allgemeinen führt eine Änderung dieser Parameter zu Änderungen der Zusammensetzung des Datensatzes.

Die empfohlene Methode für die Verwendung von [!DNL Sensor] Datenquellen zum Erstellen eines Datensatzes, der einen bestimmten Zeitraum abdeckt, ist die Verwendung der Parameter &quot;Startzeit&quot;und &quot;Endzeit&quot;für den Datensatz.

Die Verwendung der Parameter &quot;Startzeit&quot;und &quot;Endzeit&quot;wird anderen Verfahren vorgezogen, z. B. dem Verschieben von Protokolldateien, um sie nach Ordner zu trennen. Durch Festlegen der Start- und Endzeiten für den Datensatz verwendet der Data Workbench-Server automatisch nur die Protokolleinträge, die innerhalb des angegebenen Intervalls erfolgten. Wenn die Endzeit in der Vergangenheit liegt, aktualisiert der Data Workbench-Server den Datensatz in der Regel mit demselben Satz von Protokolleinträgen, selbst wenn der Datensatz beispielsweise durch Hinzufügen einer neuen Transformation aktualisiert wird.

<!--
c_log_entry_con.xml
-->

## Protokolleintrag

Im Wesentlichen handelt es sich dabei um einen Filtervorgang für die verfügbaren Protokolleinträge. Wenn der Wert false [!DNL Log Entry Condition] zurückgibt, wird der Protokolleintrag aus dem verfügbaren Satz der Protokolleinträge herausgefiltert.

Die [!DNL Log Entry Condition] wird mithilfe von Bedingungsvorgängen (siehe [Bedingungen](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) beschrieben und kann jedes der Eingabefelder verwenden, die von [!DNL Sensor] (siehe *Data Workbench-[!DNL Sensor]Handbuch* ) erfasst werden, oder alle erweiterten Felder, die durch in der [!DNL Log Processing.cfg] Datei enthaltene Transformationen erzeugt werden, um die Testbedingungen zu definieren. [!DNL Log Entry] werden während der Protokollverarbeitung angewendet und können optional während der Transformation angewendet werden.

Dieses Beispiel zeigt die Verwendung der [!DNL log entry condition] für Website-Daten. Sie können die verwenden, [!DNL Log Entry Condition] um Datensätze zu erstellen, die sich auf einen bestimmten Teil der Website oder auf Besucher konzentrieren, die bestimmte Aktionen auf der Site ausführen.

Das Beispiel [!DNL Log Entry Condition] in diesem Beispiel erstellt einen Datensatz, der nur die Protokolleinträge enthält, die Teil des Site-Speichers sind. Wenn Sie die Variable [!DNL RECondition test] mit dem entsprechenden Muster [!DNL "/store/.*"] und das [!DNL cs-uri-stem] [!DNL "/store/"] Feld als Eingabe für den regulären Ausdruck verwenden, werden nur Webseiten, die mit der Zeichenfolge beginnen, in den Datensatz aufgenommen.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Schlüsseltrennung {#key-split}

Die Anzahl der Tracking-IDs im Datensatz wird künstlich erhöht, aber die Gesamtzahl der vom Data Workbench-Server verarbeiteten Protokolleinträge wird nicht künstlich erhöht, wodurch die Gesamtzahl der zählbaren Ereignisse im Datensatz erhalten bleibt. Nachdem die Daten für ein einzelnes Element aufgeteilt wurden, sind die Daten für immer mit zwei verschiedenen Tracking-IDs verknüpft und können nicht zugeordnet werden.

Wenn Sie beispielsweise mit Webdaten arbeiten, stellt jede Tracking-ID einen individuellen Besucher dar. Wenn Sie die Schlüsselaufteilung aktivieren, werden die Besucher im Datensatz mit großen Mengen von Ereignisdaten in mehrere Besucher aufgeteilt. Während die Anzahl der Besucher im Datensatz künstlich erhöht wird, wird die Gesamtzahl zählbarer Ereignisse wie Seitenansichten oder Buchungen nicht künstlich erhöht. Nach der Aufteilung können die Daten für die Unterbesucher nicht zugeordnet werden.

Schlüsselaufteilung verwendet einen probabilistischen Algorithmus. Infolgedessen gibt es einen Kompromiss zwischen der Speicherbelegung, der Ausfallwahrscheinlichkeit, dem Schwellenwert für die Schlüsselaufteilung ( [!DNL Split Key Bytes]) und der Datensatzgröße. Bei den empfohlenen Einstellungen (wie unten aufgeführt) ist die Fehlerquote niedrig. Von den Elementen, deren Ereignisdaten den Schwellenwert für die Schlüsselaufteilung überschreiten, werden etwa 1 von 22.000 (in der Regel weniger als 1 pro Datensatz) Daten eher abgeschnitten als aufgeteilt.

Die empfohlenen Werte für jeden Parameter (ohne und mit Schlüsselaufteilung) sind in der folgenden Tabelle aufgeführt.

| Parameter | Keine Schlüsselaufteilung | Schlüsselaufteilung |
|---|---|---|
| Gruppen - Maximale Schlüsselbyte | 1e6 | 2e6 |
| Schlüsselraum teilen | 6e6 | 6e6 |
| Schlüsselbyte teilen | 0 | 1e6 |
| Schlüsselabstand teilen | 10 | 10 |

[!DNL Group Maximum Key Bytes] gibt die maximale Anzahl von Ereignisdaten an, die für eine einzelne Tracking-ID verarbeitet werden können. Daten, die diesen Grenzwert überschreiten, werden aus dem Dataset-Aufbau gefiltert. [!DNL Split Key Bytes] die Anzahl der Bytes, bei denen eine einzelne Tracking-ID in mehrere Elemente aufgeteilt wird. Elemente werden entsprechend einer Wahrscheinlichkeitsverteilung bei etwa dieser Anzahl von Byte aufgeteilt. [!DNL Split Key Space Ratio] und [!DNL Split Key Bucket Space] steuern Sie die Speicherauslastung und die Ausfallrate der Tastenaufteilung.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]und [!DNL Split Key Bucket Space] alle müssen deklariert werden, damit die Schlüsselteilung ordnungsgemäß funktioniert. Ändern Sie die Werte dieser Parameter nur nach Rücksprache mit Adobe.

