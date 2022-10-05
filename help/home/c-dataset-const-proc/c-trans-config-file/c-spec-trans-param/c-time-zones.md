---
description: Der Parameter "Zeitzone"in der Datei "Transformation.cfg"steuert Zeitdimensionen, Zeitkonversionen (z. B. das Feld x-local-timestring ) und die Formatierung aller lokalen Zeiten im Datensatzprofil.
title: Zeitzonen
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Zeitzonen{#time-zones}

{{eol}}

Der Parameter &quot;Zeitzone&quot;in der Datei &quot;Transformation.cfg&quot;steuert Zeitdimensionen, Zeitkonversionen (z. B. das Feld x-local-timestring ) und die Formatierung aller lokalen Zeiten im Datensatzprofil.

>[!NOTE]
>
>Der Parameter Zeitzone hat keine Auswirkungen auf die Funktionalität auf Systemebene wie Zeitstempel in Status- und Ereignisprotokollen, die in der lokalen Zeit des Systems ausgedrückt werden.

Der Parameter Zeitzone unterstützt ein systemunabhängiges Zeitzonenformat (&quot;Coordinated Universal Time&quot;) mit folgendem Format:

Zeitzone = Zeichenfolge: UTC +hhmm-Module

Das Zeichen (+) kann ein Pluszeichen (+) oder ein Minuszeichen (-) sein und *hhmm* ist der Offset von UTC in Stunden und Minuten. Die optionale Variable *dstrules* gibt einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zur Uhrzeitverschiebung an.

Wenn Sie *dstrules*, eine tabulatorgetrennte Datei mit dem Namen [!DNL dstrules .dst] muss im Unterverzeichnis Datensatz\TimeZone des Datensatzprofils vorhanden sein. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können für verschiedene Jahre unterschiedliche Regeln haben. Die [!DNL DST.dst] -Datei, die von der Adobe im Basisprofil bereitgestellt wird, die Standardregeln der USA, die durch das Energy Policy Act von 2005 (in Kraft seit 2007) festgelegt wurden, und die US-Vorschriften für frühere Jahre.

Nachfolgend finden Sie Beispiele für Zeitzoneneinträge:

* US Eastern Daylight Time: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne Einschränkungen : Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, die Systemzeitzone des Data Workbench-Servers, der Data Workbench und [!DNL Report] -Maschinen müssen nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven Datensatzprofile auf einem Data Workbench-Server nicht dieselbe Zeitzoneneinstellung haben.

Adobe rät davon ab, mehr als ein Datensatzprofil auf einem einzelnen Data Workbench-Servercomputer oder Data Workbench-Servercluster auszuführen.

Benutzer von Data Workbench sehen Daten in der Zeitzone des Datensatzprofils anstelle der Systemzeitzone. Adobe empfiehlt, dass die Systemzeitzone für einen Data Workbench-Servercomputer mit der in seinen Datensätzen verwendeten Zeitzone übereinstimmt.

>[!NOTE]
>
>Sie können einen Zeitzonenparameter im [!DNL Log Processing.cfg] -Datei, wobei sie für Zeitkonvertierungen während der Protokollverarbeitung verwendet wird. Informationen zum Zeitzonenparameter finden Sie im [!DNL Log Processing.cfg] -Datei, siehe [Konfigurationsdatei für die Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
