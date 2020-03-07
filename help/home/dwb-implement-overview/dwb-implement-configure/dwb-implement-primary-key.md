---
description: In diesem Abschnitt wird das Erstellen von primären Schlüsseln (Tracking-ID) für Data Workbench-Datensätze für Schemadesign und -implementierung erläutert.
title: Datenverarbeitung - Aufbau eines primären Schlüssels
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datenverarbeitung - Aufbau eines primären Schlüssels{#data-processing-building-primary-key}

In diesem Abschnitt wird das Erstellen von primären Schlüsseln (Tracking-ID) für Data Workbench-Datensätze für Schemadesign und -implementierung erläutert.

## Die Tracking-ID {#section-24683031044a4af49988655ccb9a45fd}

Nach dem Lesen und Dekodieren der Daten in DWB (mithilfe von Decodern) besteht der erste Schritt darin, die Verfolgungs-ID und den Zeitstempel zu definieren. Die Tracking-ID ist ein Bezeichner, der einen Kundendatensatz eindeutig identifiziert. Es kann sich um ein beliebiges Feld im Feed wie E-Mail-ID, Sozialversicherungsnummer, Cookie-ID usw. handeln. Das als Tracking-ID zu verwendende Feld wird vom Client während der Erkennungssitzung festgelegt. Tracking-ID und Zeitstempel sind obligatorische Felder und müssen für jeden Datensatz definiert werden.

Normalerweise wird für Online-Daten die Cookie-ID (Kombination aus *x-visid_high* und* x-visid_low*) als Standardmethode für die eindeutige Kundenidentifizierung verwendet. Dies kann jedoch entsprechend den Anforderungen des Kunden geändert werden. Das Datum und die Uhrzeit, zu der die Anforderung (oder das Ereignis) auftritt, sind *x-timestamp*. Alle Datensätze in DWB werden nach *trackingid* gruppiert und nach Zeitstempel sortiert. Die [!DNL Definitions.cfg] Datei &quot;Erforderliches Feld&quot;ist eine Datei mit dem Datenbestand zur Verarbeitung von Protokollen, in der die erforderlichen Felder definiert werden: *x-trackingid* und *x-timestamp*.

Hinweis: *x-trackingid *in DWB ist ein integriertes Feld und dieser Name sollte nicht für ein anderes Feld verwendet werden.

**Beispiel 1**: Erstellen von *x-trackingid* mit Cookie-ID (wenn nur Onlinedaten verwendet werden)

Um das *x-trackingid *in DWB mithilfe der Cookie-ID zu erstellen, verwenden Sie die Hash-Funktion, um das *x-trackingid* in der [!DNL foundation.cfg] Datei zu erstellen (es empfiehlt sich, die Verfolgungs-ID in zu definieren, [!DNL foundation.cfg] aber es kann in jeder anderen Konfigurationsdatei im [!DNL Dataset > log processing] Ordner definiert werden), wie im Folgenden gezeigt:

![](assets/dwb_impl_primary_key1.png)

**Beispiel 2**: Erstellen von *x-trackingid* mit E-Mail-ID (sofern Online- und Offlinedaten verfügbar sind)

Es wird davon ausgegangen, dass Offline- und Online-Daten verfügbar sind (in diesem Beispiel) und die E-Mail-ID in beiden Datenquellen verfügbar ist. Da die E-Mail-ID einen Kunden eindeutig identifiziert, wird sie zum Erstellen der *x-trackingid* verwendet.

Verwenden Sie die Hash-Funktion, um die *trackingId* wie folgt zu erstellen:

![](assets/dwb_impl_primary_key2.png)

