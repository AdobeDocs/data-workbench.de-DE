---
description: Metriken, Dimensionen und Filter bieten ein Framework, in dem Berechnungen zu den zu einem Data Workbench-Datensatz verarbeiteten Daten vorgenommen werden.
solution: Analytics
title: Data Workbench-Metriken, -Dimensionen und -Filter
topic: Data workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench-Metriken, -Dimensionen und -Filter{#data-workbench-metrics-dimensions-and-filters}

Metriken, Dimensionen und Filter bieten ein Framework, in dem Berechnungen zu den zu einem Data Workbench-Datensatz verarbeiteten Daten vorgenommen werden.

Die Ergebnisse der mit diesem Framework definierten Berechnungen werden in Arbeitsbereichen, Dashboards, Berichten oder anderen Ausgaben angezeigt. Kurz gesagt, eine beliebige Zahl, die Sie in oder von einer Anwendung sehen, ist das Ergebnis einer Abfrage eines Datensatzes, die eine Metrik, eine Dimension und einen Filter enthält.

Auf der grundlegendsten Ebene beschreibt eine Metrik, was aus und über den Datensatz berechnet wird, eine Dimension unterteilt die Daten im Datensatz in Kategorien und ein Filter beschreibt einen ausgewählten Teil oder eine Untergruppe der Daten im Datensatz.

Wenn der Data Workbench-Server Daten verarbeitet, um ein Dataset zu erstellen, werden Dimensionen der Daten erstellt und dann kontinuierlich aktualisiert, wenn neue Daten vom Server gelesen und verarbeitet werden. Metriken und Filter werden anhand dieser Datendimensionen berechnet.

>[!CAUTION]
>
>Wenn Sie eine interne Metrik neu definieren, verhält sich das System aufgrund des falschen Werts unerwartet. Ihre Berichte werden nur generiert, wenn eine Metrik 100 % liest. Es wird empfohlen, die Metrikdefinitionen nicht zu ändern.

## Beispiel {#section-ecc465d1a5e34d559c1983e96fa409ec}

Stellen Sie sich einen Datensatz vor, der Informationen über alle Menschen auf der Welt enthält. Dieser Datensatz enthält mindestens alle Menschen auf der Welt und ihr Alter. Eine nützliche Metrik, die aus diesem Datensatz errechnet werden kann, wäre das Durchschnittsalter. Die Auswertung dieser Metrik würde zu einer Zahl führen: Durchschnittsalter der Weltbevölkerung.

Durch Hinzufügen einer Dimension zum Datensatz werden diese Informationen nützlicher und leichter zu handhaben. Wenn der Datensatz auch das Land des Wohnsitzes jeder Person enthält, könnte die Definition der Dimension &quot;Land&quot;eine Möglichkeit bieten, die Menschen für jedes Land der Welt in Gruppen zu unterteilen. Die Bewertung der Metrik &quot;Durchschnittsalter&quot;über die Dimension &quot;Land&quot;würde zu einer Liste von Zahlen führen, eine für jedes Land, die das Durchschnittsalter der Personen in diesem Land repräsentieren.

Die Anwendung eines Filters (oder Auswahlfilters) in einer Metrikformel kann detailliertere Informationen liefern oder die Definition einer neuen Metrik auf der Grundlage vorhandener Metriken und Dimensionen ermöglichen. Die Bewertung der Metrik &quot;Durchschnittsalter&quot;mit einem Filter von &quot;wobei Land gleich Schweden&quot;ergibt eine Zahl: Durchschnittsalter der Menschen in Schweden. Eine auf diesem Filter basierende Metrik könnte das schwedische Durchschnittsalter sein.

Beispiel:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Beziehung von Metriken, Dimensionen und Filtern {#section-28622596124140b280e6b993b174ef84}

Im Allgemeinen führt die Bewertung einer Metrik über eine Dimension dazu, dass diese Metrik für jedes Dimensionselement (oder Element) ausgewertet wird. Im obigen Beispiel hat die Dimension &quot;Land&quot;ein Element für jedes Land der Welt. Die Bewertung des Durchschnittsalters über das Land würde das Durchschnittsalter für jedes Element (Länder) einschließlich des Elements Schweden erbringen.

Beachten Sie, dass Sie beim Auswerten einer Metrik über eine Dimension dasselbe numerische Ergebnis für ein bestimmtes Dimensionselement erhalten, unabhängig davon, ob Sie diese Metrik für die gesamte Dimension auswerten oder einen Filter definieren, der diesem spezifischen Dimensionselement entspricht. Wenn man das vorangegangene Beispiel verwendet, würde eine der folgenden Methoden bei der Suche nach dem Durchschnittsalter der Menschen in Schweden identische Ergebnisse liefern:

* Bewerten Sie die Metrik &quot;Durchschnittsalter&quot;über die Dimension &quot;Land&quot;und sehen Sie sich dann die Zahl für das Dimensionselement Schweden an.
* Bewerten Sie die Metrik für das durchschnittliche Alter mit einem Filter von &quot;Personen in Schweden&quot;(ausgedrückt als [!DNL Average_[AgeCountry=&#39;Sweden&#39;]]).

Filter sind syntaktische Ausdrücke, die auf eine oder mehrere Dimensionen und Dimensionselemente verweisen. Wie Sie im obigen Beispiel gesehen haben, ist die Verwendung des Ausdrucks [!DNL [dimension=element]] eine einfache Möglichkeit, einen Filter anzugeben.

Ebenso einfach ist es, einen solchen Filter anzuwenden, um eine neue Metrik mit einem Ausdruck wie [!DNL New_Metric=[MetricFilter]] zu definieren. Ein solcher Filter kann verwendet werden, um eine neue Metrik basierend auf einem bestimmten Dimensionselement zu definieren. Um das obige Beispiel zu verwenden, gibt [!DNL Average_[AgeCountry=&#39;Sweden&#39;]] eine Metrik für das Durchschnittsalter von Menschen in Schweden an. Wenn wir dieser Metrik einen Namen geben würden, z. B. Swedish_Average_Age, könnten wir sie in anderen Berechnungen als Metrik verwenden. Die Auswertung [!DNL Swedish_Average_Age/Average_Age] würde zum Beispiel zu einer einzigen Zahl führen: das Verhältnis zwischen dem Durchschnittsalter der Menschen in Schweden und dem der Menschen in der übrigen Welt.

Wenn der Datensatz mit Informationen über alle Menschen in der Welt auch die Dimension &quot;Augenfarbe&quot;enthält, würde der Ausdruck [!DNL Swedish_Average_[AgeEye_Color=&#39;green&#39;]] zum Durchschnittsalter von Schweden mit grünen Augen führen. Sie können dasselbe Ergebnis auch ohne Verwendung einer Zwischenmetrikdefinition erhalten, indem Sie einen anderen Filter anwenden: [!DNL Average_[AgeCountry=&#39;Sweden&#39; AND Eye_Color=&#39;green&#39;]]. In diesem Fall gibt der [!DNL AND] Operator einen Filterausdruck mit zwei weiteren einfachen Filterausdrücken an.
