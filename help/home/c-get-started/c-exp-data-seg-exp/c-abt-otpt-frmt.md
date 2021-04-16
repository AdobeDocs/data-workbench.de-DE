---
description: Richtlinien zum Festlegen des Ausgabeformats.
title: Ausgabeformat
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Ausgabeformat{#output-format}

Richtlinien zum Festlegen des Ausgabeformats.

* Jeder Metrik- oder Dimensionsname muss mit einem Prozentzeichen (%) Beginn und enden.

   * %XYZ% gibt das Element der Dimension XYZ an, das dem Element der Ebene entspricht. Es wird ein Fehler generiert, wenn die Dimension XYZ mit Ebene nicht eins zu eins oder eins zu eins ist.
   * %=XYZ% gibt den Wert der Metrik oder Metrikformel XYZ für das angegebene Element der Ebene an.

* Dimensionen, die zwei oder mehr Wörter sind, erfordern keine Unterstriche.
* Metriknamen, die zwei Wörter oder länger sind, erfordern Unterstriche.

>[!NOTE]
>
>Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste in das Feld [!DNL Output Format] klicken, wird ein [!DNL Insert menu] angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen (z. B. Tabulatoren), die häufig als Trennzeichen verwendet werden.

Wenn Sie Daten zur Sitzungsdauer für Ihr Segment exportieren möchten, müssen Sie eine neue Metrik erstellen, die auf der Metrik &quot;Sitzungsdauer&quot;basiert. Die neue Metrik, die nur mit dem Feld [!DNL Output Format] des Segmentexports verwendet werden soll, ermöglicht Microsoft Excel die korrekte Interpretation von Sitzungen, die weniger als eine Stunde dauern. Um eine neue Metrik für die Sitzungsdauer zu erstellen, öffnen Sie die Datei [!DNL Session Duration.metric] (aus dem [!DNL Profile Manager]) und fügen Sie ein Rautenzeichen (#) in die Zeitzeichenfolge ein: [!DNL ftime = string: %#H:%M:%S]

Das Rautenzeichen bewirkt, dass eine vorangestellte &quot;0&quot;an eine Sitzungsdauer von weniger als 1 Stunde angehängt wird. Excel interpretiert 0:53:21 als 53 Minuten und 21 Sekunden. Speichern Sie die neue Metrik unter einem anderen Namen und laden Sie sie in das entsprechende Profil hoch, damit andere sie verwenden können, indem Sie mit der rechten Maustaste auf das Dateimarkierungszeichen in der Spalte [!DNL User] klicken und **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]*** klicken.
