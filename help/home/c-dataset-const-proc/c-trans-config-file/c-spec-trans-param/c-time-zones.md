---
description: Der Parameter "Zeitzone"in der Datei "Transformation.cfg"steuert die Zeitdimensionen, Zeitkonvertierungen (z. B. Definieren des Felds x-local-timestring) und Formatierung aller lokalen Zeiten im Datensatzprofil.
solution: Analytics
title: Zeitzonen
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Zeitzonen{#time-zones}

Der Parameter &quot;Zeitzone&quot;in der Datei &quot;Transformation.cfg&quot;steuert die Zeitdimensionen, Zeitkonvertierungen (z. B. Definieren des Felds x-local-timestring) und Formatierung aller lokalen Zeiten im Datensatzprofil.

>[!NOTE]
>
>Der Parameter &quot;Zeitzone&quot;hat keine Auswirkungen auf Funktionen auf Systemebene wie Zeitstempel in Status- und Ereignisprotokollen, die in der lokalen Zeit des Systems angegeben werden.

Der Parameter &quot;Zeitzone&quot;unterstützt ein systemunabhängiges Zeitzonenformat (&quot;Coordinated Universal Time&quot;) im folgenden Format:

Zeitzone = Zeichenfolge: UTC +hhmm-Zeichen

Das Zeichen (+) kann entweder ein Pluszeichen (+) oder ein Minuszeichen (-) sein, und *hhmm* ist der Offset von UTC in Stunden und Minuten. Die optionalen Variablen *beschreiben* einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zum Uhrzeitwechsel.

Wenn Sie *Module* angeben, muss sich eine tabulatorgetrennte Datei mit dem Namen [!DNL dstrules .dst] im Unterverzeichnis DataSet\TimeZone des Datensatzprofils befinden. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können unterschiedliche Regelsätze für verschiedene Jahre verwenden. Die von Adobe im Basisprofil bereitgestellte [!DNL DST.dst] Datei legt die Standardregeln der USA fest, die mit dem Energy Policy Act von 2005 (in Kraft seit 2007) und den US-Regeln für frühere Jahre festgelegt wurden.

Nachstehend sind Beispiele für Zeitzonen aufgeführt:

* Östliche Sommerzeit in den USA: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne Zeichen: Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone von Data Workbench-Server, Data Workbench und [!DNL Report] Computern nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven DataSet-Profile auf einem Data Workbench-Servercomputer nicht die gleiche Zeitzoneneinstellung haben.

Adobe empfiehlt nicht, mehr als ein Datenset-Profil auf einem einzelnen Datenbasis-Servercomputer oder einem Datenbasis-Servercluster auszuführen.

Data Workbench-Benutzer sehen Daten in der Zeitzone des Datensatzprofils anstelle der Systemzeitzone. Adobe empfiehlt, dass die Systemzeitzone für einen Data Workbench-Servercomputer mit der Zeitzone in seinen Datensätzen übereinstimmt.

>[!NOTE]
>
>Sie können einen Zeitzonenparameter in der [!DNL Log Processing.cfg] Datei angeben, der bei der Protokollverarbeitung für Zeitkonvertierungen verwendet wird. Informationen zum Parameter &quot;Zeitzone&quot;in der [!DNL Log Processing.cfg] Datei finden Sie unter Konfigurationsdatei für die [Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

