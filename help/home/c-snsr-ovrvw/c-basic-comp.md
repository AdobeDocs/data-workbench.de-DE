---
description: Sensor besteht aus drei Hauptkomponenten Datenerfassung, Festplattenwarteschlange und Datenübertragung.
title: Grundlegende Komponenten
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
exl-id: aee6a601-590a-43e0-aeeb-42a4522e55c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# Grundlegende Komponenten{#what-are-basic-components}

{{eol}}

Sensor besteht aus drei Hauptkomponenten: Datenerfassung, Festplattenwarteschlange und Datenübertragung.

![](assets/Visual-Sensor.png)

## Datenerfassung {#section-f970eaff30364a3c8106d5ec9c1b5caa}

Der Datenerfasser (Collector) ist ein NSAPI-, ISAPI-, J2EE-Filter-Servlet oder Apache-Modul, das innerhalb des Webserverprozesses ausgeführt wird.

Sie erfasst die unverarbeiteten Ereignisdaten zu jeder HTTP-Anforderung, die der Webserver verarbeitet und in der Festplattenwarteschlange ablegt. Wenn Sie mehrere Instanzen eines Webservers auf demselben Computer ausführen, lädt jede Instanz ihre eigene Instanz des Sammlermoduls. Allerdings schreiben alle Instanzen des Sammlers ihre Ereignisdaten in dieselbe Datenträgerwarteschlange.

## Festplattenwarteschlange {#section-41aac77ab30e48478d1b31eac288df05}

Die Warteschlange der Festplatte (Warteschlange) ist eine fehlertolerante, FIFO-Warteschlangendatei (zuerst in, erster Out) mit Speicherzuordnung, die die von Sensor erfassten Roh-Ereignisdaten speichert und auf dem Webserver, auf dem sie installiert ist, temporären Speicher bereitstellt.

Um zu verhindern, dass die Warteschlange ohne Einschränkung erweitert wird (und damit den gesamten verfügbaren Speicherplatz belegt), wird die Warteschlange in einer Datei mit fester Größe aufbewahrt, d. h. sie enthält nur so viele Ereignisdaten wie sie gespeichert werden konnten. Die Größe der Warteschlangendatei wird beim Installieren des Sensors im Parameter QueueSize der Konfigurationsdatei für Sensor txlogd.conf konfiguriert. Informationen zu den txlogd.conf-Parametern finden Sie unter Parameter für die Datei &quot;Sensor Txlogd.conf&quot;.

Sobald die physische Länge der Datei feststeht, wächst oder schrumpft sie nicht mehr. Der Kollektor legt einfach neue Ereignisdaten in die Warteschlange und der Sender ruft Ereignisse daraus ab. Wenn der Wächter das Ende der Datei erreicht, wird er nicht mehr in die Warteschlangendatei geschrieben.

Im Allgemeinen ruft der Transmitter Ereignisse so schnell aus der Warteschlange ab, wie der Collector sie ablegt. Wenn die Verbindung zwischen dem Transmitter und Insight Server jedoch langsam ist oder nicht verfügbar ist, kann die Warteschlange mit nicht übertragenen Ereignissen gefüllt werden. In diesem Fall hört der Kollektor auf, Daten zu sammeln, bis der Transmitter die Warteschlange herunterzieht. Informationen zu Anforderungen, die der Webserver während dieser Zeit verarbeitet, gehen dauerhaft verloren.

**Bestimmen der Warteschlangengröße**

Bevor Sie Sensor installieren, müssen Sie festlegen, wie groß die Warteschlange sein muss. Um permanenten Datenverlust zu vermeiden, ist es wichtig, eine Warteschlange zu erstellen, die groß genug ist, um die Anzahl der Ereignisse aufzunehmen, die sich während des wahrscheinlichsten längeren Ausfalls der Verbindung zum Insight Server ansammeln könnten (d. h. genügend Speicher für mehrere Tage Spitzenaktivität). Die Warteschlange muss so konfiguriert sein, dass genügend Ereignisdaten gespeichert werden, damit Systemadministratoren Zeit haben, die Netzwerkzugriffsfähigkeit auf den Insight Server wiederherzustellen oder den Insight Server zu reparieren oder zu ersetzen, ohne Daten zu verlieren. Wenn der Sensor fehlgeschlagen ist und keine gültige und zugängliche Warteschlangendatei zum Speichern der Ereignisdaten verfügbar ist, gehen nachfolgende Daten verloren.

>[!NOTE]
>
>Es ist wichtig, dass die Administratoren der einzelnen Computer, auf denen Sensor ausgeführt wird, die Einzigartigkeit der lokalen Warteschlangendatei verstehen, um sicherzustellen, dass sie sie nicht als gewöhnliche Protokolldatei behandeln, die gelöscht, archiviert oder komprimiert werden kann.

Adobe empfiehlt, die Warteschlange so zu konfigurieren, dass sie mindestens zehn (10) Spitzenereignisdaten enthält, die vom Server erzeugt werden, auf dem der Sensor installiert ist. Das heißt, nehmen Sie die Anzahl der Ereignisdaten von einem beliebigen Spitzentag im letzten Jahr und multiplizieren Sie sie mit zehn.

Diese Empfehlung setzt Folgendes voraus:

* Das Informationstechnologie-Team Ihres Unternehmens überwacht jeden Sensor in der in diesem Handbuch beschriebenen Weise und führt dies mindestens einmal täglich durch. Sollte dies nicht der Fall sein, sollte diese Frist entsprechend verlängert werden.
* Das Informationstechnologie-Team Ihres Unternehmens kann innerhalb von 72 Stunden die Netzwerkfreigabe wiederherstellen oder installierte Insight Server ersetzen oder reparieren. Sollte dies nicht der Fall sein, sollte diese Frist entsprechend verlängert werden.
* Die Konfiguration des Sensors bleibt gleich.
* Keine externen Ereignisse (z. B. eine große Marketing-Kampagne) führen dazu, dass die Anzahl der von den Webservern generierten Ereignisdaten erheblich zunimmt.

Ihre Auswahl der Warteschlangengröße hängt weitgehend von der gewünschten Systemüberwachung im Hinblick auf die Vorgehensweisen und Richtlinien Ihres Unternehmens bezüglich der Antwortzeiten und der Verwaltung des Wochenende-/Feiertagssystems ab. Da größere Warteschlangengrößen besser sind, empfiehlt Adobe, dass Ihr Unternehmen die Warteschlange so groß wie möglich macht.

>[!NOTE]
>
>Größere Dateigrößen für Warteschlangen wirken sich nicht auf die Leistung aus.

Weitere Empfehlungen zur Größe der Warteschlange erhalten Sie von Adobe Consulting Services.

## Datenübertragung {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

Der Transmitter ist ein unabhängiger Prozess (z. B. ein Daemon auf einem UNIX-basierten Computer oder ein Dienst auf einem Windows-Computer), der auf demselben Computer wie der Webserver ausgeführt wird.

Der Transmitter liest die Ereignisdaten aus der Festplattenwarteschlange, komprimiert sie und sendet sie über HTTP/S an den von Ihnen angegebenen Insight Server, wo sie verarbeitet und in gespeichert werden. **.vsl** Dateien.
