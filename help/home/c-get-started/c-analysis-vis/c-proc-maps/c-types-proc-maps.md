---
description: Informationen zu den verschiedenen Arten von Prozesskarten.
title: Typen von Prozesskarten
uuid: 19473b77-13c1-4829-b018-d3316e434ba4
exl-id: 8bac7036-c7fe-4566-8e59-08e1ddc7ddb7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---

# Typen von Prozesskarten{#types-of-process-maps}

Informationen zu den verschiedenen Arten von Prozesskarten.

## 2D-Prozesskarten {#section-ea7fbdb80b1b44aebcd9e4090b6540bf}

Zweidimensionale Prozesskarten bieten eine zweidimensionale Ansicht der Aktivität zwischen Dimensionselementen. Die Größe eines Knotens in einer 2D-Prozesszuordnung ist proportional zum Wert der mit diesem Knoten verknüpften Metrik. Darüber hinaus sind sowohl die Stärke als auch die Intensität eines Pfeils zwischen zwei Knoten proportional zum Durchschnitt der Metrikwerte für diese Knoten.

In einer 2D-Prozesszuordnung können Sie eine der folgenden Aufgaben ausführen:

* Knoten auswählen, verschieben, entfernen und beschriften
* Auswählen von Elementen
* Dimensionen speichern
* Andere Visualisierungen erstellen
* Farblinks aktivieren
* Anzahl der Anzeigemetriken
* Hinzufügen von Hinweisen

Die 2D-Prozesskarte im folgenden Beispiel zeigt Knoten, die den Namen von Filmen entsprechen. Jeder Filmname ist ein Element der Dimension Film , das in einem Datensatz definiert ist, der aus Filmdaten besteht. Die Dimension Film ist die Basisdimension für diese Prozesskarte.

![](assets/vis_2DProcessMap_MovieNodes.png)

Im Beispiel sind die Größe jedes Knotens sowie die Stärke und Intensität jedes Pfeils proportional zur Metrik Bewertungen , was einer Zählung der Bewertungen entspricht, die ein Film erhalten hat. Daher hat ein Film mit einem großen Knoten wie *Independence Day* mehr Bewertungen als ein Film mit einem kleinen Knoten wie *Event Horizon*. Sie können auch sehen, dass mehr Film-Viewer *Independence Day* vor *Cold Mountain* bewertet haben als dieselben Filme in der umgekehrten Reihenfolge. Beachten Sie, dass die Pfeile nicht darauf hinweisen, dass die Betrachter *Independence Day* und dann *Cold Mountain* unmittelbar danach bewertet haben oder umgekehrt. Vielleicht haben die Zuschauer dazwischen andere Filme bewertet, aber diese Filme werden nicht auf dieser Karte angezeigt.

## 2D-Metrikzuordnungen {#section-a9b846fc71224058918fbc378315effe}

Zweidimensionale Metrikzuordnungen sind ein Typ von 2D-Prozesszuordnung, mit der Knoten basierend auf dem Wert einer bestimmten Metrik positioniert werden. In vielen Fällen ist die mit der 2D-Metrikzuordnung verwendete Metrik entweder &quot;Konversion&quot;oder &quot;Treue&quot;. Mithilfe von Umrechnungs- und Aufbewahrungskarten können Sie erkennen, welche Schritte in den Prozessen Ihrer kundenorientierten Kanäle die Kundenkonvertierung und -bindung beeinflussen.

>[!NOTE]
>
>Die Metrik, die Sie mit einer 2D-Metrikzuordnung verwenden, muss als Prozentsatz ausgedrückt werden.

In einer Konversionsmetrikzuordnung werden Knoten mit einer Konversionsrate von 0 Prozent links im Diagramm dargestellt und Seiten mit einer Konvertierung von 100 Prozent werden rechts abgebildet. Die Aktivität zwischen Knoten wird angezeigt, sodass Sie leicht erkennen können, welche Schritte in einem Prozess zu einer erhöhten oder verringerten Konvertierung führen und welche Schritte zum Abbruch führen. Eine Prozesskonversionsanalyse ist eine effektive Möglichkeit, Prozesse zu vergleichen oder verschiedene Implementierungen desselben Prozesses zu vergleichen.

![](assets/vis_2DMetricMap_Conversion.png)

Auf ähnliche Weise zeigen Treuemaps Elemente mit einer 0-prozentigen Beibehaltung links im Diagramm und Elemente mit einer 100-prozentigen Beibehaltung auf der rechten Seite an. Sie können die Treuerate für jeden Knoten auf der Karte sehen, was Ihnen dabei hilft festzustellen, welche Elemente Kunden beeinflussen, zurückzugeben.

![](assets/vis_2DMetricMap_Retention.png)

>[!NOTE]
>
>Sie können Knoten in 2D-Metrikzuordnungen nicht horizontal verschieben. Metrikzuordnungen dienen dazu, Knoten basierend auf ihren Metrikwerten von links nach rechts zu positionieren.

## 3D-Prozesskarten {#section-80acb63ea0994af1af7faef3c6264e51}

Dreidimensionale Prozesskarten bieten eine dreidimensionale Ansicht der Aktivität zwischen Dimensionselementen. Die Höhe eines Balkens in einer 3D-Prozesszuordnung ist proportional zum Wert der mit diesem Knoten verknüpften Metrik. Wie bei 2D-Prozesskarten sind sowohl die Dicke als auch die Intensität der Connectoren zwischen zwei Knoten proportional zum Durchschnitt der Metrikwerte für diese Knoten. In einer 3D-Prozesszuordnung können Sie eine der folgenden Aufgaben ausführen:

* Knoten auswählen, verschieben, entfernen und beschriften
* Auswählen von Elementen
* Dimensionen speichern
* Andere Visualisierungen erstellen
* Farblinks aktivieren

Die 3D-Prozesskarte im folgenden Beispiel zeigt Knoten, die den Seiten einer Website entsprechen. Jede Seite ist ein Element der Dimension Seite , die in einem Datensatz definiert ist, der aus Web-Traffic-Daten besteht. Die Dimension Seite ist die Basisdimension für diese Prozesskarte.

![](assets/vis_3DProcessMap_PageNodes.png)

In diesem Beispiel sind die Höhe jedes Balkens sowie die Stärke und Intensität jedes Connectors proportional zur Metrik Sitzungen , also der Anzahl der Sitzungen, in denen die Seiten angezeigt wurden. Daher wurde eine Seite mit einer großen Leiste wie /faq/all/FAQs während mehr Sitzungen angezeigt als eine Seite mit einer kurzen Leiste, z. B. /vs/demo. Beachten Sie, dass die Verbindungen zwischen zwei Seiten nicht darauf hinweisen, dass eine Seite während einer bestimmten Sitzung unmittelbar vor oder nach der anderen angezeigt wurde. Andere Seiten wurden möglicherweise während derselben Sitzung angezeigt, aber diese Seiten werden nicht auf dieser Karte angezeigt.
