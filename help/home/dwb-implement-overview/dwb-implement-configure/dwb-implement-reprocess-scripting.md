---
description: In diesem Abschnitt erhalten Sie eine kurze Anleitung, in der Sie die erforderlichen Mindestschritte zum Einrichten und Planen von Skripten zur wöchentlichen Neuverarbeitung Ihrer Protokolldateien finden. Dies kann als Referenzhandbuch zum Einrichten oder Ändern von Profilen verwendet werden.
title: Skripterstellung zur erneuten Verarbeitung im Wochenturnus
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Skripterstellung zur erneuten Verarbeitung im Wochenturnus{#scripting-to-weekly-reprocess}

{{eol}}

In diesem Abschnitt erhalten Sie eine kurze Anleitung, in der Sie die erforderlichen Mindestschritte zum Einrichten und Planen von Skripten zur wöchentlichen Neuverarbeitung Ihrer Protokolldateien finden. Dies kann als Referenzhandbuch zum Einrichten oder Ändern von Profilen verwendet werden.

## Neuverarbeitung {#section-7e335aacc199488592e78a835e2649fe}

Laden der Daten in DWB basierend auf Änderungen in Datenquellen, Offline-Datenquellen oder dem Zeitraum. Das Skript verarbeitet den Startdatumsparameter in *Log Processing.cfg* -Datei.

## Voraussetzungen {#section-804acce5df4942469c9313535627038a}

Report Suite-ID, Anzahl der Monatsdaten sollte in DWB verfügbar sein. Der Ordner Perl64 sollte in Ihrem Ordner C:\ drive verfügbar sein.

## Protokolle erneut verarbeiten {#section-565d3e1f0df14127a97d9beecd14f02f}

Geben Sie die oben genannten Details (Voraussetzungen) in Windows-Befehlsskript an *Reprocess.bat* verfügbar unter Ordner *\scripts\Log Processing* auf dem Haupt-FSU-Server.

Dieses Skript ruft intern zwei clientspezifische Skripte auf: Eine zur erneuten Verarbeitung der Daten und eine andere zur E-Mail-Warnung. Diese beiden Skripte sind auch im *\scripts\Log Processing* Ordner.

Das Skript ändert die Neuverarbeitungsparameter im *Log Processing.cfg* -Datei.

## Rollierendes Fenster für Protokolle {#section-ed5f44d890b34523ab33da7aa0ae3990}

Details (Voraussetzungen) in Windows-Befehlsskript angeben *logprocessingdate.bat* verfügbar unter Ordner *\scripts\Scripository* auf dem Maing-FSU-Server. Dieses Skript ruft intern zwei clientspezifische Skripte auf: Ein Schritt zur Einrichtung des Startdatums für Protokolle und ein anderer für E-Mail-Warnungen. Diese beiden Skripte sind auch in &quot;* \scripts\Scripository*&quot;verfügbar.

Geben Sie die Report Suite-ID und die Anzahl der Monate in der Datei &quot;logprocessingDate.bat&quot;an.

Das Skript ändert den Startdatumsparameter in *Log Processing.cfg*.

>[!NOTE]
>
>Wenn die Variable *Scripting* nicht verfügbar ist, führen Sie den folgenden Prozess aus, um den *Scripting* und nehmen Sie Änderungen in den oben genannten Dateien mit kundenspezifischen Details vor. Geben Sie Ihre E-Mail-Adresse an, um im Falle eines Fehlers einen Warnhinweis zu erhalten.

## Skripte planen {#section-063cf0c755dc47d28d60947d8d43d0e9}

Führen Sie diese Schritte aus, um die Skripte in der Windows-Aufgabenplanung zu planen.

1. Planen Sie das Skript in der Aufgabenplanung von Windows.

   * Task Scheduler öffnen: Klicken Sie mit der rechten Maustaste auf die **Aufgabenplanbibliothek** und klicken Sie auf **Aufgabe erstellen**.

   * Im **Allgemein** Registerkarte geben Sie einen Aufgabennamen an und wählen Sie **Optionen**.

   * Unter dem **Trigger** Registerkarte, klicken Sie auf **Neu** und ein neues Fenster öffnet sich.

   * Unter dem **Aktionen** Registerkarte, klicken Sie auf **Neu** und ein neues Fenster öffnet sich. Geben Sie dann Skriptdetails und andere Optionen an. (Start in hat einen Pfad, in dem Skript platziert wird).

1. Validierung: Klicken Sie mit der rechten Maustaste und führen Sie den Auftrag aus und überprüfen Sie die Änderungen im *Protokollverarbeitung.cfg* -Datei. An die im Script angegebene E-Mail-Adresse wird eine E-Mail gesendet.
