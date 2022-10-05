---
description: Ereignisdaten müssen täglich mithilfe der normalen Backup-Systeme und Notfallwiederherstellungsverfahren Ihres Unternehmens gesichert werden.
title: Sichern von Ereignisdaten
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# Sichern von Ereignisdaten{#backing-up-event-data}

{{eol}}

Ereignisdaten müssen täglich mithilfe der normalen Backup-Systeme und Notfallwiederherstellungsverfahren Ihres Unternehmens gesichert werden.

**Empfohlene Häufigkeit:** Täglich

[!DNL Insight Server] beginnt täglich um 12:00 Uhr GMT neue Protokolldateien. Adobe empfiehlt, Protokolldateien täglich kurz nach 12:00 Uhr GMT zu sichern, damit Sie alle Daten des Vortags erfassen können. Wenn Sie beispielsweise am 15. Dezember um 12:05 Uhr GMT alle Protokolldateien sichern, werden alle Daten vom 14. Dezember erfasst. [!DNL Insight Server] muss nicht während der Sicherung der Protokolldateien angehalten werden und alle Funktionen bleiben verfügbar.

## Sichern von Integration, Betriebssystem, Ausgabe und Systemdaten {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Empfohlene Häufigkeit:** Täglich

Integration, Betriebssystem, Ausgabe und Systemdaten müssen regelmäßig und sorgfältig mithilfe der normalen Sicherungs- und Notfallwiederherstellungssysteme Ihres Unternehmens gesichert werden.
