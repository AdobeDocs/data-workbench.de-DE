---
description: Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu ermöglichen.
title: Über die Umwandlungsfunktion
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Über die Umwandlungsfunktion{#about-transformation-functionality}

Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquellendaten für die Verwendung durch andere Anwendungen zu ermöglichen.

[!DNL Transform] Sie können  [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten lesen und die Daten als  [!DNL .vsl] Dateien, Textdateien oder durch Trennzeichen getrennte Textdateien exportieren, die von DataWarehouse zum Laden von Routinen, Prüfungsagenturen oder anderen Zielgruppen verwendet werden können. Die Extraktion und Transformation der Daten kann kontinuierlich oder auf andere geplante Weise durchgeführt werden.

>[!NOTE]
>
>In der Regel wird [!DNL Transform] auf einem Data Workbench-Server-FSU konfiguriert. Ihre Implementierung erfordert jedoch möglicherweise eine Konfiguration auf einer Data Workbench-Server-DPU. Weitere Informationen erhalten Sie bei der Adobe.

Sie können Speichernutzungsinformationen für [!DNL Transform] in der Detaillierten Statusoberfläche Ansicht geben. Weitere Informationen finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

Die Segmentexportfunktion bietet eine weitere Möglichkeit, Daten aus einer Adobe zu exportieren. [!DNL Transform] ermöglicht Ihnen den Export von nicht verarbeiteten Daten in eine externe Zielgruppe, aber mit der Segmentexportfunktion können Sie verarbeitete Daten aus dem Datensatz ausgeben. Außerdem müssen die exportierten Daten als Dimension im Datensatz definiert werden. Weitere Informationen zum Segmentexport finden Sie im *Data Workbench Benutzerhandbuch*.
