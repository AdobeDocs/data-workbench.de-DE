---
description: Die Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquelldaten für andere Anwendungen zu ermöglichen.
title: Über die Umwandlungsfunktion
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Über die Umwandlungsfunktion{#about-transformation-functionality}

Die Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquelldaten für andere Anwendungen zu ermöglichen.

[!DNL Transform] Sie können  [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten lesen und die Daten als  [!DNL .vsl] Dateien, Textdateien oder Textdateien mit Trennzeichen exportieren, die durch DataWarehouse von Laderoutinen, Prüfagenturen oder anderen Zielen verwendet werden können. Die Datenextraktion und -umwandlung kann fortlaufend oder auf andere geplante Weise durchgeführt werden.

>[!NOTE]
>
>In der Regel wird [!DNL Transform] in einer Data Workbench-Server-FSU konfiguriert. Ihre Implementierung erfordert jedoch möglicherweise eine Konfiguration auf einer Data Workbench-Server-DPU. Weitere Informationen erhalten Sie bei der Adobe.

Informationen zur Speicherbelegung für [!DNL Transform] finden Sie in der detaillierten Statusschnittstelle. Weitere Informationen finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

Die Segmentexportfunktion bietet eine weitere Möglichkeit, Daten aus einer Adobe App zu exportieren. [!DNL Transform] ermöglicht Ihnen den Export von nicht verarbeiteten Daten in eine externe Zielgruppe. Mit der Segmentexportfunktion können Sie jedoch verarbeitete Daten aus dem Datensatz ausgeben, und es ist erforderlich, die exportierten Daten als Dimension im Datensatz zu definieren. Weitere Informationen zum Segmentexport finden Sie im *Data Workbench-Benutzerhandbuch*.
