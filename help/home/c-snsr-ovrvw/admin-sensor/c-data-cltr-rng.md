---
description: Überprüfen Sie, ob der Sammler mit verschiedenen Methoden ausgeführt wird.
title: Feststellen, dass die Datenerfassung funktioniert
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Feststellen, dass die Datenerfassung funktioniert{#confirming-that-the-data-collector-is-running}

{{eol}}

Überprüfen Sie, ob der Sammler mit verschiedenen Methoden ausgeführt wird.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Verwenden Sie die Site-Test-Funktion im Transmitter.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Überprüfen Sie, ob [!DNL Sensor] setzt ein Cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Verwenden von Site-Tests {#section-a5a697c3252e40f184c0b662926170f2}

Eine Möglichkeit, zu überprüfen, ob der Kollektor ausgeführt wird, besteht darin, die Site-Test -Funktion im Transmitter zu aktivieren. Wenn Sie Site-Test aktivieren, sendet der Transmitter regelmäßig (alle 60 Sekunden) eine GET-Anfrage an den Webserver, auf dem der Collector ausgeführt wird. Wenn Site Test keine Antwort vom Webserver erhält, schreibt er eine Fehlermeldung in syslog und sendet eine Fehlermeldung an die [!DNL data workbench server] (wird in die Sensorprotokolldatei geschrieben).

Wenn Site Test eine Antwort vom Webserver erhält, sucht er in der Warteschlangendatei nach einem Paket vom Webserver. Wenn das Paket nicht angezeigt wird (was darauf hinweist, dass der Kollektor das Ereignis nicht erfasst hat), schreibt Site Test eine Fehlermeldung in syslog und sendet eine Fehlermeldung an Adobe (die auch in die Sensorprotokolldatei geschrieben ist).

In den Anforderungen, die Site Test an den Webserver sendet, setzt Site Test den Wert User-Agent auf &quot; [!DNL Sensor] Test.&quot; Wenn diese Anforderungen nicht in Ihrem Datensatz angezeigt werden sollen, fügen Sie die [!DNL Sensor] Test&quot; User-Agent für die [!DNL Baseline Robots List.txt] oder [!DNL Extended Robots List.txt] in der Datei [!DNL Lookups] Ordner auf [!DNL data workbench server].

**Aktivieren von Site-Tests im Transmitter**

1. Suchen Sie die [!DNL txlogd.conf] Datei auf dem Computer, auf dem [!DNL Sensor] wird ausgeführt und in einem Texteditor geöffnet.

1. Im [!DNL txlogd.conf] -Datei, suchen Sie die Zeile &quot;SiteTest&quot; und konfigurieren Sie sie wie unten dargestellt. Wenn [!DNL txlogd.conf] -Datei enthält nicht die Zeile &quot;SiteTest&quot;, fügen Sie einfach die Zeile am Ende der Konfigurationsdatei hinzu.

   SiteTest http, *serverAddress*, *port*, *resource*

   where *serverAddress* der Name oder die IP-Adresse des Webservers, *port* der HTTP-Listening-Anschluss des Servers ist und *resource* ist die spezifische Ressource, die Site-Test beim Testen des Servers anfordern soll. Beachten Sie Folgendes: *resource* kann eine Abfragezeichenfolge enthalten.

   Beispiel: SiteTest http,localhost,80,/index.jsp

   Um mehrere Webserver zu testen, geben Sie einfach mehrere SiteTest-Zeilen an.

## Suchen nach einem Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Eine andere Möglichkeit, zu überprüfen, ob der Wächter auf einem Webserver ausgeführt wird, besteht darin, zu überprüfen, ob [!DNL Sensor] setzt ein Cookie in den Antworten, die der Webserver an Clients zurückgibt. Wenn der Wächter funktioniert, gibt der Webserver ein &quot;v1st&quot;-Cookie zurück.

Sie können das Cookie umbenennen. Wenn Sie dies getan haben, müssen Sie nach dem angegebenen Namen suchen, nicht nach v1st.

Sie können diese Prüfung mit einem automatisierten Skript oder Überwachungsagenten durchführen. Für ein Beispielskript oder zusätzliche Hilfe zu dieser Aufgabe wenden Sie sich bitte an Adobe Consulting Services.
