---
description: Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Laufe der Zeit zu verfolgen.
solution: Analytics
title: Das v1st-Cookie
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Das v1st-Cookie{#understanding-the-v-st-cookie}

Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Laufe der Zeit zu verfolgen.

Wenn ein bestimmter Browser (als Besucher bezeichnet) zum ersten Mal eine Anforderung Ihrer Website sendet, [!DNL Sensor] wird mit Ihrem Webserver ein beständiges Cookie (cs(cookie)(v1st) gesetzt, das intern im System als x-trackingid interpretiert wird. Dieses beständige Cookie wird zusätzlich zu jedem anderen Cookie gesetzt, das Ihre Site andernfalls setzen könnte. Dieses Cookie optimiert Ihre Fähigkeit, Besucher über mehrere Sitzungen zu verfolgen, was viele Analysetypen ermöglicht, die sonst unmöglich wären.

[!DNL Sensor] weist einen 64-Bit-numerischen Schlüssel im Cookie zu, um neue Besucher zu identifizieren, die eine Anforderung der Site als eindeutige Kennung stellen. Wenn der [!DNL Sensor] Benutzer eine Anforderung von einem Browser sieht, prüft er, ob &quot;cs(cookie)(v1st)&quot;, ein beständiges Erstanbieter-Cookie, das von festgelegt wird, in den Anforderungsdaten vorhanden [!DNL Sensor]ist. Wenn &quot;cs(cookie)(v1st)&quot;nicht vorhanden ist, weist [!DNL Sensor]der Browser über Ihren Webserver an, die Variable einzustellen. Im Gegensatz zu anderen Lösungen [!DNL Sensor] kann dieses Cookie bei der ersten Anforderung des Besuchers gesetzt werden.

Unten sehen Sie den standardmäßigen persistenten Cookie-Header, der nach der ersten Anforderung Ihrer Site durch Ihren Webserver an den Browser gesendet wird, in Richtung [!DNL Sensor]. Das Format kann zum Zeitpunkt der Konfiguration definiert werden, wenn ein anderer Name oder ein anderes Ablaufdatum gewünscht wird. Beispiel:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Dieses Cookie wird nur einmal gesetzt, und zwar bei der ersten Anforderung, die der Besucher an Ihre Site gesendet hat. Er wird dann jedes Mal von diesem Besucher erfasst, wenn dieser Browser eine Anforderung (entweder eine Seite oder eine eingebettete Objektanforderung) Ihrer Site in Zukunft stellt. Das Cookie ist sehr klein, um die Bandbreite zu minimieren, die für die Übertragung an Ihre Server bei jeder Anforderung von diesem Browser auf Ihre Site verwendet wird.

Die Annahme eines beständigen Cookies liegt im Ermessen des Browsers. Die meisten Webbenutzer verstehen, was Cookies tun, und erkennen auch, dass Erstanbieter-Cookies ihnen einen wertvollen Vorteil bieten, da sie es ihnen ermöglichen, Site-Inhalte an ihre Vorlieben anzupassen. Diese Erstanbieter-Cookies werden nicht durch die Standardsicherheitseinstellungen der gängigen Browser blockiert. Wenn ein Benutzer sich dafür entscheidet, Erstanbieter-Cookies zu blockieren, werden seine Seitenansichtenanforderungen weiterhin protokolliert, aber die Messungsdaten aus diesen Anforderungen können nicht zuverlässig mit einem bestimmten Besucher oder dessen Sitzungen auf der Site korreliert werden. Viele Sites, besonders anspruchsvolle dynamische Sites, verwenden bereits Erstanbieter-Cookies, die in vielen Fällen erforderlich sind, damit Webanwendungen für den Besucher funktionieren können. Ein Schritt zurück von einem beständigen Cookie ist ein Sitzungs-Cookie, das die Verbindung einer Reihe von Anforderungen zu einer Sitzung ermöglicht, jedoch keine Verfolgung von Besuchern zwischen Sitzungen ermöglicht. [!DNL Site] ist in der Lage, Besucherdaten basierend auf Sitzungs-Cookies oder nach IP-Nummer zu segmentieren. Beide Methoden beeinträchtigen jedoch signifikant die Art und den Wert der Analyse, die mit oder einem anderen Webaktivitätsanalyse- und Berichterstattungssystem durchgeführt werden kann, [!DNL Site] und beeinträchtigen diese erheblich.
