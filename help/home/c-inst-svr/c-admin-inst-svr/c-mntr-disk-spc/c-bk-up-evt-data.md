---
description: Ereignisdaten müssen täglich mit den normalen Backup- und Disaster Recovery-Verfahren Ihres Unternehmens gesichert werden.
solution: Insight
title: Sichern von Ereignisdaten
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sichern von Ereignisdaten{#backing-up-event-data}

Ereignisdaten müssen täglich mit den normalen Backup- und Disaster Recovery-Verfahren Ihres Unternehmens gesichert werden.

**Empfohlene Häufigkeit:** Täglich

[!DNL Insight Server] beginnt täglich um 12:00 Uhr GMT neue Protokolldateien. Adobe empfiehlt, dass Sie Protokolldateien jeden Tag kurz nach 12:00 Uhr GMT sichern, damit Sie alle Daten des Vortages erfassen können. Wenn Sie beispielsweise am 15. Dezember um 12:05 Uhr GMT alle Protokolldateien sichern, werden alle Daten vom 14. Dezember erfasst. [!DNL Insight Server] muss während der Sicherung der Protokolldatei nicht gestoppt werden, und alle Funktionen bleiben verfügbar.

## Sichern von Integration, Betriebssystem, Ausgabe und Systemdaten {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Empfohlene Häufigkeit:** Täglich

Integration, Betriebssystem, Ausgabe und Systemdaten müssen regelmäßig und sorgfältig mit den normalen Backup- und Disaster Recovery-Systemen Ihres Unternehmens gesichert werden.
