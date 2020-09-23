---
description: Überprüfen Sie, ob der Collector mit verschiedenen Methoden ausgeführt wird.
solution: Analytics
title: Feststellen, dass die Datenerfassung funktioniert
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---


# Feststellen, dass die Datenerfassung funktioniert{#confirming-that-the-data-collector-is-running}

Überprüfen Sie, ob der Collector mit verschiedenen Methoden ausgeführt wird.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Verwenden Sie die Site-Testfunktion im Transmitter.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Überprüfen Sie, [!DNL Sensor] ob ein Cookie gesetzt wird.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Verwenden des Site-Tests {#section-a5a697c3252e40f184c0b662926170f2}

Eine Möglichkeit, zu überprüfen, ob der Collector ausgeführt wird, ist die Aktivierung der Site-Test-Funktion im Transmitter. Wenn Sie Site-Test aktivieren, sendet der Sender regelmäßig (alle 60 Sekunden) eine GET an den Webserver, auf dem der Collector ausgeführt wird. Wenn der Site-Test keine Antwort vom Webserver erhält, schreibt er eine Fehlermeldung an syslog und sendet eine Fehlermeldung an die [!DNL data workbench server] (die in die Sensor-Protokolldatei geschrieben wird).

Wenn Site-Test eine Antwort vom Webserver erhält, sucht er in der Warteschlangendatei nach einem Paket vom Webserver. Wenn das Paket nicht angezeigt wird (was anzeigt, dass der Collector nicht ausgeführt wurde, um das Ereignis zu erfassen), schreibt Site Test eine Fehlermeldung an syslog und sendet eine Fehlermeldung an die Adobe (die auch in die Sensorprotokolldatei geschrieben wird).

In den Anforderungen, die Site-Test an den Webserver sendet, setzt Site-Test den Wert User-Agent auf &quot; [!DNL Sensor] Test&quot;. Wenn diese Anforderungen nicht in Ihrem Datensatz angezeigt werden sollen, fügen Sie den User-Agent &quot; [!DNL Sensor] Test&quot;der [!DNL Baseline Robots List.txt] Datei oder der [!DNL Extended Robots List.txt] Datei im [!DNL Lookups] Ordner auf der [!DNL data workbench server]Seite hinzu.

**So aktivieren Sie den Site-Test im Transmitter**

1. Suchen Sie die [!DNL txlogd.conf] Datei auf dem Computer, auf dem sie ausgeführt [!DNL Sensor] wird, und öffnen Sie sie in einem Texteditor.

1. Suchen Sie in der [!DNL txlogd.conf] Datei die Zeile &quot;SiteTest&quot; und konfigurieren Sie sie wie unten dargestellt. Wenn Ihre [!DNL txlogd.conf] Datei nicht die Zeile &quot;SiteTest&quot;enthält, fügen Sie einfach die Zeile zum Ende der Konfigurationsdatei hinzu.

   SiteTest http, *serverAddress*, *port*, *resource*

   wobei *serverAddress* der Name oder die IP-Adresse des Webservers, *port* der HTTP-Listening-Anschluss des Servers und *resource* die spezifische Ressource ist, die beim Testen des Servers von Site Test angefordert werden soll. Beachten Sie, dass die *Ressource* eine Abfrage-Zeichenfolge enthalten kann.

   Beispiel: SiteTest http,localhost,80,/index.jsp

   Um mehrere Webserver zu testen, geben Sie einfach mehrere SiteTest-Zeilen an.

## Suchen nach einem Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Eine andere Möglichkeit, zu überprüfen, ob der Collector auf einem Webserver ausgeführt wird, besteht darin, zu überprüfen, ob ein Cookie in den Antworten gesetzt [!DNL Sensor] wird, die der Webserver an Clients zurückgibt. Wenn der Collector funktioniert, gibt der Webserver ein &quot;v1st&quot;-Cookie zurück.

Es ist möglich, das Cookie umzubenennen. Ist dies der Fall, müssen Sie nach dem angegebenen Namen suchen, nicht nach v1st.

Sie können diese Prüfung mit einem automatisierten Skript oder einem Überwachungsagenten durchführen. Für ein Beispielskript oder zusätzliche Hilfe zu dieser Aufgabe wenden Sie sich bitte an Adobe Consulting Services.
