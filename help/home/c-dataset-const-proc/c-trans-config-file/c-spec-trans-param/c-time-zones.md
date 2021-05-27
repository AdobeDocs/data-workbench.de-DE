---
description: Der Parameter "Zeitzone"in der Datei "Transformation.cfg"steuert Zeitdimensionen, Zeitkonversionen (z. B. das Feld x-local-timestring ) und die Formatierung aller lokalen Zeiten im Datensatzprofil.
title: Zeitzonen
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Zeitzonen{#time-zones}

Der Parameter &quot;Zeitzone&quot;in der Datei &quot;Transformation.cfg&quot;steuert Zeitdimensionen, Zeitkonversionen (z. B. das Feld x-local-timestring ) und die Formatierung aller lokalen Zeiten im Datensatzprofil.

>[!NOTE]
>
>Der Parameter Zeitzone hat keine Auswirkungen auf die Funktionalität auf Systemebene wie Zeitstempel in Status- und Ereignisprotokollen, die in der lokalen Zeit des Systems ausgedrückt werden.

Der Parameter Zeitzone unterstützt ein systemunabhängiges Zeitzonenformat (&quot;Coordinated Universal Time&quot;) mit folgendem Format:

Zeitzone = Zeichenfolge: UTC +hhmm-Module

Das Zeichen (+) kann entweder ein Plus- (+) oder ein Minuszeichen (-) sein, und *hhmm* ist der Offset von UTC in Stunden und Minuten. Die optionale Variable *desstrules* gibt einen Regelsatz an, um die Sommerzeit oder eine ähnliche Richtlinie zur Uhrzeitverschiebung zu implementieren.

Wenn Sie *Strules* angeben, muss eine tabulatorgetrennte Datei mit dem Namen [!DNL dstrules .dst] im Unterverzeichnis Datensatz\TimeZone des Datensatzprofils vorhanden sein. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können für verschiedene Jahre unterschiedliche Regeln haben. Die von der Adobe im Basisprofil bereitgestellte [!DNL DST.dst]-Datei enthält die US-Standardregeln, die durch das Energy Policy Act von 2005 (in Kraft seit 2007) festgelegt wurden, und die US-Vorschriften für frühere Jahre.

Nachfolgend finden Sie Beispiele für Zeitzoneneinträge:

* US Eastern Daylight Time: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne Einschränkungen : Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone der Computer von Data Workbench Server, Data Workbench und [!DNL Report] nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven Datensatzprofile auf einem Data Workbench-Server nicht dieselbe Zeitzoneneinstellung haben.

Adobe rät davon ab, mehr als ein Datensatzprofil auf einem einzelnen Data Workbench-Servercomputer oder Data Workbench-Servercluster auszuführen.

Benutzer von Data Workbench sehen Daten in der Zeitzone des Datensatzprofils anstelle der Systemzeitzone. Adobe empfiehlt, dass die Systemzeitzone für einen Data Workbench-Servercomputer mit der in seinen Datensätzen verwendeten Zeitzone übereinstimmt.

>[!NOTE]
>
>Sie können in der Datei [!DNL Log Processing.cfg] einen Zeitzonenparameter angeben, der bei der Protokollverarbeitung für Zeitkonvertierungen verwendet wird. Weitere Informationen zum Parameter Zeitzone in der Datei [!DNL Log Processing.cfg] finden Sie unter [Konfigurationsdatei für die Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
