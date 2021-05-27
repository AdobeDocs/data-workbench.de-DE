---
description: Im Report Portal können Sie von Report Server generierte Berichte als Excel-Dateien (.xls- oder .xlsx-Dateien) oder PNG-Dateien anzeigen.
title: Konfigurieren von cfg-Dateien für Berichte
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Konfigurieren von cfg-Dateien für Berichte{#configuring-report-cfg-files}

Im Report Portal können Sie von Report Server generierte Berichte als Excel-Dateien (.xls- oder .xlsx-Dateien) oder PNG-Dateien anzeigen.

Um einen Berichtssatz im [!DNL Report Portal] anzuzeigen, müssen Sie die folgenden Parameter in der [!DNL Report.cfg]-Datei für diesen Berichtssatz festlegen:

* Geben Sie im Parameter **[!UICONTROL Output Root]** den Dokumentenstamm des Webservers an, der für Ihr Portal verwendet wird.
* Geben Sie im Parameter **[!UICONTROL Report Types]** Excel, PNG und/oder Miniatur als Berichtstypen an, die Sie generieren möchten.

Wenn [!DNL Report Server] die Berichte in den von Ihnen angegebenen Formaten generiert, werden diese Dateien im Basisverzeichnis des Webservers abgelegt. Während der Installation konfigurieren Sie [!DNL Report Portal], um auf die Berichte zuzugreifen.

Weitere Informationen zu den spezifischen [!DNL Report.cfg]-Parametern finden Sie unter [Report.cfg-Parameter](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
