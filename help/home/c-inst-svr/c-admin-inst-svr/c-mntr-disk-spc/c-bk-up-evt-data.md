---
description: Ereignis-Daten müssen täglich mit den normalen Backup- und Disaster Recovery-Verfahren Ihrer Firma gesichert werden.
solution: Analytics
title: Sichern von Ereignisdaten
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---


# Sichern von Ereignisdaten{#backing-up-event-data}

Ereignis-Daten müssen täglich mit den normalen Backup- und Disaster Recovery-Verfahren Ihrer Firma gesichert werden.

**Empfohlene Häufigkeit:** Täglich

[!DNL Insight Server] beginnt täglich um 12:00 Uhr GMT neue Protokolldateien. Adobe empfiehlt, dass Sie Protokolldateien jeden Tag kurz nach 12:00 Uhr GMT sichern, damit Sie alle Daten des Vortages erfassen können. Wenn Sie beispielsweise am 15. Dezember um 12:05 Uhr GMT alle Protokolldateien sichern, werden alle Daten vom 14. Dezember erfasst. [!DNL Insight Server] muss während der Sicherung der Protokolldatei nicht gestoppt werden, und alle Funktionen bleiben verfügbar.

## Sichern von Integration, Betriebssystem, Ausgabe und Systemdaten {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Empfohlene Häufigkeit:** Täglich

Integration-, Betriebssystem-, Ausgabe- und Systemdaten müssen regelmäßig und sorgfältig mit den normalen Backup- und Disaster Recovery-Systemen Ihrer Firma gesichert werden.
