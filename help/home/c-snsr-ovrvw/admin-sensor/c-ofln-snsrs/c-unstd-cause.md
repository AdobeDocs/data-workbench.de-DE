---
description: Informationen zur Behebung von Webserverproblemen, z. B. wenn der Webserver nicht mehr gedreht werden kann oder der Webserver ausfällt.
title: Erläuterungen zu Ursachen
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Erläuterungen zu Ursachen{#understanding-the-causes}

Informationen zur Behebung von Webserverproblemen, z. B. wenn der Webserver nicht mehr gedreht werden kann oder der Webserver ausfällt.

## Wenn ein Webserver aus der Drehung genommen wird {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Wenn ein Webserver aus der Rotation eines Serverpools herausgenommen wird, aber ansonsten mit dem Sender verbunden ist, der periodische Heartbeats sendet, wird die Ausführungszeit beibehalten, und es ist kein Eingreifen von irgendjemandem erforderlich.

## Wenn ein Webserver ausfällt {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Wenn ein Webserver aufgrund eines katastrophalen Fehlers vollständig offline ist oder keine Daten oder Heartbeats sendet, stoppt die Ausführungszeit von [!DNL data workbench server], um sicherzustellen, dass das [!DNL data workbench server] das letzte Mal, wenn die  Daten von ALLEN Datenquellen erhalten, von denen er Kenntnis hat, angezeigt wird. Das System selbst verarbeitet weiterhin Daten, die in der Data Workbench noch für die Analyse verfügbar sind, aber alles, was in der [!DNL data workbench server] auf der Ausführungszeit basiert, funktioniert nicht. Beispielsweise wird der Trigger &quot;Ausführungszeit&quot;verwendet, um viele abgeleitete Dimensionen im System zu erstellen. Wenn die Ausführungszeit beendet ist, wird kein Berichte ausgelöst und diese bestimmten abgeleiteten Dimensionen sind nicht verfügbar.

Wenn beispielsweise WEB2 am 15. Juni offline war und keine Daten fünf Tage lang gesendet hat, wäre der Ausführungszeitpunkt irgendwann am 15. Juni. Die Dimension von &quot;Gestern&quot;wäre beispielsweise der 14. Juni, obwohl heute der 20. Juni ist.
