---
description: Informationen zur Behebung von Webserverproblemen, z. B. wenn der Webserver nicht mehr gedreht werden kann oder der Webserver ausfällt.
solution: Insight
title: Die Ursachen
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Die Ursachen{#understanding-the-causes}

Informationen zur Behebung von Webserverproblemen, z. B. wenn der Webserver nicht mehr gedreht werden kann oder der Webserver ausfällt.

## Wenn ein Webserver aus der Drehung herausgenommen wird {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Wenn ein Webserver aus der Rotation eines Serverpools herausgenommen wird, aber ansonsten mit dem Sender verbunden ist, der periodische Heartbeats sendet, wird die Ausführungszeit beibehalten, und es ist kein Eingreifen von irgendjemandem erforderlich.

## Wenn ein Webserver ausfällt {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Wenn ein Webserver aufgrund eines katastrophalen Fehlers vollständig offline ist oder keine Daten oder Heartbeats sendet, wird die Ausführungszeit auf den [!DNL data workbench server] Haltestellen angegeben, um sicherzustellen, dass dies das letzte Mal ist, dass die Daten von ALL den Datenquellen, von denen er Kenntnis hat, [!DNL data workbench server] empfangen wurden. Das System selbst verarbeitet weiterhin Daten, die in Data Workbench noch für die Analyse verfügbar sind, aber alles, was auf der Ausführungszeit basiert, funktioniert nicht [!DNL data workbench server] . Beispielsweise löst die Ausführungszeit die Berichterstellung aus und wird verwendet, um viele abgeleitete Dimensionen im System zu erstellen. Wenn die Ausführungszeit beendet ist, wird keine Berichterstellung ausgelöst und diese bestimmten abgeleiteten Dimensionen sind nicht verfügbar.

Wenn beispielsweise WEB2 am 15. Juni offline war und keine Daten fünf Tage lang gesendet hat, wäre der Ausführungszeitpunkt irgendwann am 15. Juni. Die Dimension von gestern wäre beispielsweise der 14. Juni, obwohl heute der 20. Juni ist.
