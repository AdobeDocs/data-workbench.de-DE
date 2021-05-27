---
description: Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Zeitverlauf zu verfolgen.
title: Grundlagen zum v1st-Cookie
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Grundlagen zum v1st-Cookie{#understanding-the-v-st-cookie}

Site verwendet Cookies, um Besucher Ihrer Website eindeutig zu identifizieren und ihr Verhalten im Zeitverlauf zu verfolgen.

Wenn ein bestimmter Browser (als Besucher betrachtet) zum ersten Mal Ihre Website anfordert, arbeitet [!DNL Sensor] mit Ihrem Webserver zusammen, um ein beständiges Cookie, cs(cookie)(v1st), zu setzen, das intern im System als x-trackingid interpretiert wird. Dieses persistente Cookie wird zusätzlich zu jedem anderen Cookie gesetzt, das andernfalls auf Ihrer Site gesetzt wird. Dieses Cookie optimiert Ihre Fähigkeit, Ihre Besucher über mehrere Sitzungen hinweg zu verfolgen, was viele Analysetypen ermöglicht, die sonst nicht möglich sind.

[!DNL Sensor] weist dem Cookie einen numerischen 64-Bit-Schlüssel zu, um neue Besucher zu identifizieren, die eine Anforderung der Site als eindeutige Kennung stellen. Wenn das [!DNL Sensor] eine Anforderung von einem Browser sieht, wird überprüft, ob &quot;cs(cookie)(v1st)&quot;, ein von [!DNL Sensor] festgelegtes persistentes Erstanbieter-Cookie, in den Anfragedaten vorhanden ist. Wenn &quot;cs(cookie)(v1st)&quot;nicht vorhanden ist, teilt [!DNL Sensor] dem Browser über Ihren Webserver mit, dass er sie festlegt. Im Gegensatz zu anderen Lösungen kann [!DNL Sensor] dieses Cookie in der ersten Anforderung des Besuchers setzen.

Unten finden Sie die standardmäßige persistente Cookie-Kopfzeile, die von Ihrem Webserver bei der ersten Anforderung Ihrer Site an den Browser gesendet wird, in Richtung [!DNL Sensor]. Das Format kann zum Zeitpunkt der Konfiguration definiert werden, wenn ein anderer Name oder ein anderes Ablaufdatum gewünscht wird. Beispiel:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Dieses Cookie wird nur einmal bei der allerersten Anforderung des Besuchers an Ihre Site gesetzt. Er wird dann jedes Mal von diesem Besucher erfasst, wenn dieser Browser eine Anforderung (entweder eine Seite oder eine eingebettete Objektanforderung) Ihrer Site in der Zukunft sendet. Das Cookie ist sehr klein, um die Bandbreite zu minimieren, die für die Übertragung an Ihre Server bei jeder Anforderung von diesem Browser an Ihre Site verwendet wird.

Das Akzeptieren eines persistenten Cookies liegt im Ermessen des Browsers. Die meisten Webbenutzer verstehen, was Cookies tun, und erkennen auch, dass Erstanbieter-Cookies ihnen einen wertvollen Vorteil bieten, da sie es ermöglichen, Site-Inhalte an ihre Voreinstellungen anzupassen. Diese Erstanbieter-Cookies werden nicht durch die Standardsicherheitseinstellungen der gängigen Browser blockiert. Wenn ein Benutzer Erstanbieter-Cookies blockiert, werden seine Seitenansichtsanforderungen weiterhin protokolliert, aber die Messdaten aus diesen Anforderungen können nicht zuverlässig mit einem bestimmten Besucher oder dessen Sitzungen auf der Site korreliert werden. Viele Websites, insbesondere komplexe dynamische Sites, verwenden bereits Erstanbieter-Cookies, die in vielen Fällen erforderlich sind, damit Webanwendungen für den Besucher funktionieren können. Ein Schritt zurück von einem beständigen Cookie ist ein Sitzungs-Cookie, das es ermöglicht, eine Reihe von Anforderungen in eine Sitzung einzufügen, jedoch kein Besucher-Tracking zwischen Sitzungen zulässt. [!DNL Site] ist in der Lage, Besucherdaten auf der Grundlage von Sitzungs-Cookies oder anhand der IP-Nummer zu segmentieren. Beide Methoden beeinträchtigen jedoch erheblich die Analysetypen und -werte, die mit  [!DNL Site] oder einem anderen Web-Aktivitäts-Analyse- und Berichterstattungssystem durchgeführt werden können.
