---
description: 'Sensor besteht aus drei Hauptkomponenten: Datenerfassung, Disk Queue und Data Transmitter.'
title: Grundlegende Komponenten
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Grundlegende Komponenten{#what-are-basic-components}

Sensor besteht aus drei Hauptkomponenten: Datenerfassung, Disk Queue und Data Transmitter.

![](assets/Visual-Sensor.png)

## Datenerfassung {#section-f970eaff30364a3c8106d5ec9c1b5caa}

Der Datenerfasser (Collector) ist ein NSAPI-, ISAPI-, J2EE-Filter-Servlet oder Apache-Modul, das im Webserverprozess ausgeführt wird.

Er erfasst die unverarbeiteten Ereignisdaten zu jeder HTTP-Anforderung, die der Webserver verarbeitet und in die Datenträgerwarteschlange einlegt. Wenn Sie mehrere Instanzen eines Webservers auf demselben Computer ausführen, lädt jede Instanz ihre eigene Instanz des Sammlermoduls. Allerdings schreiben alle Instanzen des Sammlers ihre Ereignisdaten in dieselbe Datenträgerwarteschlange.

## Festplattenwarteschlange {#section-41aac77ab30e48478d1b31eac288df05}

Die Disk Queue (Queue) ist eine fehlertolerante, FIFO-Datei (first in, first out) mit Speicherzuordnung, die die von Sensor erfassten unverarbeiteten Ereignisdaten speichert und temporären Speicher für gesammelte Ereignisdaten auf dem Webserver bereitstellt, auf dem sie installiert ist.

Um zu verhindern, dass die Warteschlange ohne Einschränkung erweitert wird (und damit den gesamten verfügbaren Speicherplatz belegt), wird die Warteschlange in einer Datei mit fester Größe beibehalten, d. h. sie enthält nur so viele Ereignisdaten wie sie über die Kapazität verfügen. Die Größe der Warteschlangendatei wird im Parameter QueueSize der Sensor-Konfigurationsdatei txlogd.conf konfiguriert, wenn der Sensor installiert ist. Informationen zu den Parametern txlogd.conf finden Sie unter Sensor Txlogd.conf-Dateiparameter.

Sobald die physische Länge der Datei festgelegt ist, wird sie nicht größer oder kleiner. Der Collector legt einfach neue Ereignisdaten in die Warteschlange und der Transmitter ruft Ereignisse daraus ab. Wenn der Collector das Dateiende erreicht, wird das Schreiben in die Warteschlangendatei beendet.

Im Allgemeinen ruft der Transmitter Ereignisse so schnell aus der Warteschlange ab, wie der Collector sie ablagert. Wenn die Verbindung zwischen dem Transmitter und dem Insight-Server langsam oder nicht verfügbar ist, kann die Warteschlange mit nicht übertragenen Ereignissen gefüllt werden. In diesem Fall stoppt der Collector die Datenerfassung, bis der Transmitter die Warteschlange herunterzieht. Informationen zu Anforderungen, die der Webserver während dieser Zeit verarbeitet, gehen dauerhaft verloren.

**Bestimmen der Warteschlangengröße**

Bevor Sie Sensor installieren, müssen Sie festlegen, wie groß die Warteschlange sein muss. Um einen dauerhaften Datenverlust zu vermeiden, ist es wichtig, eine Warteschlange zu erstellen, die groß genug ist, um die Anzahl der Ereignisse zu berücksichtigen, die während des wahrscheinlichsten längeren Ausfalls der Verbindung mit dem Insight-Server akkumuliert werden könnten (d. h. genügend Speicher für mehrere Tage der Spitzenaktivität). Die Warteschlange muss so konfiguriert sein, dass genügend Ereignisdaten gespeichert werden, damit Systemadministratoren Zeit haben, die Netzwerkzugriffsrechte auf den Insight-Server wiederherzustellen oder den Insight-Server zu reparieren oder zu ersetzen, ohne Daten zu verlieren. Wenn der Sensor fehlgeschlagen ist und keine gültige und zugängliche Warteschlangendatei zur Speicherung der Ereignisdaten verfügbar ist, gehen nachfolgende Daten verloren.

>[!NOTE]
>
>Es ist wichtig, dass die Administratoren der einzelnen Computer, auf denen Sensor ausgeführt wird, die Besonderheit der lokalen Warteschlangendatei verstehen, um sicherzustellen, dass sie diese nicht als normale Protokolldatei behandeln, die gelöscht, archiviert oder komprimiert werden kann.

Adobe empfiehlt, dass die Warteschlange so konfiguriert wird, dass sie mindestens zehn (10) Spitzenereignisdaten enthält, die vom Server erzeugt werden, auf dem der Sensor installiert ist. Das heißt, nehmen Sie die Anzahl der Ereignisdaten von einem beliebigen Spitzentag im letzten Jahr und multiplizieren Sie sie mit zehn.

Diese Empfehlung setzt Folgendes voraus:

* Das Informationstechnologie-Team Ihres Unternehmens überwacht jeden Sensor in der in diesem Leitfaden beschriebenen Art und Weise und tut dies mindestens einmal täglich. Sollte dies nicht der Fall sein, sollte diese Frist angemessen verlängert werden.
* Das Informationstechnologie-Team Ihres Unternehmens ist in der Lage, innerhalb von 72 Stunden Netzwerkzugriff wiederherzustellen oder installierte Insight-Server zu ersetzen oder zu reparieren. Sollte dies nicht der Fall sein, sollte diese Frist angemessen verlängert werden.
* Die Konfiguration des Sensors bleibt gleich.
* Keine externen Ereignisse (z. B. eine große Marketingkampagne) führen dazu, dass die Anzahl der von den Webservern generierten Ereignisdaten erheblich zunimmt.

Ihre Wahl der Warteschlangengröße hängt weitgehend von der gewünschten Systemüberwachung im Hinblick auf die Vorgehensweisen und Richtlinien Ihres Unternehmens in Bezug auf die Antwortzeiten und die Verwaltung des Wochenende-/Feiertagssystems ab. Da größere Warteschlangengrößen besser sind, empfiehlt Adobe, dass Ihr Unternehmen die Warteschlange so groß wie möglich macht.

>[!NOTE]
>
>Größere Warteschlangendateigrößen haben keine Auswirkungen auf die Leistung.

Weitere Empfehlungen zur Größe der Warteschlange erhalten Sie von Adobe Consulting Services.

## Datenübermittler {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

Der Transmitter ist ein unabhängiger Prozess (z. B. ein Daemon auf einem UNIX-basierten Computer oder ein Dienst auf einem Windows-Computer), der auf demselben Computer wie der Webserver ausgeführt wird.

Der Transmitter liest die Ereignisdaten aus der Disk-Warteschlange, komprimiert sie und sendet sie per HTTP/S an den von Ihnen angegebenen Insight Server, wo sie in **.vsl** -Dateien verarbeitet und gespeichert werden.
