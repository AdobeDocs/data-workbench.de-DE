---
description: Mit Sensor können Sie Webanfragedaten (Ereignis- oder Protokolldaten) sowie erweiterte Messdaten erfassen.
title: Welche Daten können erfasst werden?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Welche Daten können erfasst werden?{#what-kind-of-data-can-i-acquire}

Mit Sensor können Sie Webanfragedaten (Ereignis- oder Protokolldaten) sowie erweiterte Messdaten erfassen.

Erweiterte Messdaten stehen Ihren Webservern im Rahmen ihres normalen Betriebs nicht zur Verfügung.

Die folgenden Themen werden beschrieben:

## Web Request Data {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] ermöglicht die Erfassung und den automatischen Transport von Webanfragedaten (Ereignis- oder Protokolldaten) zur Speicherung und Verarbeitung zur Analyse an einen zentralen Ort. Sofern Sie sich nicht ausdrücklich dafür entscheiden, bestimmte Anforderungstypen herauszufiltern und keine Daten zu diesen Anfragetypen zu erfassen, erfasst [!DNL Sensor] Daten zu allen GET der Webserver, auf denen sie installiert ist.

[!DNL Sensor] automatisiert diesen Datenerfassungsprozess für alle auf Ihren GET ausgeführten Anfragen und bietet im Vergleich zu alternativen Methoden zum Erwerb von Website-Anforderungsdaten erhebliche geschäftliche und technische Vorteile. Zu diesen Vorteilen zählen:

* Anforderungen, die für die Analyse und Berichterstellung nicht erforderlich sind, können herausgefiltert werden, bevor Sie Kosten für die Akquise, den Transport, die Speicherung und die Verarbeitung verursachen.
* Site-Administratoren müssen Protokolldateien im Batch-Modus weder manuell noch über ein Skript drehen.
* [!DNL Sensor] aggregiert Protokolldateien an einem zentralen Speicherort, um einen einfachen Zugriff für die Verarbeitung zu ermöglichen.
* [!DNL Sensor] organisiert Protokolldateien und speichert sie in einem gemeinsamen datenschutzbezogenen Format, sodass sie nicht vorverarbeitet werden müssen, bevor sie für Analyse- und Berichtszwecke verwendet werden können.
* Instanzen bestimmter Inhaltstypen können in die Protokolldateien aufgenommen werden, obwohl die meisten Anforderungen für einen bestimmten Inhaltstyp automatisch herausgefiltert werden.
* [!DNL Sensor] komprimiert Protokolldateieinträge, was deutlich weniger Speicherplatz erfordert, Kosten senkt und es ermöglicht, die Daten für längere Zeiträume für die Analyse verfügbar zu halten.
* [!DNL Sensor’s] Fehlertolerante Funktionen ermöglichen System- und Netzwerkfehler und stellen gleichzeitig sicher, dass die Protokolldaten an ein zentrales Repository gesendet werden.
* [!DNL Sensor] ermöglicht die Implementierung gesteuerter Experimente mit Webinhalten, Prozessen und Marketing-Kampagnen.
* [!DNL Sensor] Zeitstempel protokollieren Einträge in 100ns Einheiten, was neue Arten von Analysefunktionen ermöglicht.
* [!DNL Sensor] ermöglicht es Site-Eigentümern, nach der ersten Implementierung Daten (Messungen) zu den Protokolleinträgen hinzuzufügen, um sie bei der Analyse und Berichterstellung zu berücksichtigen.

Weitere Informationen zum Erfassen erweiterter Messdaten finden Sie unter [Erfassen grundlegender Messungen](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Erweiterte Messdaten {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] unterstützt auch die Verwendung von Seiten-Tags (oder eingebetteten Objektanforderungen) zum Erfassen von Messdaten, die Ihren Webservern im Rahmen ihres normalen Betriebs nicht zur Verfügung stehen. Seiten-Tags werden häufig zum Messen von:

* Die Anzeige einer logischen Seite auf einer dynamischen Website.
* Die Anzeige von Inhalten oder Anzeigen auf einer von Drittanbietern kontrollierten Website.
* Die Anzeige von Inhalten, die aus einem Browser-Cache oder CDN bereitgestellt werden.
* Detaillierte Informationen zum Browser eines Besuchers, einschließlich Messungen wie Seitenladezeit, Bildschirmauflösung, vom Besucher ausgefüllte Formularfelder usw.
* Andere Daten, die von Browsern nicht anderweitig an Ihre Webserver gesendet werden.

[!DNL Sensor] erfasst alle Informationen, die in einer GET-Anfrage an einen Webserver platziert werden, der ausgeführt  [!DNL Sensor]wird. Solche Anfragen können aus eingebetteten Objektanfragen beliebiger Art stammen, um entweder einfach zu messen, ob die Anfrage von einem bestimmten Browser zu einem bestimmten Zeitpunkt erfolgte, oder um andere Messdaten in den Datenerfassungsstream zu übergeben, damit sie zu Analyse- und Berichtszwecken verarbeitet werden können.

[!DNL Sensor] bietet die beste Lösung sowohl für die clientseitige als auch für die serverseitige Datenerfassung. Sie erfasst Ihre serverseitigen Web-Protokolldaten und erfasst clientseitige, Drittanbieter-Site- oder Cache-Busting-Messungen, die von eingebetteten Objektanfragen durchgeführt werden. Mit anderen Worten: [!DNL Sensor] erfasst sowohl die Anforderungsdaten, die Ihren Webservern normalerweise bekannt sind (serverseitige Messungen), als auch alle zusätzlichen Messdaten, die Sie durch die Verwendung von Seiten-Tags (clientseitige Messungen) erfassen, die ihre Daten an alle Webserver senden, auf denen [!DNL Sensor] ausgeführt wird. Solche Webserver können sich der Erfassung clientseitiger Messungen widmen, müssen dies jedoch nicht sein.

Weitere Informationen zum Erfassen erweiterter Messdaten finden Sie unter [Erfassen erweiterter Messgrößen](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
