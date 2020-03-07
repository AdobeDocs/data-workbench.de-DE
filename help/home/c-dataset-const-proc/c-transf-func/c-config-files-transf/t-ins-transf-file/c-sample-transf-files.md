---
description: Informationen zum Angeben von Parametern in der Datei "Transform.cfg"basierend auf den verschiedenen Szenarien.
solution: Analytics
title: Beispiel für Data Workbench Transform.cfg-Dateien
topic: Data workbench
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Beispiel für Data Workbench Transform.cfg-Dateien{#sample-data-workbench-transform-cfg-files}

Informationen zum Angeben von Parametern in der Datei &quot;Transform.cfg&quot;basierend auf den verschiedenen Szenarien.

* [Eine einfache Insight Transform.cfg-Datei](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Ausgabe mit kommagetrennten Werten](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Beispielprotokolldateien](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Aufteilen von Protokolldateien nach Website-Abschnitten](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

In jedem Beispiel wird die Datei als [!DNL Transform.cfg] Fenster in Data Workbench angezeigt.

## Eine einfache Data Workbench Transform.cfg-Datei {#section-b7e83cafa3a947c597bd09d316930190}

Das folgende [!DNL Transform.cfg] Fenster enthält Anweisungen zum Lesen von [!DNL .vsl] Dateien aus dem [!DNL Logs] Ordner und zum Exportieren der Felder x-timestring und x-trackingid in eine Textdatei, die im Verzeichnis Logs\VT gespeichert ist. Da weder ein Zeitraum für die Dateidrehung noch ein Format für die Ausgabedatei angegeben ist, enthält jede Datei Daten für einen Kalendertag und hat einen Namen im Standardformat [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Ausgabe mit kommagetrennten Werten {#section-03916934ad574efc8695abbae54a1816}

Das folgende [!DNL Transform.cfg] Fenster enthält Anweisungen zum Lesen von [!DNL .vsl] Dateien aus dem Protokollordner und zum Exportieren der Felder 0 bis 13 in eine kommagetrennte ( [!DNL .csv]) Datei, die im Ordner &quot;Logs\VT\CSV directory&quot;gespeichert ist. Da kein Zeitraum für die Dateirotation angegeben ist, enthält jede Datei Daten für einen Kalendertag. Die Ausgabedateien sind [!DNL .csv] Dateien, die im Format benannt wurden [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Beispielprotokolldateien {#section-113b3b0c0c7547ea9536bb2f465c0875}

Sie können die Umwandlungsfunktion konfigurieren, um eine aktuelle, kompakte Version Ihrer vollständigen Protokolldateien zu erstellen und zu verwalten. Auf diese Weise können Sie Ihre DataSet-Konfigurationen schnell testen, mit Wiederverarbeitungszeiten von Sekunden oder Minuten anstelle von Stunden, die zur Neuverarbeitung des gesamten Datensatzes erforderlich sind. Das folgende Beispiel zeigt, wie Sie die Transformationsfunktion zu diesem Zweck konfigurieren.

Das folgende [!DNL Transform.cfg] Fenster enthält Anweisungen zum Lesen von [!DNL .vsl] Dateien aus dem Verzeichnis &quot;Protokolle&quot;und zum Exportieren der Felder &quot;x-timestring&quot;und &quot;x-trackingid&quot;in eine Textdatei, die im Verzeichnis &quot;Protokolle\VT&quot;gespeichert ist. Der angegebene Hash-Schwellenwert filtert bestimmte Tracking-IDs aus dem Datensatz, wodurch ein Datensatz erstellt wird, der mit einem Faktor von 100 gesampelt wird. Da kein Zeitraum für die Dateirotation angegeben ist, enthält jede Datei Daten für einen Kalendertag. Die Namen der Ausgabedateien haben das Standardformat [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Aufteilen von Protokolldateien nach Website-Abschnitten {#section-2cac205cd3934d31abb6c6ed8780196d}

Das folgende [!DNL Transform.cfg] Fenster enthält Anweisungen zum Lesen von [!DNL .vsl]Dateien aus dem Verzeichnis &quot;Protokolle&quot;und zum Exportieren der Felder &quot;x-timestring&quot;und &quot;x-trackingid&quot;in eine Textdatei, die im Verzeichnis &quot;Protokolle\VT&quot;gespeichert ist. Die Transformation ( [!DNL RETransform]) des regulären Ausdrucks nimmt als Eingabe das cs-uri-Stammfeld und erstellt ein neues Feld (x-site), das einen Abschnitt der Site definiert. Das Feld &quot;x-site&quot;ist im Namen der Ausgabetextdateien enthalten, die jeweils Daten eines Kalendertages enthalten.

![](assets/cfg_VisualTransform_SplittingExample.png)

