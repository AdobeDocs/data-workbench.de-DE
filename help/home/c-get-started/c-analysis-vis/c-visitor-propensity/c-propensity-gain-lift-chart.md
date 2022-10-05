---
description: Die Diagramme für Steigerung und Gewinn bieten Visualisierungen zur Bewertung der potenziellen Leistung eines bewerteten Modells, um die Leistung über definierte Teile der Zielgruppe auszuwerten.
title: Diagramme für Tendenz-Gain und -Lift
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 1%

---

# Diagramme für Tendenz-Gain und -Lift{#propensity-gain-and-lift-charts}

{{eol}}

Die Diagramme für Steigerung und Gewinn bieten Visualisierungen zur Bewertung der potenziellen Leistung eines bewerteten Modells, um die Leistung über definierte Teile der Zielgruppe auszuwerten.

Gewinn- und Steigerungsdiagramme sind Visualisierungen, mit denen die potenzielle Leistung des bewerteten Modells bewertet wird. In diesen Diagrammen wird die Leistung für jeden Teil der Population bewertet.

**So öffnen Sie ein Lift- oder Gewinn-Diagramm**

1. Auswählen [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Bewegen **[!UICONTROL Model Complete]** eines gespeicherten Punktes.

![](assets/propensity_lift_gain_1.png)

**Über Steigerungs- und Gewinndiagramme**

Die Diagramme für Steigerung und Gewinn sind nützliche visuelle Werkzeuge zur Messung des Werts eines prädiktiven Modells. Beide Diagramme bestehen aus einer Steigerungskurve (grün) und einer Grundlinie (rosa). Für **Gewinndiagramm**, zeigt der Abstand zwischen der Steigerungskurve und der Grundlinie an, wie stark Sie die Leistung bei Antworten (oder den &quot;Gewinn&quot;) verbessern können, wenn Sie den Prognosemodus verwenden. Der Gewinn wird erzielt, indem die Interessenten (Kunden/Besucher), die am ehesten konvertieren, priorisiert und gezielt angesprochen werden, anstatt dass Marketing zufällig zu Kunden/Besuchern führt. Auf diese Weise können Sie den erwarteten Wert quantifizieren, indem Sie mithilfe des Vorhersagemodells auswählen, welche Perspektiven kontaktiert werden sollen.

Ähnlich wie das Gewinndiagramm wird die **Steigerungsdiagramm** zeigt, wie viel wahrscheinlicher Sie positive Antworten erhalten, als wenn Sie potenzielle Kontakte zufällig kontaktiert haben. Sie möchten, dass der Abstand zwischen der Steigerungskurve und der Grundlinie so groß wie möglich ist, was höhere erwartete Gewinne durch die Verwendung des Prognosemodells zur Kontaktaufnahme mit Kunden darstellt. Mathematisch werden die Diagramme für Gewinn und Steigerung wie folgt definiert:

* **Gewinn** = (Erwartete Antwort mit dem prädiktiven Modell für Kontaktaussichten) / (Erwartete Antwort von zufällig kontaktierenden Perspektiven)
* **Steigerung** = (Erwartete Antwort unter einer bestimmten Gruppengröße von mithilfe des prädiktiven Modells identifizierten Perspektiven) / (Erwartete Antwort unter derselben spezifischen Gruppengröße der zufällig identifizierten Perspektiven)

**Beispiel für Diagramme zu Steigerung und Gewinn**

Betrachten Sie beispielsweise das Beispiel eines Einzelhändlers, der eine E-Mail-Remarketing-Kampagne starten möchte, um Yoga-Hosen zu verkaufen. In der Vergangenheit erwartet der Analytiker basierend auf früheren E-Mail-Remarketing-Kampagnen, die dieser ähneln, eine durchschnittliche Reaktionsrate von 20 Prozent. Während der Analyst fast 5 Millionen Kunden in seiner E-Mail-Datenbank hat, möchte das Unternehmen nur an Kunden vermarkten, die am ehesten auf die E-Mail und den Kauf reagieren. Auf diese Weise wird das Unternehmen den ROI der Kampagne maximieren und gleichzeitig sicherstellen, dass es nicht unnötig E-Mails an uninteressierte Kunden sendet. Bei einer erwarteten Reaktionsrate von 20 Prozent erwarten Marketingexperten und Analytiker, dass rund 1 Million Kunden wahrscheinlich reagieren und kaufen. Anstatt zufällig zu vermuten, welche dieser Kunden zu den 20 Prozent-Antworten zählen wird, möchte der Analytiker intelligente Vorhersagen darüber treffen, welche der 1 Million potenziellen Kunden (unter der Datenbank von 5 Millionen Kunden) am ehesten reagieren.

Mithilfe der Zielgruppen-Scoring-Funktion von Adobe definiert der Analyst den Erfolg als potenziellen Klick auf eine E-Mail und Kauf von Yoga-Hots (der abhängigen Variablen). Nach Auswahl der unabhängigen Variablen (basierend auf Erfahrungen und Kenntnissen aus der Analyse von Datenkorrelationen und Zielgruppen-Clustering unter anderen Analysen) wird jeder Interessent über seine Wahrscheinlichkeit bewertet, positiv auf die E-Mail-Remarketing-Kampagne zu reagieren (Klick auf die E-Mail und Kauf von Yoga-Pants). Der Analytiker öffnet die resultierenden Gewinn- und Steigerungsdiagramme basierend auf dem Prognosemodell.

Die Y-Achse zeigt den Prozentsatz der kumulativen erwarteten positiven Antworten. In unserem Beispiel erwarten wir insgesamt 1 Million positive Antworten. Ein Wert von 20 % auf der Y-Achse entspricht 20 % der erwarteten positiven Reaktionen von 1 Million bzw. 200.000 positiven Antworten. Die X-Achse zeigt den Prozentsatz der kontaktierten potenziellen Kunden. In unserem Beispiel stellt die X-Achse einen Bruchteil der 5 Millionen Kunden in der E-Mail-Datenbank dar. Die Baseline (rosa) ist die Gesamtansprechrate. Wenn Sie X% der Interessenten kontaktieren, erhalten Sie X% der gesamten positiven Antworten. Unter Verwendung des Vorhersagemodells zeigt die Steigerungskurve (grün) den Prozentsatz der positiven Reaktionen an, die erzielt wurden (y-Achse), indem ein bestimmter Prozentsatz von Interessenten kontaktiert wird (x-Achse).

Das Diagramm Steigerung zeigt die erwartete Steigerung infolge der Verwendung des Prognosemodells zur Bestimmung der Top-1-Millionen-Interessenten an, die am ehesten Yoga-Hosen kaufen, nachdem sie die E-Mail erhalten und geklickt haben. Für die Kontaktaufnahme von 20 Prozent der zufällig ausgewählten Interessenten ohne Prognosemodell sollten Sie mit 20 Prozent der Antwortenden rechnen. Wenn Sie jedoch das Prognosemodell verwenden, um die 20 % der besten potenziellen Reaktionen zu ermitteln, erwarten Sie 50 % der Antwortenden. Der y-Wert der Steigerungskurve bei 20 Prozent ist 50/20 = 2,5. Das Steigerungsdiagramm zeigt, wie viel wahrscheinlicher Sie Befragte erhalten, als wenn Sie eine zufällige Stichprobe von Interessenten kontaktieren. Wenn Sie beispielsweise nur 20 Prozent der Interessenten auf der Basis des Vorhersagemodells kontaktieren, erreichen Sie 2,5 Mal so viele Befragte wie keine Prognosemodelle.
