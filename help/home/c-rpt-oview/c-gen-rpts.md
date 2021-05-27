---
description: Erstellen Sie Berichte, indem Sie Arbeitsbereiche verarbeiten und als Berichte angeben.
title: Erstellen von Berichten
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Erstellen von Berichten{#generating-reports}

Erstellen Sie Berichte, indem Sie Arbeitsbereiche verarbeiten und als Berichte angeben.

[!DNL Report] generiert Ihre Berichte in dem im  [!DNL Every] Parameter in der  [!DNL Report.cfg] Datei festgelegten Intervall (z. B.  [!DNL "day]&quot;, wodurch der Bericht täglich verarbeitet wird) und basierend auf den anderen  [!DNL Report.cfg] Dateieinstellungen.

Beim Generieren von Berichten wird die prozentuale Vervollständigung auf der Registerkarte [!DNL Reports] unter der Miniaturansicht für diesen Bericht angezeigt. Wenn bei [!DNL Report] bei der Berichterstellung ein Problem auftritt, wird die neueste Fehlermeldung auf der Registerkarte [!DNL Reports] im Ordner des Berichtssatzes angezeigt. Wenn [!DNL Report] für einen bestimmten Bericht einen Fehler auftritt, werden die anderen Berichte in der Gruppe weiterhin verarbeitet.

Sie können die Berichte in einem Berichtssatz in einem oder allen der folgenden Formate generieren, indem Sie den Parameter [!DNL Report Types] in der Datei [!DNL Report.cfg] verwenden:

* Microsoft Excel-Datei ( [!DNL .xls] oder [!DNL .xlsx])
* Grafikdatei für tragbare Netzwerke ( [!DNL .png])
* Miniaturansicht ( [!DNL .jpg])

[!DNL Report] erstellt zusammen mit den angegebenen Ausgabetypen eine [!DNL .xml]-Datei mit dem Namen Ihres Berichts. Diese *`<report name>`*.xml-Datei enthält die Beschreibung des Berichts, der in Data Workbench auf der Registerkarte [!DNL Reports] unter der Miniaturansicht des Berichts angezeigt wird. Dadurch wird die Beschreibung verfügbar, die beim Verteilen Ihrer Berichte über ein Reporting-Portal verwendet werden kann. Weitere Informationen zu [!DNL Report Portal] finden Sie unter [Arbeiten mit Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Wenn Sie eine interne Metrik neu definieren, verhält sich das System aufgrund des falschen Werts unerwartet. Ihre Berichte werden nur generiert, wenn eine Metrik zu 100 % gelesen werden kann. Daher wird empfohlen, die Metrikdefinitionen nicht zu ändern.
