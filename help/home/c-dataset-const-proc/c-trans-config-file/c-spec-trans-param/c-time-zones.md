---
description: Der Zeitzonenparameter in der Datei "Transformation.cfg"steuert Zeitdimensionen, Zeitkonvertierungen (z. B. Definieren des Felds "x-local-timestring") und Formatierung aller Ortszeiten im DataSet-Profil.
title: Zeitzonen
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Zeitzonen{#time-zones}

Der Zeitzonenparameter in der Datei &quot;Transformation.cfg&quot;steuert Zeitdimensionen, Zeitkonvertierungen (z. B. Definieren des Felds &quot;x-local-timestring&quot;) und Formatierung aller Ortszeiten im DataSet-Profil.

>[!NOTE]
>
>Der Parameter &quot;Zeitzone&quot;hat keine Auswirkungen auf Funktionen auf Systemebene wie Zeitstempel im Status- und Ereignis-Protokoll, die in Systemlokalzeit ausgedrückt werden.

Der Parameter &quot;Zeitzone&quot;unterstützt ein systemunabhängiges Zeitzonenformat (&quot;Coordinated Universal Time&quot;) im folgenden Format:

Zeitzone = Zeichenfolge: UTC +hhmm-Zeichen

Das Zeichen (+) kann entweder ein Plus- (+) oder ein Minuszeichen (-) und *hmm* der Offset von UTC in Stunden und Minuten sein. Die optionale Variable *dstrules* gibt einen Regelsatz zur Implementierung der Sommerzeit oder einer ähnlichen Richtlinie zum Uhrzeitwechsel an.

Wenn Sie *Module* angeben, muss sich eine tabulatorgetrennte Datei mit dem Namen [!DNL dstrules .dst] im Unterordner &quot;Dataset\TimeZone&quot;des Dataset-Profils befinden. Die Datei gibt einen zeitzonenunabhängigen Regelsatz für die Sommerzeit an. Sie können unterschiedliche Regelsätze für verschiedene Jahre verwenden. Die [!DNL DST.dst]-Datei, die von der Adobe im Base-Profil bereitgestellt wird, legt die Standardregeln der USA fest, die im Energy Policy Act von 2005 (in Kraft seit 2007) und in den USA für Vorjahre festgelegt wurden.

Nachstehend sind Beispiele für Zeitzonen aufgeführt:

* Östliche Sommerzeit in den USA: Zeitzone = Zeichenfolge: UTC -0500 DST
* UTC-Zeit ohne Offset und ohne Zeichen: Zeitzone = Zeichenfolge: UTC -0000

Wenn dieses Format verwendet wird, muss die Systemzeitzone der Computer mit Data Workbench-Server, Data Workbench und [!DNL Report] nicht mit der angegebenen Zeitzone übereinstimmen. Darüber hinaus müssen alle aktiven DataSet-Profil auf einem Data Workbench-Servercomputer nicht über die gleiche Zeitzoneneinstellung verfügen.

Es wird von Adobe nicht empfohlen, mehr als ein DataSet-Profil auf einem einzelnen Data Workbench-Servercomputer oder einem Data Workbench-Servercluster auszuführen.

Data Workbench-Benutzer sehen Daten in der Zeitzone des Dataset-Profils anstelle der Systemzeitzone. Adobe empfiehlt, dass die Systemzeitzone für einen Data Workbench-Servercomputer mit der Zeitzone in den zugehörigen Datensätzen übereinstimmt.

>[!NOTE]
>
>Sie können einen Zeitzonenparameter in der Datei [!DNL Log Processing.cfg] angeben, in der er für Zeitkonvertierungen während der Protokollverarbeitung verwendet wird. Weitere Informationen zum Zeitzonenparameter in der Datei [!DNL Log Processing.cfg] finden Sie unter [Konfigurationsdatei für die Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
