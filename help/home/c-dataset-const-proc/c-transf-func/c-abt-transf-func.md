---
description: Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu ermöglichen.
solution: Analytics
title: Informationen zu Transformation-Funktionen
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informationen zu Transformation-Funktionen{#about-transformation-functionality}

Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu ermöglichen.

[!DNL Transform] Sie können [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten lesen und die Daten als [!DNL .vsl] Dateien, Textdateien oder durch Trennzeichen getrennte Textdateien exportieren, die von DataWarehouse-Laderoutinen, Prüfungsagenturen oder anderen Zielen verwendet werden können. Die Datenextrahierung und -umwandlung kann auf kontinuierlicher oder anderer planmäßiger Basis durchgeführt werden.

>[!NOTE]
>
>In der Regel [!DNL Transform] wird auf einem Data Workbench-Server-FSU konfiguriert. Ihre Implementierung erfordert jedoch möglicherweise eine Konfiguration auf einer Data Workbench-Server-DPU. Weitere Informationen erhalten Sie bei Adobe.

Informationen zur Speicherbelegung finden Sie [!DNL Transform] in der Detaillierten Statusoberfläche. Weitere Informationen finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

Die Segmentexportfunktion bietet eine weitere Möglichkeit, Daten aus einer Adobe-Anwendung zu exportieren. [!DNL Transform] ermöglicht Ihnen den Export nicht verarbeiteter Daten in ein externes Ziel, aber mit der Segmentexportfunktion können Sie verarbeitete Daten aus dem Datensatz ausgeben, und es ist erforderlich, dass die exportierten Daten als Dimension im Datensatz definiert werden. Weitere Informationen zum Segmentexport finden Sie im *Data Workbench-Benutzerhandbuch*.
