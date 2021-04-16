---
description: Überprüfen Sie, ob der Collector mit verschiedenen Methoden ausgeführt wird.
title: Feststellen, dass die Datenerfassung funktioniert
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Feststellen, dass die Datenerfassung funktioniert{#confirming-that-the-data-collector-is-running}

Überprüfen Sie, ob der Collector mit verschiedenen Methoden ausgeführt wird.

**Empfohlene Häufigkeit:** alle 5-10 Minuten

* [Verwenden Sie die Site-Testfunktion im Transmitter.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Überprüfen Sie,  [!DNL Sensor] ob ein Cookie gesetzt wird.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Verwenden des Site-Tests {#section-a5a697c3252e40f184c0b662926170f2}

Eine Möglichkeit, zu überprüfen, ob der Collector ausgeführt wird, ist die Aktivierung der Site-Test-Funktion im Transmitter. Wenn Sie Site-Test aktivieren, sendet der Sender regelmäßig (alle 60 Sekunden) eine GET an den Webserver, auf dem der Collector ausgeführt wird. Wenn der Site-Test keine Antwort vom Webserver erhält, schreibt er eine Fehlermeldung an syslog und sendet eine Fehlermeldung an das [!DNL data workbench server] (das in die Sensor-Protokolldatei geschrieben wird).

Wenn Site-Test eine Antwort vom Webserver erhält, sucht er in der Warteschlangendatei nach einem Paket vom Webserver. Wenn das Paket nicht angezeigt wird (was anzeigt, dass der Collector nicht ausgeführt wurde, um das Ereignis zu erfassen), schreibt Site Test eine Fehlermeldung an syslog und sendet eine Fehlermeldung an die Adobe (die auch in die Sensorprotokolldatei geschrieben wird).

In den Anforderungen, die Site-Test an den Webserver sendet, setzt Site-Test den Wert User-Agent auf &quot;[!DNL Sensor] Test&quot;. Wenn diese Anforderungen nicht in Ihrem Datensatz angezeigt werden sollen, fügen Sie den User-Agent &quot;[!DNL Sensor] Test&quot;der Datei &quot;[!DNL Baseline Robots List.txt]&quot;oder der Datei &quot;[!DNL Extended Robots List.txt]&quot;im Ordner &quot;[!DNL Lookups]&quot;unter &quot;[!DNL data workbench server]&quot;hinzu.

**So aktivieren Sie den Site-Test im Transmitter**

1. Suchen Sie die Datei [!DNL txlogd.conf] auf dem Computer, auf dem [!DNL Sensor] ausgeführt wird, und öffnen Sie sie in einem Texteditor.

1. Suchen Sie in der Datei [!DNL txlogd.conf] die Zeile &quot;SiteTest&quot;und konfigurieren Sie sie wie unten dargestellt. Wenn Ihre [!DNL txlogd.conf]-Datei nicht die Zeile &quot;SiteTest&quot;enthält, fügen Sie einfach die Zeile zum Ende der Konfigurationsdatei hinzu.

   SiteTest http, *serverAddress*, *port*, *resource*

   wobei *serverAddress* der Name oder die IP-Adresse des Webservers, *port* der HTTP-Listening-Anschluss des Servers und *resource* die spezifische Ressource ist, die Sie beim Testen des Servers von Site-Test anfordern möchten. Beachten Sie, dass *resource* eine Abfrage-Zeichenfolge enthalten kann.

   Beispiel: SiteTest http,localhost,80,/index.jsp

   Um mehrere Webserver zu testen, geben Sie einfach mehrere SiteTest-Zeilen an.

## Suchen nach einem Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Eine andere Möglichkeit, zu überprüfen, ob der Collector auf einem Webserver ausgeführt wird, besteht darin, zu überprüfen, ob [!DNL Sensor] ein Cookie in den Antworten setzt, die der Webserver an Clients zurückgibt. Wenn der Collector funktioniert, gibt der Webserver ein &quot;v1st&quot;-Cookie zurück.

Es ist möglich, das Cookie umzubenennen. Ist dies der Fall, müssen Sie nach dem angegebenen Namen suchen, nicht nach v1st.

Sie können diese Prüfung mit einem automatisierten Skript oder einem Überwachungsagenten durchführen. Für ein Beispielskript oder zusätzliche Hilfe zu dieser Aufgabe wenden Sie sich bitte an Adobe Consulting Services.
