---
description: Informationen zu den Zeitzonencodes und -formaten.
solution: Analytics
title: Zeitzonencodes
topic: Data workbench
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zeitzonencodes{#time-zone-codes}

Informationen zu den Zeitzonencodes und -formaten.

Die meisten zeitbasierten Parameter im Data Workbench-Server werden im folgenden Format angegeben:

* Monat TT , JJJJ HH :MM :SS TZone
* Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) des folgenden Formats ausgedrückt:

* UTC +hhmm-Zeichen

Das Zeichen (+) kann entweder ein Plus- (+) oder ein Minuszeichen (-) sein, und hhmm ist der Offset von UTC in Stunden und Minuten. Die optionale Variable gibt einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zur Uhrzeitverschiebung an.

Wenn Sie Module angeben, [!DNL dstrules.dst] muss sich eine tabulatorgetrennte Datei mit dem Namen im Ordner &quot;Dataset\TimeZone&quot;entweder des [!DNL Base] Profils (für Konfigurationsdateien, die keinem bestimmten Datensatz zugeordnet sind) oder des Datensatzprofils (für Konfigurationsdateien, die dataset-spezifisch sind) befinden. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können unterschiedliche Regelsätze für verschiedene Jahre verwenden. In der [!DNL DST.dst] Datei, die Adobe im Profil bereitstellt, werden die [!DNL Base] Standardregeln der USA, die mit dem Energy Policy Act von 2005 (in Kraft seit 2007) festgelegt wurden, und die US-Regeln für frühere Jahre festgelegt.

Beispiele für Zeitzoneneinträge sind unten aufgeführt:

* Östliche Sommerzeit in den USA: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne Module (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone von Data Workbench-Server, Data Workbench und Report Computern nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven DataSet-Profile auf einem Data Workbench-Servercomputer nicht die gleiche Zeitzoneneinstellung haben.

Die folgende Tabelle enthält eine Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Tabelle mit Zeitzonencode {#section-b4f965b872c543e2ac52a3c94410d076}

Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechseln der Uhr implementieren, müssen Sie die [!DNL .dst] Datei mit den entsprechenden Regeln im Profilnamenverzeichnis auf dem Datenbasis-Server [!DNL \Dataset\Timezone] speichern.

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

