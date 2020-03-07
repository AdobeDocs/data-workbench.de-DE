---
description: Sensor ermöglicht Ihnen die Erfassung von Webanforderungsdaten (Ereignis- oder Protokolldaten) sowie erweiterter Messungsdaten.
solution: Analytics
title: Welche Daten kann ich erlangen?
topic: Data workbench
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Welche Daten kann ich erlangen?{#what-kind-of-data-can-i-acquire}

Sensor ermöglicht Ihnen die Erfassung von Webanforderungsdaten (Ereignis- oder Protokolldaten) sowie erweiterter Messungsdaten.

Für Ihre Webserver stehen im Rahmen ihres normalen Betriebs keine erweiterten Messungsdaten zur Verfügung.

Die folgenden Themen werden beschrieben:

## Webanforderungsdaten {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] ermöglicht die Erfassung und den automatischen Transport von Webanforderungsdaten (Ereignis- oder Protokolldaten) zur Speicherung und Verarbeitung zur Analyse an einen zentralen Ort. Sofern Sie nicht ausdrücklich entscheiden, bestimmte Anforderungstypen auszufiltern und keine Daten über diese Anforderungstypen zu erfassen, werden Daten über alle GET-Anforderungen der Webserver erfasst, auf denen sie installiert sind. [!DNL Sensor]

[!DNL Sensor] automatisiert diesen Datenerfassungsprozess für alle GET-Anforderungen, die auf Ihren Servern ausgeführt werden, und bietet erhebliche geschäftliche und technische Vorteile gegenüber alternativen Methoden zum Erwerb von Website-Anforderungsdaten. Zu diesen Vorteilen zählen:

* Anforderungen, die für die Analyse und Berichterstellung unnötig sind, können herausgefiltert werden, bevor Ihnen Kosten für Akquise, Transport, Lagerung und Verarbeitung entstehen.
* Site-Administratoren müssen Protokolldateien nicht im Stapelverfahren drehen, weder manuell noch über ein Skript.
* [!DNL Sensor] aggregiert Protokolldateien an einem zentralen Speicherort, um einen einfachen Zugriff für die Verarbeitung zu ermöglichen.
* [!DNL Sensor] organisiert und speichert Protokolldateien in einem gängigen datenschutzfreundlichen Format, sodass sie nicht mehr vorverarbeitet werden müssen, bevor sie für Analyse- und Berichterstellungszwecke verwendet werden können.
* Instanzen bestimmter Inhaltstypen können in die Protokolldateien aufgenommen werden, auch wenn die meisten Anforderungen für einen bestimmten Inhaltstyp automatisch herausgefiltert werden.
* [!DNL Sensor] komprimiert Protokolldateieinträge, was deutlich weniger Speicherplatz erfordert, was Kosten senkt und eine längere Verfügbarkeit der Daten für die Analyse ermöglicht.
* [!DNL Sensor’s] Fehlertolerante Funktionen ermöglichen System- und Netzwerkfehler und stellen gleichzeitig sicher, dass die Protokolldaten an ein zentrales Repository gesendet werden.
* [!DNL Sensor] ermöglicht die Implementierung von kontrollierten Experimenten mit Webinhalten, Prozessen und Marketingkampagnen.
* [!DNL Sensor] Zeitstempel protokollieren Einträge in Einheiten von 100 ns, was neue Arten von Analysefunktionen ermöglicht.
* [!DNL Sensor] ermöglicht es Site-Eigentümern, Daten (Messungen) zu den Protokolleinträgen nach der ersten Implementierung hinzuzufügen, um sie bei der Analyse und Berichterstellung zu berücksichtigen.

Weitere Informationen zum Abrufen erweiterter Messungsdaten finden Sie unter [Grundlegende Messungen](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe)abrufen.

## Erweiterte Messdaten {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] unterstützt auch die Verwendung von Seiten-Tags (oder eingebetteten Objektanforderungen) zum Erfassen von Messungsdaten, die im Rahmen ihres normalen Betriebs nicht für Ihre Webserver verfügbar sind. Seiten-Tags werden häufig zur Messung verwendet:

* Die Anzeige einer logischen Seite in einer dynamischen Website.
* Die Anzeige von Inhalten oder Anzeigen auf einer von Drittanbietern kontrollierten Website.
* Die Anzeige von Inhalten, die aus einem Browser-Cache oder CDN bereitgestellt werden.
* Detaillierte Informationen zum Browser eines Besuchers, einschließlich Messungen wie Seitenladezeit, Bildschirmauflösung, ausgefüllte Formularfelder usw.
* Andere Daten, die nicht anderweitig von Browsern an Ihre Webserver gesendet werden.

[!DNL Sensor] erfasst alle Informationen, die in einer GET-Anforderung an einen Webserver platziert werden, der ausgeführt wird [!DNL Sensor]. Solche Anfragen können von eingebetteten Objektanforderungen jeder Art stammen, entweder um einfach zu messen, ob die Anforderung zu einem bestimmten Zeitpunkt von einem bestimmten Browser gesendet wurde, oder um andere Messungsdaten an den Datenerfassungsstream zu übergeben, damit sie für Analyse- und Berichterstattungszwecke verarbeitet werden können.

[!DNL Sensor] bietet die besten clientseitigen und serverseitigen Datenerfassungswelten - es werden serverseitige Webprotokolldaten erfasst und clientseitige, Drittanbieter-Site- oder Cache-Busting-Messungen gesammelt, die von eingebetteten Objektanforderungen ausgeführt werden. Mit anderen Worten, [!DNL Sensor] erfasst sowohl die Anforderungsdaten, die Ihren Webservern normalerweise bekannt sind (serverseitige Messungen), als auch alle zusätzlichen Messdaten, die Sie mithilfe von Seiten-Tags (clientseitige Messungen) erfassen, die ihre Daten an alle Webserver senden, die ausgeführt werden, [!DNL Sensor]. Solche Webserver können sich der Erfassung clientseitiger Messungen widmen, müssen aber nicht unbedingt sein.

Weitere Informationen zum Abrufen erweiterter Messungsdaten finden Sie unter [Akquise erweiterter Messungen](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
