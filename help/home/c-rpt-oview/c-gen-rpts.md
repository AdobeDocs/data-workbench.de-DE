---
description: Erstellen Sie Berichte, indem Sie Arbeitsbereiche verarbeiten und als Berichte angeben.
title: Erstellen von Berichten
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Erstellen von Berichten{#generating-reports}

{{eol}}

Erstellen Sie Berichte, indem Sie Arbeitsbereiche verarbeiten und als Berichte angeben.

[!DNL Report] generiert Ihre Berichte in dem im [!DNL Every] -Parameter in der [!DNL Report.cfg] -Datei (z. B. [!DNL "day],&quot; der den Bericht täglich verarbeitet) und auf der anderen Grundlage [!DNL Report.cfg] Dateieinstellungen.

Beim Generieren von Berichten wird der prozentuale Abschluss auf der Seite [!DNL Reports] unter der Miniaturansicht für diesen Bericht. Wenn [!DNL Report] bei der Berichterstellung ein Problem auftritt, wird die neueste Fehlermeldung auf der Seite [!DNL Reports] im Ordner des Berichtssatzes. Wenn [!DNL Report] für einen bestimmten Bericht einen Fehler auftritt, werden die anderen Berichte in der Gruppe weiterhin verarbeitet.

Sie können die Berichte in einem Berichtssatz in einem oder allen der folgenden Formate generieren, indem Sie die [!DNL Report Types] -Parameter in der [!DNL Report.cfg] Datei:

* Microsoft Excel-Datei ( [!DNL .xls] oder [!DNL .xlsx])
* Grafikdatei für tragbare Netzwerke ( [!DNL .png])
* Miniatur ( [!DNL .jpg])

zusammen mit den angegebenen Ausgabetypen, [!DNL Report] erstellt eine [!DNL .xml] -Datei, die denselben Namen wie Ihr Bericht hat. Diese *`<report name>`*.xml enthält die Beschreibung des Berichts, der in Data Workbench auf der [!DNL Reports] unter der Miniaturansicht des Berichts. Dadurch wird die Beschreibung verfügbar, die beim Verteilen Ihrer Berichte über ein Reporting-Portal verwendet werden kann. Informationen zum [!DNL Report Portal], siehe [Arbeiten mit Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Wenn Sie eine interne Metrik neu definieren, verhält sich das System aufgrund des falschen Werts unerwartet. Ihre Berichte werden nur generiert, wenn eine Metrik zu 100 % gelesen werden kann. Daher wird empfohlen, die Metrikdefinitionen nicht zu ändern.
