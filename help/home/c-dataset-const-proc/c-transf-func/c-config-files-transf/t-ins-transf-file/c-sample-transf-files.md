---
description: Informationen zum Angeben von Parametern in der Datei "Transform.cfg"basierend auf den verschiedenen Szenarien.
title: Beispiele für Data Workbench Transform.cfg-Dateien
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Beispiele für Data Workbench Transform.cfg-Dateien{#sample-data-workbench-transform-cfg-files}

{{eol}}

Informationen zum Angeben von Parametern in der Datei &quot;Transform.cfg&quot;basierend auf den verschiedenen Szenarien.

* [Einfache Insight-Datei &quot;Transform.cfg&quot;](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Ausgabe mit kommagetrennten Werten](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Beispielhafte Protokolldateien](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Aufteilen von Protokolldateien nach Website-Abschnitten](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

In jedem Beispiel wird die Datei als [!DNL Transform.cfg] in Data Workbench angezeigt.

## Einfache Data Workbench Transform.cfg-Datei {#section-b7e83cafa3a947c597bd09d316930190}

Folgendes [!DNL Transform.cfg] enthält Anweisungen zum Lesen [!DNL .vsl] -Dateien aus [!DNL Logs] und exportieren Sie die Felder x-timestring und x-trackingid in eine Textdatei, die im Verzeichnis Logs\VT gespeichert ist. Da weder ein Zeitraum für die Dateirotation noch ein Format für den Dateinamen angegeben ist, enthält jede Datei Daten für einen Kalendertag und hat einen Namen im Standardformat [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Ausgabe mit kommagetrennten Werten {#section-03916934ad574efc8695abbae54a1816}

Folgendes [!DNL Transform.cfg] enthält Anweisungen zum Lesen [!DNL .vsl] Dateien aus dem Verzeichnis Protokolle und exportieren Sie die Felder 0 bis 13 in ein kommagetrenntes ( [!DNL .csv]) im Verzeichnis Logs\VT\CSV gespeichert. Da kein Zeitraum für die Dateirotation angegeben ist, enthält jede Datei Daten für einen Kalendertag. Die Ausgabedateien sind [!DNL .csv] Dateien mit dem Namen im Format [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Beispielprotokolldateien {#section-113b3b0c0c7547ea9536bb2f465c0875}

Sie können die Umwandlungsfunktion konfigurieren, um eine aktuelle, kompakte Version Ihrer vollständigen Protokolldateien zu erstellen und zu verwalten. Auf diese Weise können Sie Ihre Datensatzkonfigurationen schnell testen, wobei die Neuverarbeitung von Sekunden oder Minuten anstatt Stunden erforderlich ist, um den gesamten Datensatz erneut zu verarbeiten. Das folgende Beispiel zeigt, wie die Umwandlungsfunktion dazu konfiguriert werden kann.

Folgendes [!DNL Transform.cfg] enthält Anweisungen zum Lesen [!DNL .vsl] -Dateien aus dem Verzeichnis Protokolle und exportieren Sie die Felder x-timestring und x-trackingid in eine Textdatei, die im Verzeichnis Logs\VT gespeichert ist. Der angegebene Hash-Schwellenwert filtert bestimmte Tracking-IDs aus dem Datensatz und erstellt so einen Datensatz, der mit dem Faktor 100 gesampelt wird. Da kein Zeitraum für die Dateirotation angegeben ist, enthält jede Datei Daten für einen Kalendertag. Die Namen der Ausgabedateien sind im Standardformat [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Aufteilen von Protokolldateien nach Website-Abschnitten {#section-2cac205cd3934d31abb6c6ed8780196d}

Folgendes [!DNL Transform.cfg] enthält Anweisungen zum Lesen [!DNL .vsl]-Dateien aus dem Verzeichnis Protokolle und exportieren Sie die Felder x-timestring und x-trackingid in eine Textdatei, die im Verzeichnis Logs\VT gespeichert ist. Die Umwandlung regulärer Ausdrücke ( [!DNL RETransform]) nimmt als Eingabe das Feld cs-uri-stamm und erstellt ein neues Feld (x-site), das einen Abschnitt der Site definiert. Das Feld x-site ist im Namen der Ausgabetextdateien enthalten, die jeweils Daten für einen Kalendertag enthalten.

![](assets/cfg_VisualTransform_SplittingExample.png)
