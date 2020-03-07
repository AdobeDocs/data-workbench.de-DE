---
description: Nachdem die Berichte generiert wurden, verteilt Report die Berichte im Satz auf Grundlage der Einstellungen in der Datei "Report.cfg".
solution: Analytics
title: Verteilen von Berichten
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verteilen von Berichten{#distributing-reports}

Nachdem die Berichte generiert wurden, verteilt Report die Berichte im Satz auf Grundlage der Einstellungen in der Datei &quot;Report.cfg&quot;.

[!DNL Report] ermöglicht die Verteilung der Berichte in einem Satz mit folgenden Methoden:

* **E-Mail:** Um Berichte als Excel-Dateien, [!DNL .png] Dateien oder Miniaturansichten per E-Mail (Inline- oder als Anhänge) zu verteilen, geben Sie die Parameter für den Mail-Bericht in der [!DNL Report.cfg] Datei des Berichtssatzes an. Alle Berichte in diesem Satz werden per E-Mail an die angegebenen Empfänger gesendet.

* **Freigegebener Ordner:** Um Berichte als Excel-Dateien, [!DNL .png] Dateien oder Miniaturansichten in einen freigegebenen Ordner zu verteilen, geben Sie den Ordner im Parameter &quot;Ausgabestamm&quot;in der [!DNL Report.cfg] Datei des Berichtssatzes an.

* **Berichterstellungsportal:** Mit einem Berichterstellungsportal können Sie Berichte über Ihren Webbrowser anzeigen. In Adobe [!DNL Report Portal] werden Berichte angezeigt, die als Excel oder [!DNL .png] Dateien generiert wurden, jedoch nicht als Miniaturansichten ( [!DNL .jpg]). Um Berichte an ein Portal zu verteilen, geben Sie den Dokumentenstamm des Webservers an, der für das Portal verwendet wird, und zwar im Parameter &quot;Ausgabestamm&quot;in der [!DNL Report.cfg] Datei des Berichtssatzes. Weitere Informationen zum Installieren und Verwenden [!DNL Report Portal]finden Sie unter [Arbeiten mit Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Zum Lesen der Ausgabe, die derzeit von unterstützt wird, benötigen Sie eine Anwendung, [!DNL Report]die die Berichte im gewünschten Format anzeigen kann. Zum Anzeigen von [!DNL .xlsx] Dateien benötigen Sie beispielsweise Microsoft Excel 2007 oder höher.

Sie können auch eine Kombination dieser Generierungs- und Verteilungsoptionen verwenden. Wenn Sie beispielsweise den [!DNL Report Types] Parameter zum Generieren eines Berichtssatzes als Excel- und [!DNL .png] -Dateien festlegen und dann die Parameter [!DNL Mail Report]und [!DNL Output Root] festlegen, werden alle Berichte in diesem Satz an den angegebenen Ausgabeverzeichnis verteilt (möglicherweise in einem Portal angezeigt) und per E-Mail an Empfänger gesendet.

Anweisungen zum Konfigurieren der Berichtssätze finden Sie unter [Arbeiten mit Berichtssätzen](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Weitere Informationen zu den spezifischen [!DNL Report.cfg] Parametern finden Sie unter [Report.cfg-Parameter](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
