---
description: Die Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquelldaten für andere Anwendungen zu ermöglichen.
title: Über die Umwandlungsfunktion
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Über die Umwandlungsfunktion{#about-transformation-functionality}

{{eol}}

Die Transform-Funktion (Transform) wird auf einem Data Workbench-Servercomputer ausgeführt, um den Export von Protokollquelldaten für andere Anwendungen zu ermöglichen.

[!DNL Transform] lesen [!DNL .vsl] Dateien, Protokolldateien, XML-Dateien und ODBC-Daten und exportieren Sie die Daten als [!DNL .vsl] -Dateien, Textdateien oder Textdateien mit Trennzeichen, die von DataWarehouse-Laderoutinen, Prüfagenturen oder anderen Zielen verwendet werden können. Die Datenextraktion und -umwandlung kann fortlaufend oder auf andere geplante Weise durchgeführt werden.

>[!NOTE]
>
>In der Regel [!DNL Transform] wird auf einer FSU des Data Workbench-Servers konfiguriert. Ihre Implementierung erfordert jedoch möglicherweise eine Konfiguration auf einer Data Workbench-Server-DPU. Weitere Informationen erhalten Sie bei der Adobe.

Sie können Informationen zur Speicherbelegung anzeigen für [!DNL Transform] in der Oberfläche für den detaillierten Status . Weitere Informationen finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;im *Data Workbench-Benutzerhandbuch*.

Die Segmentexportfunktion bietet eine weitere Möglichkeit, Daten aus einer Adobe App zu exportieren. [!DNL Transform] ermöglicht Ihnen den Export von nicht verarbeiteten Daten in eine externe Zielgruppe. Mit der Segmentexportfunktion können Sie jedoch verarbeitete Daten aus dem Datensatz ausgeben, und es ist erforderlich, die exportierten Daten als Dimension im Datensatz zu definieren. Weitere Informationen zum Segmentexport finden Sie unter *Data Workbench-Benutzerhandbuch*.
