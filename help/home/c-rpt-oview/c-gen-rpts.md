---
description: Erstellen Sie Berichte, indem Sie Arbeitsbereiche verarbeiten und als Berichte festlegen.
solution: Analytics
title: Erstellen von Berichten
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen von Berichten{#generating-reports}

Erstellen Sie Berichte, indem Sie Arbeitsbereiche verarbeiten und als Berichte festlegen.

[!DNL Report] erstellt Ihre Berichte in dem im [!DNL Every] Parameter in der [!DNL Report.cfg] Datei festgelegten Intervall (z. B. [!DNL "day]&quot;, bei dem der Bericht täglich verarbeitet wird) und auf der Grundlage der anderen [!DNL Report.cfg] Dateieinstellungen.

Beim Generieren von Berichten wird der Prozentsatz der Vollständigkeit auf der Registerkarte unter der Miniaturansicht des jeweiligen Berichts angezeigt. [!DNL Reports] Wenn [!DNL Report] bei der Berichterstellung ein Problem auftritt, wird auf der Registerkarte im Ordner des Berichtssatzes die letzte Fehlermeldung angezeigt [!DNL Reports] . Wenn [!DNL Report] bei einem bestimmten Bericht ein Fehler auftritt, werden die anderen Berichte im Satz weiter verarbeitet.

Sie können die Berichte in einem Berichtssatz in einem der folgenden oder allen der folgenden Formate mithilfe des [!DNL Report Types] Parameters in der [!DNL Report.cfg] Datei generieren:

* Microsoft Excel-Datei ( [!DNL .xls] oder [!DNL .xlsx])
* Portable network graphic file ( [!DNL .png])
* Miniaturansicht ( [!DNL .jpg])

Erstellt zusammen mit den angegebenen Ausgabetypen [!DNL Report] eine [!DNL .xml] Datei mit dem Namen Ihres Berichts. Diese *`<report name>`*.xml-Datei enthält die Beschreibung des Berichts, der auf der Registerkarte unter der Miniaturansicht des Berichts in Data Workbench angezeigt wird [!DNL Reports] . Dadurch wird die Beschreibung für die Verteilung Ihrer Berichte über ein Berichterstellungsportal verfügbar. Weitere Informationen zum [!DNL Report Portal]Bericht finden Sie unter [Arbeiten mit Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Wenn Sie eine interne Metrik neu definieren, verhält sich das System aufgrund des falschen Werts unerwartet. Ihre Berichte werden nur generiert, wenn eine Metrik 100 % liest. Es wird empfohlen, die Metrikdefinitionen nicht zu ändern.
