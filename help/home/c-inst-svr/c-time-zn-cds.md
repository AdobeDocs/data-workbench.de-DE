---
description: Formatanweisungen zu zeitbasierten Parametern in Insight Server.
title: Zeitzonencodes
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# Zeitzonencodes{#time-zone-codes}

Formatanweisungen zu zeitbasierten Parametern in Insight Server.

Die meisten zeitbasierten Parameter in [!DNL Insight Server] sind im folgenden Format angegeben:

*Monat DD, JJJJ HH:MM:SS TimeZone*

Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) mit folgendem Format ausgedrückt:

UTC +hhmm *Strules*

Das Zeichen (+) kann entweder ein Plus- (+) oder ein Minuszeichen (-) sein, und *hhmm* ist der Offset von UTC in Stunden und Minuten. Die optionale Variable *desstrules* gibt einen Regelsatz an, um die Sommerzeit oder eine ähnliche Richtlinie zur Uhrzeitverschiebung zu implementieren.

Wenn Sie *Strings* angeben, muss eine tabulatorgetrennte Datei mit dem Namen *&lt; [!DNL dstrules]* [!DNL .dst] im Ordner Datensatz\TimeZone des Basisprofils (für Konfigurationsdateien, die nicht mit einem bestimmten Datensatz verknüpft sind) oder des Datensatzprofils (für Konfigurationsdateien, die datasetspezifisch sind) vorhanden sein. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können für verschiedene Jahre unterschiedliche Regeln haben. Die von der Adobe im Basisprofil bereitgestellte [!DNL DST.dst]-Datei enthält die US-Standardregeln, die durch das Energy Policy Act von 2005 (in Kraft seit 2007) festgelegt wurden, und die US-Vorschriften für frühere Jahre.

Nachfolgend finden Sie Beispiele für Zeitzoneneinträge:

* US Eastern Daylight Time: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und keine *Strules* (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone der Maschinen [!DNL Insight Server], [!DNL Insight] und [!DNL Report] nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven Datensatzprofile auf einem [!DNL Insight Server]-Computer nicht dieselbe Zeitzoneneinstellung haben.

Die folgende Tabelle enthält die Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Zeitzonen-Code-Tabelle {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechsel der Uhr implementieren, müssen Sie die Datei [!DNL .dst] mit den entsprechenden Regeln auf dem Computer *Profilname*\Dataset\Timezone directory on the [!DNL Insight Server] speichern.

| Code | Zeitzone | Versatz von GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Eastern Standard | 5 |
| bearbeiten | Eastern Daylight | 5 |
| cst | Central Standard | 6 |
| cdt | Zentraler Tageslicht | 6 |
| mst | Mountain Standard | 7 |
| mdt | Mountain Daylight | 7 |
| pst | Pacific Standard | 8 |
| pdt | Pacific Daylight | 8 |
