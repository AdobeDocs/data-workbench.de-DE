---
description: Die Angebot-Visualisierungen für Steigerungs- und Gewinn-Diagramme zur Bewertung der potenziellen Leistung eines bewerteten Modells zur Leistungsbewertung über definierte Teile der Audience.
title: Diagramme für Tendenz-Gain und -Lift
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 1%

---

# Diagramme für Tendenz-Gain und -Lift{#propensity-gain-and-lift-charts}

Die Angebot-Visualisierungen für Steigerungs- und Gewinn-Diagramme zur Bewertung der potenziellen Leistung eines bewerteten Modells zur Leistungsbewertung über definierte Teile der Audience.

Gewinn- und Steigerungsdiagramme sind Visualisierungen, die zur Bewertung der potenziellen Leistung des bewerteten Modells erstellt wurden. Diese Diagramme bewerten die Leistung für jeden Teil der Bevölkerung.

**So öffnen Sie ein Lift- oder Gewinn-Diagramm**

1. Auswählen [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Bewegen Sie den Mauszeiger über **[!UICONTROL Model Complete]** eines gespeicherten Ergebnisses.

![](assets/propensity_lift_gain_1.png)

**Informationen zu Steigerungs- und Gewinndiagrammen**

Die Lift- und Gewinn-Diagramme sind nützliche visuelle Werkzeuge zur Messung des Werts eines Vorhersagemodells. Beide Diagramme bestehen aus einer Steigerungskurve (grün) und einer Grundlinie (rosa). Für das **Gewinn-Diagramm** stellt der Abstand zwischen der Steigerungskurve und der Grundlinie dar, wie stark Sie die Performance der Antworten (oder den &quot;Gewinn&quot;) aus der Verwendung des Vorhersagemodus verbessern können. Der Gewinn wird durch Priorisierung und Targeting der Potenzieller Kunde (Kunden/Besucher) erzielt, die am ehesten umgerechnet werden, und nicht durch zufällige Marketingmaßnahmen zu Kunden/Besuchern. Auf diese Weise können Sie den erwarteten Wert der Verwendung des Vorhersagemodells quantifizieren, um auszuwählen, welche Potenzieller Kunde kontaktiert werden sollen.

Ähnlich wie im Gewinn-Diagramm zeigt das **Lift-Diagramm** an, wie viel wahrscheinlicher positive Antworten Sie erhalten, als wenn Sie zufällig Potenzieller Kunde kontaktiert haben. Sie möchten, dass der Abstand zwischen der Steigerungskurve und der Grundlinie so groß wie möglich ist, was höhere erwartete Gewinne durch die Verwendung des Prognosemodells zur Kontaktaufnahme mit Kunden darstellt. Mathematisch sind die Gewinn- und Steigerungsdiagramme wie folgt definiert:

* **Gewinn** = (Erwartete Antwort mit dem Prädiktivmodell für Kontaktpersonen) / (Erwartete Reaktion von zufällig kontaktierenden Potenzieller Kunden)
* **Steigerung** = (Erwartete Reaktion unter einer bestimmten Gruppengröße, die anhand des Prognosemodells identifiziert wurde) / (Erwartete Reaktion unter derselben spezifischen Gruppengröße von Potenzieller Kunden, die als Zufallszahl identifiziert wurden)

**Beispiel für Lift- und Gewinn-Diagramme**

Betrachten Sie beispielsweise das Beispiel eines Einzelhändlers, der eine E-Mail-Remarketing-Kampagne starten möchte, um Yoga-Hosen zu verkaufen. Historisch betrachtet erwartet der Analyst eine durchschnittliche Antwortquote von 20 Prozent basierend auf früheren E-Mail-Remarketing-Kampagnen, die dieser ähneln. Während der Analyst fast 5 Millionen Kunden in seiner E-Mail-Datenbank hat, möchte das Unternehmen nur diejenigen Kunden auf den Markt bringen, die mit der größten Wahrscheinlichkeit auf die E-Mail und den Kauf reagieren. Auf diese Weise wird die Firma den ROI der Kampagne maximieren und gleichzeitig sicherstellen, dass sie nicht unnötig E-Mails an uninteressierte Kunden versenden. Bei einer erwarteten Antwortquote von 20 Prozent erwarten Marketingexperten und Analytiker, dass ungefähr 1 Million Kunden wahrscheinlich reagieren und kaufen. Anstatt zufällig zu erraten, welche dieser Kunden zu den 20 Prozent Antworten gehören werden, möchte der Analysten schlau vorgehen, um vorherzusagen, welche der 1 Million Potenzieller Kunde (unter den 5 Millionen Kunden) am ehesten reagieren.

Mithilfe der Scoring-Funktion der Adobe definiert der Analyst den Erfolg als Potenzieller Kunde, der auf eine E-Mail klickt, und kauft Yoga Hots (die abhängige Variable). Nach der Auswahl der unabhängigen Variablen (basierend auf den Erfahrungen und Kenntnissen, die bei der Analyse von Datenkorrelationen und der Audience-Clustering unter anderem gesammelt wurden) wird jeder Potenzieller Kunde bewertet, wie wahrscheinlich es ist, dass er positiv auf die E-Mail-Remarketing-Kampagne reagiert (indem er auf die E-Mail klickt und Yoga-Pants kauft). Der Analyst öffnet die resultierenden Gewinn- und Steigerungsdiagramme basierend auf dem Vorhersagemodell.

Die Y-Achse zeigt den Prozentsatz der kumulativen erwarteten positiven Antworten. In unserem Beispiel erwarten wir insgesamt 1 Million positive Antworten. Ein Wert von 20 % auf der Y-Achse entspricht 20 % der erwarteten positiven Reaktionen von 1 Million bzw. 200 000 positiven Antworten. Die X-Achse zeigt den Prozentsatz der potenziellen Kunden an, die kontaktiert wurden. In unserem Beispiel stellt die X-Achse einen Bruchteil der 5 Millionen Kunden in der E-Mail-Datenbank dar. Die Baseline (Pink) ist die Gesamtansprechrate - wenn Sie mit X% der Potenzieller Kunde Kontakt aufnehmen, erhalten Sie X% der insgesamt positiven Antworten. Anhand des Vorhersagemodells zeigt die Steigerungskurve (grün) den Prozentsatz der positiven Reaktionen an, die erzielt werden (y-Achse), indem ein bestimmter Prozentsatz von Potenzieller Kunden (x-Achse) kontaktiert wird.

Das Lift-Diagramm zeigt die erwartete Steigerung an, die sich aus der Verwendung des Vorhersagemodells ergibt, um die 1 Million Potenzieller Kunde zu ermitteln, die am ehesten Yoga-Hosen kaufen, nachdem sie die E-Mail erhalten und auf sie geklickt haben. Für die Kontaktaufnahme mit 20 Prozent der zufällig ausgewählten Potenzieller Kunde ohne Prognosemodell sollten Sie mit 20 Prozent der Befragten rechnen. Wenn Sie jedoch das Vorhersagemodell verwenden, um die 20 Prozent der Potenzieller Kunde zu identifizieren, die am ehesten reagieren, erhalten Sie 50 % der Antwortsender. Der y-Wert der Steigerungskurve bei 20 Prozent ist 50/20 = 2,5. Das Lift-Diagramm zeigt an, wie viel wahrscheinlicher die Befragten sind, als wenn Sie eine zufällige Stichprobe von Potenzieller Kunden kontaktieren. Wenn Sie z. B. nur 20 Prozent der Potenzieller Kunde auf der Grundlage des Vorhersagemodells kontaktieren, erreichen Sie 2,5 Mal so viele Befragte, als dass Sie kein Vorhersagemodell verwendet haben.
