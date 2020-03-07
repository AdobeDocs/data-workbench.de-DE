---
description: Im Report Portal können Sie von Report Server erstellte Berichte als Excel-Dateien (.xls oder .xlsx) oder .png-Dateien anzeigen.
solution: Analytics
title: Konfigurieren von Report.cfg-Dateien
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren von Report.cfg-Dateien{#configuring-report-cfg-files}

Im Report Portal können Sie von Report Server erstellte Berichte als Excel-Dateien (.xls oder .xlsx) oder .png-Dateien anzeigen.

Um einen Berichtssatz in der anzuzeigen, müssen Sie die folgenden Parameter in der [!DNL Report Portal][!DNL Report.cfg] Datei für diesen Berichtssatz festlegen:

* Geben Sie im **[!UICONTROL Output Root]** Parameter den Dokumentenstamm des Webservers an, der für Ihr Portal verwendet wird.
* Geben Sie im **[!UICONTROL Report Types]** Parameter Excel, PNG und/oder Miniaturansicht als Berichtstypen an, die Sie erstellen möchten.

Wenn Sie die Berichte in den von Ihnen angegebenen Formaten [!DNL Report Server] erstellen, werden diese Dateien im Dokumentenstamm des Webservers abgelegt. Während der Installation konfigurieren Sie die Datei für den Zugriff [!DNL Report Portal] auf die Berichte.

Weitere Informationen zu den spezifischen [!DNL Report.cfg] Parametern finden Sie unter [Report.cfg-Parameter](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
