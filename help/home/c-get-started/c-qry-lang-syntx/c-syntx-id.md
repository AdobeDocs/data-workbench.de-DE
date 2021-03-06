---
description: Metrik-, Dimensions- und Filterausdrücke können Bezeichner verwenden, um auf benannte Metriken, Dimensionen und Filter zu verweisen.
title: Syntax für Kennungen
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# Syntax für Kennungen{#syntax-for-identifiers}

Metrik-, Dimensions- und Filterausdrücke können Bezeichner verwenden, um auf benannte Metriken, Dimensionen und Filter zu verweisen.

Bei diesen Kennungen wird zwischen Groß- und Kleinschreibung unterschieden. Sie müssen genau so eingegeben werden, wie sie definiert sind.

Eine gültige Kennung kann einen oder mehrere der folgenden Elemente enthalten:

* Unterstriche (_). Unterstriche in einem Bezeichner stellen Leerzeichen in der Metrik, Dimension oder im Filternamen dar. Die Dimension &quot;Sitzungsverweiser&quot;würde beispielsweise in einem Ausdruck als [!DNL Session_Referrer] bezeichnet.
* Prozentzeichen (%)
* Großbuchstaben (A-Z)
* Kleinbuchstaben (a-z)
* Dollarzeichen ($)
* Zahlen (0-9), außer als erstes Zeichen in einer Kennung.
* Nicht-ASCII-Zeichen

Alle anderen Zeichen sind in einer Kennung unzulässig.

Dieselben Regeln gelten für die Namen von Metriken, Dimensionen und Filtern, wenn sie außerhalb von Ausdrücken verwendet werden. Der Unterschied besteht darin, dass die Namen Leerzeichen, aber keine Unterstriche enthalten können. Sie können beispielsweise die Dimension &quot;Sitzungsverweiser&quot;in der Datei [!DNL Transformation.cfg] als Sitzungsverweiser, jedoch nicht als [!DNL Session_Referrer] definieren.
