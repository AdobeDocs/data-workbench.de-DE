---
description: Informationen zur Lösung von Webserver-Problemen, z. B. wenn der Webserver nicht mehr rotiert wird oder der Webserver fehlschlägt.
title: Erläuterungen zu Ursachen
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Erläuterungen zu Ursachen{#understanding-the-causes}

{{eol}}

Informationen zur Lösung von Webserver-Problemen, z. B. wenn der Webserver nicht mehr rotiert wird oder der Webserver fehlschlägt.

## Wenn ein Webserver aus der Rotation ausgeschlossen wird {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Wenn ein Webserver aus der Rotation eines Serverpools herausgenommen wird, aber anderweitig mit dem Sender verbunden ist, der periodische Heartbeats sendet, wird die Ausführungszeit auf dem neuesten Stand gehalten und es ist kein Eingriff von irgendjemandem erforderlich.

## Wenn ein Webserver fehlschlägt {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Wenn ein Webserver aufgrund eines katastrophalen Fehlers vollständig offline ist oder keine Daten oder Heartbeats sendet, wird die Ausführungsdauer auf der Seite [!DNL data workbench server] stoppt, um sicherzustellen, dass es das letzte Mal darstellt, dass [!DNL data workbench server] Daten von ALLEN Datenquellen erhalten hat, von denen sie Kenntnis hat. Das System selbst verarbeitet weiterhin Daten, die noch in der Data Workbench analysiert werden können, aber alles andere in der [!DNL data workbench server] , die auf der Ausführungsdauer basiert, funktioniert nicht. Beispielsweise werden die Ausführungszeitenberichte und verwendet, um viele abgeleitete Trigger im System zu erstellen. Wenn die Ausführungsdauer angehalten wurde, wird kein Reporting ausgelöst und diese bestimmten abgeleiteten Dimensionen sind nicht verfügbar.

Wenn beispielsweise WEB2 am 15. Juni offline ging und fünf Tage lang keine Daten gesendet hat, wäre der Ausführungszeitpunkt irgendwann am 15. Juni. Die Dimension von Gestern wäre beispielsweise der 14. Juni, obwohl das heutige Datum der 20. Juni ist.
