---
description: Informationen zu den Zeitzonencodes und -formaten.
title: Zeitzonencodes
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 5%

---

# Zeitzonencodes{#time-zone-codes}

Informationen zu den Zeitzonencodes und -formaten.

Die meisten zeitbasierten Parameter im Data Workbench-Server werden im folgenden Format angegeben:

* Monat TT , JJJJ HH :MM :SS TZone
* Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) des folgenden Formats ausgedrückt:

* UTC +hhmm-Zeichen

Das Zeichen (+) kann entweder ein Plus- (+) oder ein Minuszeichen (-) sein, und hhmm ist der Offset von UTC in Stunden und Minuten. Die optionale Variable gibt einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zur Uhrzeitverschiebung an.

Wenn Sie Module angeben, muss im Ordner &quot;DataSet\TimeZone&quot;des Profils [!DNL Base] (für Konfigurationsdateien, die keinem bestimmten Datensatz zugeordnet sind) oder im DataSet-Profil (für Konfigurationsdateien, die dataset-spezifisch sind) eine tabulatorgetrennte Datei mit dem Namen [!DNL dstrules.dst] vorhanden sein. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können unterschiedliche Regelsätze für verschiedene Jahre verwenden. Die [!DNL DST.dst]-Datei, die durch die Adobe im [!DNL Base]-Profil bereitgestellt wird, gibt die Standardregeln an, die in den USA durch das Energy Policy Act von 2005 (ab 2007) festgelegt wurden, und die US-amerikanischen Vorschriften für Vorjahre.

Beispiele für Zeitzoneneinträge sind unten aufgeführt:

* Östliche Sommerzeit in den USA: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne Module (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone von Data Workbench-Server, Data Workbench und Report Computern nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven DataSet-Profil auf einem Data Workbench-Servercomputer nicht über die gleiche Zeitzoneneinstellung verfügen.

Die folgende Tabelle enthält die Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Zeitzonencode-Tabelle {#section-b4f965b872c543e2ac52a3c94410d076}

Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechseln der Uhr implementieren, müssen Sie die [!DNL .dst]-Datei mit den entsprechenden Profilen im Ordner [!DNL \Dataset\Timezone] auf dem Datenbasis-Servercomputer speichern.

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
