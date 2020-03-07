---
description: Metrik-, Dimensions- und Filterausdrücke können Bezeichner verwenden, um auf benannte Metriken, Dimensionen und Filter zu verweisen.
solution: Analytics
title: Syntax für Bezeichner
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax für Bezeichner{#syntax-for-identifiers}

Metrik-, Dimensions- und Filterausdrücke können Bezeichner verwenden, um auf benannte Metriken, Dimensionen und Filter zu verweisen.

Bei diesen Bezeichnern wird die Groß-/Kleinschreibung beachtet und sie müssen genau so eingegeben werden, wie sie definiert sind.

Eine gültige Kennung kann einen oder mehrere der folgenden Elemente enthalten:

* Unterstriche (_). Unterstriche in einem Bezeichner stellen Leerzeichen im Metrik-, Dimensions- oder Filternamen dar. Beispielsweise wird die Dimension &quot;Referrer&quot;in einem Ausdruck als [!DNL Session_Referrer] &quot;Referenz&quot;bezeichnet.
* Prozentzeichen (%)
* Großbuchstaben (A-Z)
* Kleinbuchstaben (a-z)
* Dollarzeichen ($)
* Zahlen (0-9), außer als erstes Zeichen in einem Bezeichner.
* Nicht-ASCII-Zeichen

Alle anderen Zeichen sind in einem Bezeichner unzulässig.

Diese Regeln gelten auch für die Namen von Metriken, Dimensionen und Filtern, wenn sie außerhalb von Ausdrücken verwendet werden, mit der Ausnahme, dass die Namen Leerzeichen, jedoch keine Unterstriche enthalten können. Sie können beispielsweise die Dimension &quot;Referrer&quot;in der [!DNL Transformation.cfg] Datei als &quot;Sitzungsreferrer&quot;definieren, jedoch nicht [!DNL Session_Referrer].
