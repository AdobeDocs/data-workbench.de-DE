---
description: Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Laufe der Zeit zu verfolgen.
title: Grundlagen zum v1st-Cookie
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Grundlagen zum v1st-Cookie{#understanding-the-v-st-cookie}

Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Laufe der Zeit zu verfolgen.

Wenn ein bestimmter Browser (als Besucher bezeichnet) zum ersten Mal eine Anfrage an Ihre Website sendet, arbeitet [!DNL Sensor] mit Ihrem Webserver zusammen, um ein beständiges Cookie zu setzen, cs(cookie)(v1st), das intern im System als x-trackingid interpretiert wird. Dieses beständige Cookie wird zusätzlich zu jedem anderen Cookie gesetzt, das Ihre Site andernfalls setzen könnte. Dieses Cookie optimiert Ihre Fähigkeit, Ihre Besucher über mehrere Sitzungen zu verfolgen, was viele andere Analysen ermöglicht, die sonst nicht möglich wären.

[!DNL Sensor] weist einen 64-Bit-numerischen Schlüssel im Cookie zu, um neue Besucher zu identifizieren, die eine Anforderung der Site als eindeutige Kennung stellen. Wenn das [!DNL Sensor] eine Anforderung von einem Browser anzeigt, prüft es, ob &quot;cs(cookie)(v1st)&quot;, ein von [!DNL Sensor] festgelegtes beständiges Erstanbieter-Cookie, in den Anforderungsdaten vorhanden ist. Wenn cs(cookie)(v1st) nicht vorhanden ist, weist [!DNL Sensor] den Browser über Ihren Webserver an, ihn einzustellen. Im Gegensatz zu anderen Lösungen kann [!DNL Sensor] dieses Cookie bei der ersten Anforderung des Besuchers setzen.

Unten sehen Sie den standardmäßigen persistenten Cookie-Header, der nach der ersten Anforderung Ihrer Site durch Ihren Webserver an den Browser gesendet wird, in Richtung [!DNL Sensor]. Das Format kann zum Zeitpunkt der Konfiguration definiert werden, wenn ein anderer Name oder ein anderes Ablaufdatum gewünscht wird. Beispiel:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Dieses Cookie wird nur einmal gesetzt, und zwar bei der ersten Anforderung, die der Besucher an Ihre Site gesendet hat. Er wird dann jedes Mal, wenn der Browser eine Anforderung (eine Seite oder eine eingebettete Objektanforderung) Ihrer Site aufnimmt, von diesem Besucher erfasst. Das Cookie ist sehr klein, um die Bandbreite zu minimieren, die für die Übertragung an Ihre Server bei jeder Anforderung von diesem Browser auf Ihre Site verwendet wird.

Die Annahme eines beständigen Cookies liegt im Ermessen des Browsers. Die meisten Webbenutzer verstehen, was Cookies tun, und erkennen auch, dass Erstanbieter-Cookies ihnen einen wertvollen Vorteil bieten, da sie es ihnen ermöglichen, Site-Inhalte an ihre Vorlieben anzupassen. Diese Erstanbieter-Cookies werden nicht durch die Standardsicherheitseinstellungen der gängigen Browser blockiert. Wenn ein Benutzer sich dafür entscheidet, Erstanbieter-Cookies zu blockieren, werden die Seitenanfragen weiterhin protokolliert, aber die Messungsdaten aus diesen Ansichten können nicht zuverlässig mit einem bestimmten Besucher oder dessen Sitzungen auf der Site korreliert werden. Viele Sites, besonders anspruchsvolle dynamische Sites, verwenden bereits Erstanbieter-Cookies, die in vielen Fällen erforderlich sind, um Webanwendungen für den Besucher zu ermöglichen. Ein Schritt zurück von einem beständigen Cookie ist ein Sitzungs-Cookie, das die Verbindung einer Reihe von Anforderungen zu einer Sitzung ermöglicht, jedoch keine Verfolgung von Besuchern während einer Sitzung zulässt. [!DNL Site] ist in der Lage, Sitzungsdaten basierend auf Sitzungs-Cookies oder nach IP-Nummer zu segmentieren. Beide Methoden beeinträchtigen jedoch signifikant die Typen und den Wert der Analyse, die mit  [!DNL Site] oder einem anderen Web-Aktivität-Analyse- und Berichte-System durchgeführt werden können.
