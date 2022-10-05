---
description: Im Report Portal können Sie von Report Server generierte Berichte als Excel-Dateien (.xls- oder .xlsx-Dateien) oder PNG-Dateien anzeigen.
title: Konfigurieren von cfg-Dateien für Berichte
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Konfigurieren von cfg-Dateien für Berichte{#configuring-report-cfg-files}

{{eol}}

Im Report Portal können Sie von Report Server generierte Berichte als Excel-Dateien (.xls- oder .xlsx-Dateien) oder PNG-Dateien anzeigen.

So zeigen Sie einen Berichtssatz im [!DNL Report Portal]müssen Sie die folgenden Parameter in der [!DNL Report.cfg] -Datei für diesen Berichtssatz:

* Im **[!UICONTROL Output Root]** den Basisordner des Webservers angeben, der für Ihr Portal verwendet wird.
* Im **[!UICONTROL Report Types]** als die Berichtstypen angeben, die Sie generieren möchten, Excel, PNG und/oder Miniatur.

Wann [!DNL Report Server] Die Berichte werden in den von Ihnen angegebenen Formaten generiert. Diese Dateien werden im Basisverzeichnis des Webservers abgelegt, wo Sie während der Installation die [!DNL Report Portal] , um auf die Berichte zuzugreifen.

Weitere Informationen zu [!DNL Report.cfg] Parameter, siehe [Parameter &quot;Report.cfg&quot;](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
