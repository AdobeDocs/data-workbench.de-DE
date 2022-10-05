---
description: Nachdem die Berichte generiert wurden, verteilt Report die Berichte im Satz auf Grundlage der Einstellungen in der Datei "Report.cfg".
title: Bereitstellen von Berichten
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Bereitstellen von Berichten{#distributing-reports}

{{eol}}

Nachdem die Berichte generiert wurden, verteilt Report die Berichte im Satz auf Grundlage der Einstellungen in der Datei &quot;Report.cfg&quot;.

[!DNL Report] ermöglicht die Verteilung der Berichte in einem Satz mithilfe der folgenden Methoden:

* **E-Mail:** So verteilen Sie Berichte als Excel-Dateien: [!DNL .png] -Dateien oder Miniaturansichten per E-Mail (in Zeilen oder als Anhänge), geben Sie die E-Mail-Berichtsparameter in den [!DNL Report.cfg] -Datei. Alle Berichte in diesem Satz werden den angegebenen Empfängern per E-Mail zugestellt.

* **Freigegebener Ordner:** So verteilen Sie Berichte als Excel-Dateien: [!DNL .png] -Dateien oder Miniaturansichten in einem freigegebenen Ordner angeben, geben Sie das Verzeichnis im Parameter &quot;Output Root&quot;im Berichtssatz an. [!DNL Report.cfg] -Datei.

* **Reporting-Portal:** Mit einem Reporting-Portal können Sie Berichte über Ihren Webbrowser anzeigen. Adobe [!DNL Report Portal] zeigt Berichte an, die als Excel generiert wurden oder [!DNL .png] -Dateien, jedoch nicht die als Miniaturansichten ( [!DNL .jpg]). Um Berichte an ein Portal zu verteilen, geben Sie im Parameter &quot;Output Root&quot;des Berichtssatzes den Basisordner des Webservers an, der für das Portal verwendet wird. [!DNL Report.cfg] -Datei. Weitere Informationen zur Installation und Verwendung von [!DNL Report Portal], siehe [Arbeiten mit Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>So lesen Sie die Ausgabe, die derzeit von [!DNL Report]müssen Sie über eine Anwendung verfügen, die die Berichte im gewünschten Format anzeigen kann. Zum Beispiel, um [!DNL .xlsx] -Dateien, benötigen Sie Microsoft Excel 2007 oder höher.

Sie können auch eine Kombination dieser Erzeugungs- und Verteilungsoptionen verwenden. Wenn Sie beispielsweise [!DNL Report Types] Parameter zum Generieren eines Berichtssatzes als Excel und [!DNL .png] -Dateien und legen Sie dann die [!DNL Mail Report]und [!DNL Output Root] -Parameter, werden alle Berichte in diesem Satz an das angegebene Ausgabeverzeichnis verteilt (möglicherweise in einem Portal angezeigt) und per E-Mail an Empfänger gesendet.

Anweisungen zum Konfigurieren Ihrer Berichtssätze finden Sie unter [Arbeiten mit Berichtssätzen](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Weitere Informationen zu [!DNL Report.cfg] Parameter, siehe [Parameter &quot;Report.cfg&quot;](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
