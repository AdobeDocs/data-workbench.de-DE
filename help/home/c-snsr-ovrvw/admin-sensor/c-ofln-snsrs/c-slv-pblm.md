---
description: Wenn ein Webserver aufgrund eines Fehlers offline ist, ist die Lösung eine einfache Lösung, die einen Data Workbench-Benutzer mit entsprechenden Berechtigungen erfordert, um die Datei "Log Processing Mode.cfg"zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt "Offline-Quellen"hinzuzufügen.
title: Lösung des Problems
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Lösung des Problems{#solving-the-problem}

Wenn ein Webserver aufgrund eines Fehlers offline ist, ist die Lösung eine einfache Lösung, die einen Data Workbench-Benutzer mit entsprechenden Berechtigungen erfordert, um die Datei &quot;Log Processing Mode.cfg&quot;zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt &quot;Offline-Quellen&quot;hinzuzufügen.

Dieser Abschnitt der Datei teilt dem [!DNL data workbench server] mit, dass er keine Daten mehr von dieser Quelle erwarten sollte, da sie tatsächlich offline ist.

>[!NOTE]
>
>Diese Änderung muss nicht von einem Adobe Consultant vorgenommen werden. Jeder, der über die entsprechenden Berechtigungen zum Öffnen der Datei [!DNL Log Processing Mode.cfg] verfügt, kann diese Änderung vornehmen.

Wenn WEB2 beginnt, Daten erneut zu senden, bringt das [!DNL data workbench server] die Quelle wieder online und passt die Ausführungszeit an, um das letzte Mal zu widerspiegeln, wenn Daten aus allen Quellen, von denen es Kenntnis hat, empfangen wurden. Mit anderen Worten, neue Daten, die in das System eingehen, haben Vorrang vor dem, was in [!DNL Log Processing Mode.cfg file] geschrieben ist.

Wenn WEB2 wieder offline geht, wird die Ausführungszeit wieder beendet und Sie müssen die [!DNL Log Processing Mode.cfg]-Datei erneut bearbeiten, obwohl WEB2 möglicherweise bereits als Offlinequelle aufgeführt ist. Dies ist ein Artefakt der Konstruktion des Produkts, das der Definition des Ausführungszeitpunkts entspricht: das letzte Mal, dass das System über Daten für alle bekannten Quellen verfügt.

Wenn Sie weitere Webserver (WEB4, WEB5, WEB6) hinzufügen und diese beginnen, Daten an die [!DNL data workbench server] zu senden, müssen Sie nichts tun, damit die [!DNL data workbench server] die neuen Quellen erkennen. Das System wird sich einfach bewusst, dass es Daten aus diesen neuen Quellen erwartet, wie oben beschrieben.
