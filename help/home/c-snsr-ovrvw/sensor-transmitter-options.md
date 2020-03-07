---
description: Informationen zu Sensor Transmitter-Startbefehlen für UNIX und Windows.
title: Sensor Transmitter-Befehlszeilenoptionen
uuid: 8d077d76-a709-494e-a176-07ca3e761662
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sensor Transmitter-Befehlszeilenoptionen{#sensor-transmitter-command-line-options}

Informationen zu Sensor Transmitter-Startbefehlen für UNIX und Windows.

## Startbefehl für UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Um den Sensor-Transmitter an einem UNIX-Stamm zu starten, verwenden Sie den folgenden Befehl:

```
txlogd -f configFileName
```

wobei configFileName der vollständig qualifizierte Name der Transmitter-Konfigurationsdatei (txlogd.conf) ist.

Standardmäßig wird der Transmitter als Hintergrundprozess (ein Daemon) ausgeführt und in syslog Betriebsmeldungen geschrieben.

Im Folgenden finden Sie eine vollständige Liste der Befehlszeilenschalter für txlogd:

| Switch | Beschreibung |
|---|---|
| -f | Gibt den vollständig qualifizierten Namen der Konfigurationsdatei (txlogd.conf) an. Wenn Sie diesen Switch nicht angeben, sucht der Sender im aktuellen Verzeichnis nach txlogd.conf. |
| -n | Startet den Transmitter im interaktiven Modus (nicht als Hintergrundprozess). |
| -i | Startet den Transmitter im interaktiven Modus und leitet die Debug-Ausgabe an stdout weiter. |
| -d | Startet den Transmitter als Hintergrundprozess und leitet die Debug-Ausgabe an txlogd-debug.log im aktuellen Ordner weiter. |
| -c | Startet den Transmitter und erstellt die Disk Queue-Datei, falls sie nicht vorhanden ist. Wenn die Datenträgerwarteschlange bereits vorhanden ist, wird dieser Parameter ignoriert. |
| -x | Startet den Transmitter und beendet ihn, nachdem er das letzte Paket in der Disk-Warteschlange überträgt. Sie können diese Option verwenden, um die Warteschlange in Vorbereitung auf einen Verwaltungsvorgang, z. B. zum Erstellen einer neuen Warteschlangendatei, abzuleiten. |

## Startbefehl für Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Um Sensor zu starten und als Dienst auf einem Windows-System zu registrieren, verwenden Sie den folgenden Befehl:

```
txlog /regserver
```

