---
description: Überprüfen Sie, ob der Sammler mit verschiedenen Methoden ausgeführt wird.
title: Feststellen, dass die Datenerfassung funktioniert
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Feststellen, dass die Datenerfassung funktioniert{#confirming-that-the-data-collector-is-running}

Überprüfen Sie, ob der Sammler mit verschiedenen Methoden ausgeführt wird.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Verwenden Sie die Site-Test-Funktion im Transmitter.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Überprüfen Sie, ob [!DNL Sensor] ein Cookie setzt.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Verwenden von Site-Test {#section-a5a697c3252e40f184c0b662926170f2}

Eine Möglichkeit, zu überprüfen, ob der Kollektor ausgeführt wird, besteht darin, die Site-Test -Funktion im Transmitter zu aktivieren. Wenn Sie Site-Test aktivieren, sendet der Transmitter regelmäßig (alle 60 Sekunden) eine GET-Anfrage an den Webserver, auf dem der Collector ausgeführt wird. Wenn Site Test keine Antwort vom Webserver erhält, schreibt er eine Fehlermeldung in syslog und sendet eine Fehlermeldung an [!DNL data workbench server] (die in die Sensorprotokolldatei geschrieben ist).

Wenn Site Test eine Antwort vom Webserver erhält, sucht er in der Warteschlangendatei nach einem Paket vom Webserver. Wenn das Paket nicht angezeigt wird (was darauf hinweist, dass der Kollektor das Ereignis nicht erfasst hat), schreibt Site Test eine Fehlermeldung in syslog und sendet eine Fehlermeldung an Adobe (die auch in die Sensorprotokolldatei geschrieben ist).

In den Anforderungen, die Site Test an den Webserver sendet, setzt Site Test den Benutzeragenten-Wert auf &quot;[!DNL Sensor] Test&quot;. Wenn diese Anfragen nicht in Ihrem Datensatz angezeigt werden sollen, fügen Sie den Benutzeragenten &quot;[!DNL Sensor] Test&quot;zur Datei [!DNL Baseline Robots List.txt] oder die Datei [!DNL Extended Robots List.txt] im Ordner [!DNL Lookups] im Ordner [!DNL data workbench server] hinzu.

**Aktivieren von Site-Tests im Transmitter**

1. Suchen Sie die Datei [!DNL txlogd.conf] auf dem Computer, auf dem [!DNL Sensor] ausgeführt wird, und öffnen Sie sie in einem Texteditor.

1. Suchen Sie in der Datei [!DNL txlogd.conf] die Zeile &quot;SiteTest&quot;und konfigurieren Sie sie wie unten dargestellt. Wenn Ihre [!DNL txlogd.conf]-Datei nicht die Zeile &quot;SiteTest&quot;enthält, fügen Sie einfach die Zeile am Ende der Konfigurationsdatei hinzu.

   SiteTest http, *serverAddress*, *port*, *resource*

   wobei *serverAddress* der Name oder die IP-Adresse des Webservers, *port* der HTTP-Listening-Anschluss des Servers und *resource* die spezifische Ressource ist, die Site-Test beim Testen des Servers anfordern soll. Beachten Sie, dass *resource* eine Abfragezeichenfolge enthalten kann.

   Beispiel: SiteTest http,localhost,80,/index.jsp

   Um mehrere Webserver zu testen, geben Sie einfach mehrere SiteTest-Zeilen an.

## Suchen nach einem Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Eine andere Möglichkeit, zu überprüfen, ob der Wächter auf einem Webserver ausgeführt wird, besteht darin, zu überprüfen, ob [!DNL Sensor] ein Cookie in den Antworten setzt, die der Webserver an Clients zurückgibt. Wenn der Wächter funktioniert, gibt der Webserver ein &quot;v1st&quot;-Cookie zurück.

Sie können das Cookie umbenennen. Wenn Sie dies getan haben, müssen Sie nach dem angegebenen Namen suchen, nicht nach v1st.

Sie können diese Prüfung mit einem automatisierten Skript oder Überwachungsagenten durchführen. Für ein Beispielskript oder zusätzliche Hilfe zu dieser Aufgabe wenden Sie sich bitte an Adobe Consulting Services.
