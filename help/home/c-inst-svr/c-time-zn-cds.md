---
description: Formatieren Sie Anweisungen zu zeitbasierten Parametern in Insight Server.
solution: Insight
title: Zeitzonencodes
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zeitzonencodes{#time-zone-codes}

Formatieren Sie Anweisungen zu zeitbasierten Parametern in Insight Server.

Die meisten zeitbasierten Parameter in [!DNL Insight Server] folgendem Format:

*Monat TT, JJJJ HH:MM:SS-Zeitzone*

Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) des folgenden Formats ausgedrückt:

UTC +hhmm- *Module*

Das Zeichen (+) kann entweder ein Pluszeichen (+) oder ein Minuszeichen (-) sein, und *hhmm* ist der Offset von UTC in Stunden und Minuten. Die optionalen Variablen *beschreiben* einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zum Uhrzeitwechsel.

Wenn Sie *Module* angeben, muss sich im Ordner &quot;Dataset\TimeZone&quot;eine tabulatorgetrennte Datei mit dem Namen *&lt;[!DNL dstrules]>* [!DNL .dst] befinden, entweder im Basisprofil (für Konfigurationsdateien, die keinem bestimmten Datensatz zugeordnet sind) oder im Datenasetprofil (für Konfigurationsdateien, die dataset-spezifisch sind). Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können unterschiedliche Regelsätze für verschiedene Jahre verwenden. Die von Adobe im Basisprofil bereitgestellte [!DNL DST.dst] Datei legt die Standardregeln der USA fest, die mit dem Energy Policy Act von 2005 (in Kraft seit 2007) und den US-Regeln für frühere Jahre festgelegt wurden.

Beispiele für Zeitzoneneinträge sind unten aufgeführt:

* Östliche Sommerzeit in den USA: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne *Module* (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone von [!DNL Insight Server], [!DNL Insight]und [!DNL Report] Computern nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven Datensatzprofile auf einem [!DNL Insight Server] Computer nicht über die gleiche Zeitzoneneinstellung verfügen.

Die folgende Tabelle enthält eine Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Tabelle mit Zeitzonencode {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechseln der Uhr implementieren, müssen Sie die [!DNL .dst] Datei mit den entsprechenden Regeln im *Profilnamen*\Dataset\Timezone directory on the [!DNL Insight Server] speichern.

| Code | Zeitzone | Versatz aus GMT |
|---|---|---|
| gmt | Greenwich-Mittel | 0 |
| est | Eastern Standard | 5 |
| edt | Eastern Daylight | 5 |
| cst | Central Standard | 6 |
| cdt | Central Daylight | 6 |
| mst | Gebirgsstandard | 7 |
| mdt | Mountain Daylight | 7 |
| pst | Pacific Standard | 8 |
| pdt | Pacific Daylight | 8 |
