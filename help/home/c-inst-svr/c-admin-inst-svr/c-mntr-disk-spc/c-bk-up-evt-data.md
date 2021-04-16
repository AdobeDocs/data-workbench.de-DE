---
description: Ereignis-Daten müssen täglich mit den normalen Backup- und Disaster Recovery-Verfahren Ihrer Firma gesichert werden.
title: Sichern von Ereignisdaten
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# Sichern von Ereignisdaten{#backing-up-event-data}

Ereignis-Daten müssen täglich mit den normalen Backup- und Disaster Recovery-Verfahren Ihrer Firma gesichert werden.

**Empfohlene Häufigkeit:** Täglich

[!DNL Insight Server] beginnt täglich um 12:00 Uhr GMT neue Protokolldateien. Adobe empfiehlt, dass Sie Protokolldateien jeden Tag kurz nach 12:00 Uhr GMT sichern, damit Sie alle Daten des Vortages erfassen können. Wenn Sie beispielsweise am 15. Dezember um 12:05 Uhr GMT alle Protokolldateien sichern, werden alle Daten vom 14. Dezember erfasst. [!DNL Insight Server] muss während der Sicherung der Protokolldatei nicht gestoppt werden, und alle Funktionen bleiben verfügbar.

## Integration, Betriebssystem, Ausgabe und Systemdaten sichern {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Empfohlene Häufigkeit:** Täglich

Integration-, Betriebssystem-, Ausgabe- und Systemdaten müssen regelmäßig und sorgfältig mit den normalen Backup- und Disaster Recovery-Systemen Ihrer Firma gesichert werden.
