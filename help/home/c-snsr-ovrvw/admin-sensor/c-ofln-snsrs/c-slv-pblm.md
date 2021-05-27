---
description: Wenn ein Webserver aufgrund eines Fehlers offline geht, ist die Lösung einfach und erfordert einen Data Workbench-Benutzer mit entsprechenden Berechtigungen, um die Datei "Log Processing Mode.cfg"zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt "Offline-Quellen"hinzuzufügen.
title: Lösung des Problems
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Lösung des Problems{#solving-the-problem}

Wenn ein Webserver aufgrund eines Fehlers offline geht, ist die Lösung einfach und erfordert einen Data Workbench-Benutzer mit entsprechenden Berechtigungen, um die Datei &quot;Log Processing Mode.cfg&quot;zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt &quot;Offline-Quellen&quot;hinzuzufügen.

Dieser Abschnitt der Datei teilt dem [!DNL data workbench server] mit, dass keine Daten von dieser Quelle mehr erwartet werden sollten, da sie tatsächlich offline ist.

>[!NOTE]
>
>Diese Änderung muss nicht von einem Adobe Consultant vorgenommen werden. Jeder, der über die entsprechenden Berechtigungen zum Öffnen der Datei [!DNL Log Processing Mode.cfg] verfügt, kann diese Änderung vornehmen.

Wenn WEB2 beginnt, Daten erneut zu senden, bringt das [!DNL data workbench server] die Quelle zurück und passt den Ausführungszeitpunkt an, um das letzte Mal widerzuspiegeln, wenn es Daten aus allen Quellen erhalten hat, von denen es Kenntnis hat. Mit anderen Worten, neue Daten, die in das System eingehen, haben Vorrang vor dem, was in [!DNL Log Processing Mode.cfg file] geschrieben ist.

Wenn WEB2 wieder offline geht, wird die Ausführungszeit wieder angehalten und Sie müssen die [!DNL Log Processing Mode.cfg]-Datei erneut bearbeiten, obwohl WEB2 möglicherweise bereits als Offline-Quelle aufgelistet ist. Dies ist ein Artefakt des Designs des Produkts, das der Definition der Ausführungsdauer entspricht: das letzte Mal, dass das System über Daten für alle bekannten Quellen verfügt.

Wenn Sie weitere Webserver (WEB4, WEB5, WEB6) hinzufügen und diese Daten an [!DNL data workbench server] senden, müssen Sie nichts unternehmen, damit die [!DNL data workbench server] die neuen Quellen erkennen. Dem System wird einfach bewusst, dass es, wie oben beschrieben, Daten aus diesen neuen Quellen erwarten sollte.
