---
description: Dieser Abschnitt enthält eine kurze Anleitung, in der Sie die Mindestanforderungen für die Einrichtung und Planung von Skripten zur wöchentlichen Verarbeitung Ihrer Protokolldateien festlegen können. Dies kann als Referenzhandbuch zum Einrichten oder Ändern Ihrer Profile verwendet werden.
title: Skripten zur wöchentlichen Neuverarbeitung
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skripten zur wöchentlichen Neuverarbeitung{#scripting-to-weekly-reprocess}

Dieser Abschnitt enthält eine kurze Anleitung, in der Sie die Mindestanforderungen für die Einrichtung und Planung von Skripten zur wöchentlichen Verarbeitung Ihrer Protokolldateien festlegen können. Dies kann als Referenzhandbuch zum Einrichten oder Ändern Ihrer Profile verwendet werden.

## Neuverarbeitung {#section-7e335aacc199488592e78a835e2649fe}

Laden der Daten in DWB basierend auf Änderungen in Datenquellen, Offline-Datenquellen oder dem Zeitraum. Das Skript verarbeitet den Parameter für das Startdatum in der Datei *Log Processing.cfg* neu.

## Voraussetzungen {#section-804acce5df4942469c9313535627038a}

Report Suite-ID, Anzahl der Monatsdaten sollte in DWB verfügbar sein. Der Ordner Perl64 sollte in Ihrem C:\ drive verfügbar sein.

## Protokolle neu verarbeiten {#section-565d3e1f0df14127a97d9beecd14f02f}

Geben Sie die oben genannten Details (Voraussetzungen) in Windows Befehl Skript *Reprocess.bat* verfügbar unter Ordner *\scripts\Log Processing* auf dem Main FSU-Server.

Dieses Skript ruft intern zwei clientspezifische Skripten auf: Eine zur erneuten Verarbeitung der Daten und eine andere zur E-Mail-Warnung. Diese beiden Skripten stehen auch im Ordner *\scripts\Log Processing* zur Verfügung.

Das Skript ändert die Parameter für die Neuverarbeitung in der Datei &quot; *Log Processing.cfg* &quot;.

## Rollierendes Fenster für Protokolle {#section-ed5f44d890b34523ab33da7aa0ae3990}

Geben Sie Details (Voraussetzungen) in Windows-Befehlsskript *zur Verarbeitung von date.bat* an, das im Ordner *\scripts\Scripository* auf dem maing FSU-Server verfügbar ist. Dieses Skript ruft intern zwei clientspezifische Skripten auf: Eine zur Einrichtung des Startdatums der Protokolle und eine andere für E-Mail-Warnungen. Diese beiden Skripten stehen auch in* \scripts\Scripository* zur Verfügung.

Geben Sie Report Suite-ID und Anzahl der Monate in der Datei* logprocessing.bat* an.

Das Skript ändert den Parameter für das Startdatum in *Log Processing.cfg*.

>[!NOTE]
>
>Wenn der Ordner &quot; *Scrirepository* &quot;nicht verfügbar ist, führen Sie den folgenden Vorgang aus, um den Ordner &quot; *Scrirepository* &quot;zu kopieren und in den oben genannten Dateien unter Verwendung kundenspezifischer Details Änderungen vorzunehmen. Geben Sie Ihre E-Mail-Adresse ein, um im Falle eines Fehlers eine Warnung zu erhalten.

## Skripten planen {#section-063cf0c755dc47d28d60947d8d43d0e9}

Führen Sie die folgenden Schritte aus, um die Skripte im Windows Task Scheduler zu planen.

1. Planen Sie das Skript im Task Scheduler von Windows.

   * Taskplaner öffnen: Klicken Sie mit der rechten Maustaste auf die **Taskplaner-Bibliothek** und klicken Sie auf Aufgabe **erstellen**.

   * Geben Sie auf der Registerkarte **Allgemein** einen Aufgabennamen ein und wählen Sie **Optionen**.

   * Klicken Sie unter der Registerkarte **Auslöser** auf **Neu** , und ein neues Fenster wird geöffnet.

   * Klicken Sie unter der Registerkarte **Aktionen** auf **Neu** , und ein neues Fenster wird geöffnet. Geben Sie dann Skriptdetails und andere Optionen ein. (Start in enthält einen Pfad, in dem das Skript platziert wird).

1. Validierung: Klicken Sie mit der rechten Maustaste und führen Sie den Auftrag aus und überprüfen Sie die Änderungen in der Datei *Log processing.cfg* . An die im Skript angegebene E-Mail-ID wird eine E-Mail gesendet.

