---
description: Metriken, Dimensionen und Filter bieten ein Framework für die Durchführung von Berechnungen zu den in einem Data Workbench-Datensatz verarbeiteten Daten.
title: Metriken, Dimensionen und Filter in Data Workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
exl-id: 687d9695-e70c-49ff-ac11-1537e6309e16
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 100%

---

# Metriken, Dimensionen und Filter in Data Workbench {#data-workbench-metrics-dimensions-and-filters}

Metriken, Dimensionen und Filter bieten ein Framework für die Durchführung von Berechnungen zu den in einem Data Workbench-Datensatz verarbeiteten Daten.

Die Ergebnisse der anhand dieses Frameworks definierten Berechnungen in Arbeitsbereichen, Dashboards, Berichten oder anderen Ausgaben angezeigt. Oder kurz gesagt: Jede Zahl, die in oder von einem Programm ausgegeben wird, ist das Ergebnis einer Abfrage eines Datensatzes und umfasst eine Metrik, eine Dimension und einen Filter.

Grundsätzlich betrachtet beschreibt eine Metrik, was aus und über den Datensatz berechnet wird. Eine Dimension wiederum unterteilt die Daten im Datensatz in Kategorien, während ein Filter eine bestimmte Auswahl bzw. Untergruppe der Daten im Datensatz beschreibt.

Bei der Verarbeitung von Daten durch den Data Workbench-Server wird ein Datensatz sowie Dimensionen der darin enthaltenen Daten erstellt, die der Server dann mit neuen Daten, die er liest und verarbeitet, laufend aktualisiert. Anhand dieser Datendimensionen werden schließlich Metriken und Filter berechnet.

>[!CAUTION]
>
>Das Ändern der Definition einer internen Metrik hat aufgrund des daraus resultierenden falschen Werts ein unerwartetes Verhalten des Systems zur Folge. Ihre Berichte werden nur generiert, wenn eine Metrik zu 100 % gelesen werden kann. Daher wird empfohlen, die Metrikdefinitionen nicht zu ändern.

## Beispiel {#section-ecc465d1a5e34d559c1983e96fa409ec}

Angenommen, wir haben einen Datensatz mit Informationen über alle Menschen auf der Welt. Darin enthalten sind mindestens Daten zum Alter jedes Menschen auf der Welt. Eine sinnvolle aus diesem Datensatz zu berechnende Metrik wäre das Durchschnittsalter. Die Berechnung dieser Metrik würde eine Zahl liefern, nämlich das Durchschnittsalter der Weltbevölkerung.

Durch Ergänzen einer Dimension zum Datensatz werden diese Informationen nützlicher und leichter zu handhaben. Enthält der Datensatz etwa auch für jede Person das Land, in dem diese lebt, ließen sich durch die Definition der Dimension „Land“ die Menschen für jedes Land der Welt in Gruppen unterteilen. Die Berechnung der Metrik „Durchschnittsalter“ über die Dimension „Land“ würde dann eine Liste mit Zahlen zu jedem einzelnen Land liefern, nämlich die des Durchschnittsalters der Menschen des jeweiligen Landes.

Durch die Anwendung eines Filters (oder Auswahlfilters) in einer Metrikformel können noch detailliertere Informationen ermittelt oder eine neue Metrik auf Grundlage vorhandener Metriken und Dimensionen definiert werden. Die Berechnung der Metrik „Durchschnittsalter“ mit einem Filter für „Land ist gleich Schweden“ ergibt eine Zahl, nämlich das Durchschnittsalter der Menschen in Schweden. Eine auf diesem Filter basierende Metrik auf Basis dieses Filters wäre dann das Durchschnittsalter der schwedischen Bevölkerung.

Beispiel:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Zusammenhang zwischen Metriken, Dimensionen und Filtern {#section-28622596124140b280e6b993b174ef84}

Im Allgemeinen liefert eine Metrik, die über eine Dimension berechnet wird, die Werte für jedes Dimensionselement (oder Element). Im obigen Beispiel umfasst die Dimension „Land“ jeweils ein Element für die einzelnen Länder der Welt. Die Ermittlung des Durchschnittsalters über das Land würde das Durchschnittsalter für jedes dieser Elemente (bzw. Länder) liefern, somit also auch für das Element „Schweden“.

Hierbei gilt zu beachten: Die Ermittlung einer Metrik über eine Dimension liefert für ein spezifisches Dimensionselement immer dasselbe numerische Ergebnis, unabhängig davon, ob Sie diese Metrik für die gesamte Dimension berechnen oder einen Filter für dieses spezifische Dimensionselement definieren. So würden im vorherigen Beispiel beide der folgenden Methoden für die Ermittlung des Durchschnittsalters der Menschen in Schweden dasselbe Ergebnisse liefern:

* Berechnung der Metrik „Durchschnittsalter“ über die Dimension „Land“ und anschließende Anzeige der Zahl für das Dimensionselement „Schweden“.
* Berechnung der Metrik „Durchschnittsalter“ mit einem Filter für „Personen in Schweden“ (ausgedrückt als [!DNL Average_Age[Country=&#39;Sweden&#39;]]).

Filter sind syntaktische Ausdrücke, die auf eine oder mehrere Dimensionen und Dimensionselemente verweisen. Wie im Beispiel oben gezeigt, lässt sich über den Ausdruck [!DNL [dimension=element]] auf einfache Weise ein Filter bestimmen.

Ebenso einfach gestaltet sich die Anwendung eines solchen Filters, um eine neue Metrik unter Verwendung eines Ausdrucks wie [!DNL New_Metric=Metric[Filter]] zu definieren. Mit einem solchen Filter lässt sich eine neue Metrik auf Grundlage eines spezifischen Dimensionselements definieren. So definiert im Beispiel oben [!DNL Average_Age[Country=&#39;Sweden&#39;]] eine Metrik für das Durchschnittsalter der Menschen in Schweden. Würden wir diese Metrik mit einem Namen versehen, z. B. „Swedish_Average_Age“, könnten wir sie in anderen Berechnungen als Metrik verwenden. So würde etwa die Ermittlung von [!DNL Swedish_Average_Age/Average_Age] eine einzelne Zahl liefern, nämlich das Durchschnittsalter der Menschen in Schweden im Verhältnis zu dem der Menschen im Rest der Welt.

Enthält der Datensatz mit Informationen über alle Menschen der Welt etwa auch die Dimension „Augenfarbe“, würde der Ausdruck [!DNL Swedish_Average_Age[Eye_Color=&#39;green&#39;]] das Durchschnittsalter der Schweden liefern, deren Augen grün sind. Dasselbe Ergebnis erhalten Sie auch ohne die Definition einer Zwischenmetrik, indem Sie einen anderen Filter anwenden: [!DNL Average_Age[Country=&#39;Sweden&#39; AND Eye_Color=&#39;green&#39;]]. Darin definiert der [!DNL AND]-Operator einen Filterausdruck, der zwei weitere einfache Filterausdrücke verwendet.
