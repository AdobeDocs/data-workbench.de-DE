---
description: Informationen zu den Startbefehlen für Sensor-Transmitter für UNIX und Windows.
title: Befehlszeilenoptionen für Sensor-Transmitter
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---

# Befehlszeilenoptionen für Sensor-Transmitter{#sensor-transmitter-command-line-options}

{{eol}}

Informationen zu den Startbefehlen für Sensor-Transmitter für UNIX und Windows.

## Startbefehl für UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Um den Sensor Transmitter auf einem UNIX-Stamm zu starten, verwenden Sie den folgenden Befehl:

```
txlogd -f configFileName
```

wobei configFileName der vollständig qualifizierte Name der Konfigurationsdatei des Senders (txlogd.conf) ist.

Standardmäßig wird der Transmitter als Hintergrundprozess (Daemon) ausgeführt und schreibt Betriebsmeldungen in syslog.

Im Folgenden finden Sie eine vollständige Liste der Befehlszeilenschalter für txlogd:

| Switch | Beschreibung |
|---|---|
| -f | Gibt den vollständig qualifizierten Namen der Konfigurationsdatei an (txlogd.conf). Wenn Sie diesen Switch nicht angeben, sucht der Transmitter im aktuellen Verzeichnis nach txlogd.conf. |
| -n | Startet den Transmitter im interaktiven Modus (nicht als Hintergrundprozess). |
| -i | Startet den Transmitter im interaktiven Modus und weist die Debug-Ausgabe an &quot;stdout&quot;. |
| -d | Startet den Transmitter als Hintergrundprozess und leitet die Debug-Ausgabe an txlogd-debug.log im aktuellen Verzeichnis weiter. |
| -c | Startet den Transmitter und erstellt die Datei mit der Datenträgerwarteschlange, falls sie nicht vorhanden ist. Wenn die Festplattenwarteschlange bereits vorhanden ist, wird dieser Parameter ignoriert. |
| -x | Startet den Transmitter und beendet ihn, nachdem er das letzte Paket in der Warteschlange der Festplatte übermittelt hat. Sie können diese Option verwenden, um die Warteschlange zur Vorbereitung eines Verwaltungsvorgangs, z. B. zum Erstellen einer neuen Warteschlangendatei, abzuleiten. |

## Startbefehl für Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Um Sensor zu starten und als Dienst auf einem Windows-System zu registrieren, verwenden Sie den folgenden Befehl:

```
txlog /regserver
```
