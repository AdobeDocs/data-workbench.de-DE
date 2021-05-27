---
description: Informationen zu den Zeitzonen-Codes und -Formaten.
title: Zeitzonencodes
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 5%

---

# Zeitzonencodes{#time-zone-codes}

Informationen zu den Zeitzonen-Codes und -Formaten.

Die meisten zeitbasierten Parameter im Data Workbench-Server sind im folgenden Format angegeben:

* Monat DD , JJJJ HH :MM :SS TZone
* Beispiel: 13. August 2013 22:30:00 EST

Zeitzonen werden in einem systemunabhängigen Zeitzonenformat (Coordinated Universal Time) mit folgendem Format ausgedrückt:

* UTC +hhmm-Module

Das Zeichen (+) kann ein Plus- (+) oder Minuszeichen (-) sein und hmm ist der Offset von UTC in Stunden und Minuten. Die optionale Variable gibt einen Regelsatz an, um die Sommerzeit oder eine ähnliche Richtlinie zur Uhrzeitverschiebung zu implementieren.

Wenn Sie Regeln angeben, muss im Verzeichnis Datensatz\TimeZone eine tabulatorgetrennte Datei mit dem Namen [!DNL dstrules.dst] entweder im Verzeichnis [!DNL Base] des Profils (für Konfigurationsdateien, die nicht mit einem bestimmten Datensatz verknüpft sind) oder im Datensatzprofil (für Konfigurationsdateien, die dataset-spezifisch sind) vorhanden sein. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können für verschiedene Jahre unterschiedliche Regeln haben. Die von der Adobe im Profil [!DNL Base] bereitgestellte [!DNL DST.dst]-Datei enthält die US-Standardregeln, die durch das Energy Policy Act von 2005 (in Kraft seit 2007) festgelegt wurden, und die US-Vorschriften für frühere Jahre.

Nachfolgend finden Sie Beispiele für Zeitzoneneinträge:

* US Eastern Daylight Time: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und keine Segmente (entspricht GMT): Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone von Data Workbench-Server, Data Workbench und Report Computern nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven Datensatzprofile auf einem Data Workbench-Server nicht dieselbe Zeitzoneneinstellung haben.

Die folgende Tabelle enthält die Liste der Codes, mit denen Sie Zeitzonen in zeitbasierten Parametern angeben können.

## Zeitzonen-Code-Tabelle {#section-b4f965b872c543e2ac52a3c94410d076}

Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechsel der Uhr implementieren, müssen Sie die Datei [!DNL .dst] mit den entsprechenden Regeln im Profilnamen [!DNL \Dataset\Timezone] auf dem Data Workbench-Servercomputer speichern.

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
