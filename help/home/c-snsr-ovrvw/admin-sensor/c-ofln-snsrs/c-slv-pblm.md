---
description: Wenn ein Webserver aufgrund eines Fehlers offline geht, ist die Lösung einfach und erfordert einen Data Workbench-Benutzer mit entsprechenden Berechtigungen, um die Datei "Log Processing Mode.cfg"zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt "Offline-Quellen"hinzuzufügen.
title: Lösung des Problems
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Lösung des Problems{#solving-the-problem}

{{eol}}

Wenn ein Webserver aufgrund eines Fehlers offline geht, ist die Lösung einfach und erfordert einen Data Workbench-Benutzer mit entsprechenden Berechtigungen, um die Datei &quot;Log Processing Mode.cfg&quot;zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt &quot;Offline-Quellen&quot;hinzuzufügen.

In diesem Abschnitt der Datei wird die [!DNL data workbench server] dass keine Daten von dieser Quelle mehr erwartet werden sollten, da sie tatsächlich offline ist.

>[!NOTE]
>
>Diese Änderung muss nicht von einem Adobe Consultant vorgenommen werden. Jeder, der über die entsprechenden Berechtigungen zum Öffnen der [!DNL Log Processing Mode.cfg] kann diese Änderung vornehmen.

Wenn WEB2 beginnt, Daten erneut zu senden, wird die [!DNL data workbench server] stellt die Quelle wieder online und passt die Ausführungszeit an, um das letzte Mal wiederzugeben, wenn Daten aus allen Quellen eingehen, von denen sie Kenntnis hat. Mit anderen Worten, neue Daten, die in das System eingehen, haben Vorrang vor dem, was in der [!DNL Log Processing Mode.cfg file].

Wenn WEB2 wieder offline geht, wird die Ausführungszeit wieder angehalten und Sie müssen die [!DNL Log Processing Mode.cfg] erneut zu laden, obwohl WEB2 möglicherweise bereits als Offline-Quelle aufgeführt ist. Dies ist ein Artefakt des Designs des Produkts, das der Definition der Ausführungsdauer entspricht: das letzte Mal, dass das System über Daten für alle bekannten Quellen verfügt.

Wenn Sie weitere Webserver hinzufügen (WEB4, WEB5, WEB6), beginnen diese mit dem Senden von Daten an die [!DNL data workbench server], müssen Sie nichts tun, um die [!DNL data workbench server] die neuen Quellen erkennen. Dem System wird einfach bewusst, dass es, wie oben beschrieben, Daten aus diesen neuen Quellen erwarten sollte.
