---
description: Formatanweisungen zu zeitbasierten Parametern in Insight Server.
title: Zeitzonencodes (Insight Server)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# Zeitzonencodes{#time-zone-codes}

{{eol}}

Formatanweisungen zu zeitbasierten Parametern in Insight Server.

Die meisten zeitbasierten Parameter in [!DNL Insight Server] werden im folgenden Format angegeben:

*Monat DD, JJJJ HH:MM:SStimeZone*

Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) mit folgendem Format ausgedrückt:

UTC +hhmm *dstrules*

Das Zeichen (+) kann ein Pluszeichen (+) oder ein Minuszeichen (-) sein und *hhmm* ist der Offset von UTC in Stunden und Minuten. Die optionale Variable *dstrules* gibt einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zur Uhrzeitverschiebung an.

Wenn Sie *dstrules*, eine tabulatorgetrennte Datei mit dem Namen *&lt; [!DNL dstrules]>* [!DNL .dst] muss im Ordner &quot;Dataset\TimeZone&quot;des Basisprofils (für Konfigurationsdateien, die nicht mit einem bestimmten Datensatz verknüpft sind) oder des Datensatzprofils (für Konfigurationsdateien, die dataset-spezifisch sind) vorhanden sein. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können für verschiedene Jahre unterschiedliche Regeln haben. Die [!DNL DST.dst] -Datei, die von der Adobe im Basisprofil bereitgestellt wird, die Standardregeln der USA, die durch das Energy Policy Act von 2005 (in Kraft seit 2007) festgelegt wurden, und die US-Vorschriften für frühere Jahre.

Nachfolgend finden Sie Beispiele für Zeitzoneneinträge:

* US Eastern Daylight Time: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Versatz und keine *dstrules* (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, wird die Systemzeitzone von [!DNL Insight Server], [!DNL Insight]und [!DNL Report] -Maschinen müssen nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus beziehen sich alle aktiven Datensatzprofile auf eine [!DNL Insight Server] Die Zeitzoneneinstellung für die Maschine muss nicht identisch sein.

Die folgende Tabelle enthält die Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Zeitzonen-Code-Tabelle {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Wenn Sie die Sommerzeit oder eine ähnliche Uhrzeitverschiebungspolitik implementieren, müssen Sie die [!DNL .dst] -Datei, die die entsprechenden Regeln im *Profilname*\Datensatz\Zeitzone im Ordner [!DNL Insight Server] Maschine.

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
