---
description: Mit Sensor können Sie Web-Anforderungsdaten (Ereignis- oder Protokolldaten) sowie erweiterte Messdaten erfassen.
title: Welche Daten können erfasst werden?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Welche Daten können erfasst werden?{#what-kind-of-data-can-i-acquire}

Mit Sensor können Sie Web-Anforderungsdaten (Ereignis- oder Protokolldaten) sowie erweiterte Messdaten erfassen.

Für Ihre Webserver stehen im Rahmen ihres normalen Betriebs keine erweiterten Messungsdaten zur Verfügung.

Die folgenden Themen werden beschrieben:

## Webanforderungsdaten {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] ermöglicht die automatische Erfassung und den automatischen Transport von Webanforderungsdaten (Ereignis- oder Protokolldaten) zur Datenspeicherung und Verarbeitung zur Analyse an einen zentralen Ort. Sofern Sie nicht ausdrücklich bestimmte Anforderungstypen herausfiltern und keine Daten zu diesen Anforderungstypen erfassen, erfasst [!DNL Sensor] Daten zu allen GET der Webserver, auf denen sie installiert ist.

[!DNL Sensor] automatisiert diesen Datenerfassungsprozess für alle auf Ihren Servern ausgeführten GET und bietet im Vergleich zu anderen Methoden zum Erwerb von Website-Anforderungsdaten erhebliche geschäftliche und technische Vorteile. Zu diesen Vorteilen zählen:

* Anforderungen, die für Analyse und Berichte nicht erforderlich sind, können ausgefiltert werden, bevor Ihnen Kosten für Akquise, Transport, Datenspeicherung und Verarbeitung entstehen.
* Site-Administratoren müssen Protokolldateien nicht im Stapelverfahren drehen, weder manuell noch über ein Skript.
* [!DNL Sensor] Aggregate protokollieren Dateien an einem zentralen Speicherort, um einen einfachen Zugriff für die Verarbeitung zu ermöglichen.
* [!DNL Sensor] organisiert und speichert Protokolldateien in einem gängigen Datenspeicherformat, sodass sie nicht mehr vorverarbeitet werden müssen, bevor sie für Analyse und Berichte verwendet werden können.
* Instanzen bestimmter Inhaltstypen können in die Protokolldateien aufgenommen werden, auch wenn die meisten Anforderungen für einen bestimmten Inhaltstyp automatisch herausgefiltert werden.
* [!DNL Sensor] komprimiert Protokolldateieinträge, was deutlich weniger Platz in der Datenspeicherung erfordert, was Kosten senkt und die Analyse der Daten über längere Zeiträume hinweg ermöglicht.
* [!DNL Sensor’s] Fehlertolerante Funktionen ermöglichen Systemfehler und Netzwerkfehler, während gleichzeitig der Versand der Protokolldaten an ein zentrales Repository sichergestellt wird.
* [!DNL Sensor] ermöglicht die Implementierung von kontrollierten Experimenten mit Webinhalten, Prozessen und Marketing-Kampagnen.
* [!DNL Sensor] Zeitstempel protokollieren Einträge in Einheiten von 100 ns, was neue Arten von Analysefunktionen ermöglicht.
* [!DNL Sensor] ermöglicht es Site-Eigentümern, nach der ersten Implementierung Daten (Messungen) zu den Protokolleinträgen hinzuzufügen, um sie in Analyse und Berichte zu berücksichtigen.

Weitere Informationen zum Abrufen erweiterter Messungsdaten finden Sie unter [Grundlegende Messungen erwerben](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Erweiterte Messungsdaten {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] unterstützt auch die Verwendung von Seiten-Tags (oder eingebetteten Objektanforderungen) zum Erfassen von Messungsdaten, die im Rahmen ihres normalen Betriebs nicht für Ihre Webserver verfügbar sind. Seiten-Tags werden häufig zur Messung verwendet:

* Die Anzeige einer logischen Seite in einer dynamischen Website.
* Die Anzeige von Inhalten oder Anzeigen auf einer von Drittanbietern kontrollierten Website.
* Die Anzeige von Inhalten, die aus einem Browser-Cache oder CDN bereitgestellt werden.
* Detaillierte Informationen zum Browser eines Besuchers, einschließlich Messungen wie Seitenladezeit, Bildschirmauflösung, ausgefüllte Formularfelder usw.
* Andere Daten, die nicht anderweitig von Browsern an Ihre Webserver gesendet werden.

[!DNL Sensor] erfasst alle Informationen, die in einer an einen ausgeführten Webserver gerichteten GET platziert  [!DNL Sensor]werden. Solche Anfragen können von eingebetteten Objektanforderungen jeder Art stammen, entweder um einfach zu messen, ob die Anforderung zu einem bestimmten Zeitpunkt von einem bestimmten Browser gesendet wurde, oder um andere Messungsdaten an den Datenerfassungsstream zu übergeben, damit sie für Analyse und Berichte verarbeitet werden können.

[!DNL Sensor] bietet die besten clientseitigen und serverseitigen Datenerfassungswelten - es werden serverseitige Webprotokolldaten erfasst und clientseitige, Drittanbieter-Site- oder Cache-Busting-Messungen gesammelt, die von eingebetteten Objektanforderungen ausgeführt werden. Mit anderen Worten, [!DNL Sensor] erfasst sowohl die Anforderungsdaten, die Ihren Webservern normalerweise bekannt sind (serverseitige Messungen), als auch alle zusätzlichen Messdaten, die Sie mithilfe von Seiten-Tags (clientseitige Messungen) erfassen, die ihre Daten an Webserver senden, auf denen &lt; a1/> ausgeführt wird. [!DNL Sensor] Solche Webserver können sich der Erfassung clientseitiger Messungen widmen, müssen aber nicht unbedingt sein.

Weitere Informationen zum Abrufen erweiterter Messungsdaten finden Sie unter [Akquieren erweiterter Messungen](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
