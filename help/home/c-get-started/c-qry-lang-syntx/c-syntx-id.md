---
description: Metrik-, Dimensions- und Filter-Ausdruck können Bezeichner verwenden, um auf benannte Metriken, Dimensionen und Filter zu verweisen.
title: Syntax für Kennungen
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# Syntax für Kennungen{#syntax-for-identifiers}

Metrik-, Dimensions- und Filter-Ausdruck können Bezeichner verwenden, um auf benannte Metriken, Dimensionen und Filter zu verweisen.

Bei diesen Bezeichnern wird die Groß-/Kleinschreibung beachtet und sie müssen genau so eingegeben werden, wie sie definiert sind.

Eine gültige Kennung kann einen oder mehrere der folgenden Elemente enthalten:

* Unterstriche (_). Unterstriche in einem Bezeichner stellen Leerzeichen im Metrik-, Dimensions- oder Filternamen dar. Beispielsweise würde die Dimension &quot;Session Werber&quot;in einem Ausdruck als [!DNL Session_Referrer] bezeichnet.
* Prozentzeichen (%)
* Großbuchstaben (A-Z)
* Kleinbuchstaben (a-z)
* Dollarzeichen ($)
* Zahlen (0-9), außer als erstes Zeichen in einem Bezeichner.
* Nicht-ASCII-Zeichen

Alle anderen Zeichen sind in einem Bezeichner unzulässig.

Diese Regeln gelten auch für die Namen von Metriken, Dimensionen und Filtern, wenn sie außerhalb von Ausdrücken verwendet werden, mit der Ausnahme, dass die Namen Leerzeichen, jedoch keine Unterstriche enthalten können. Sie können beispielsweise die Dimension &quot;Sitzungs-Werber&quot;in der Datei [!DNL Transformation.cfg] als Sitzungs-Werber, jedoch nicht als [!DNL Session_Referrer] definieren.
