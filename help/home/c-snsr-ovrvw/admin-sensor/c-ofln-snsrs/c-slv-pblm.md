---
description: Wenn ein Webserver aufgrund eines Fehlers offline ist, ist die Lösung eine einfache, die einen Data Workbench-Benutzer mit entsprechenden Berechtigungen erfordert, um die Datei "Log Processing Mode.cfg"zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt "Offline-Quellen"hinzuzufügen.
solution: Insight
title: Lösung des Problems
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lösung des Problems{#solving-the-problem}

Wenn ein Webserver aufgrund eines Fehlers offline ist, ist die Lösung eine einfache, die einen Data Workbench-Benutzer mit entsprechenden Berechtigungen erfordert, um die Datei &quot;Log Processing Mode.cfg&quot;zu öffnen und die ID des Sensors (in unserem Beispiel WEB2) zum Abschnitt &quot;Offline-Quellen&quot;hinzuzufügen.

Dieser Abschnitt der Datei teilt dem [!DNL data workbench server] mit, dass keine Daten mehr von dieser Quelle erwartet werden sollten, da sie tatsächlich offline ist.

>[!NOTE]
>
>Diese Änderung muss nicht von einem Adobe-Berater vorgenommen werden. Jeder, der über die entsprechenden Berechtigungen zum Öffnen der [!DNL Log Processing Mode.cfg] Datei verfügt, kann diese Änderung vornehmen.

Wenn WEB2 beginnt, Daten erneut zu senden, [!DNL data workbench server] bringt die Quelle zurück ins Netz und passt die Ausführungszeit an, um das letzte Mal, wenn sie Daten aus allen Quellen erhalten hat, von denen sie Kenntnis hat, widerzuspiegeln. Mit anderen Worten, neue Daten, die in das System eingehen, haben Vorrang vor dem, was in der [!DNL Log Processing Mode.cfg file].

Wenn WEB2 wieder offline geht, wird die Ausführungszeit wieder beendet und Sie müssen die [!DNL Log Processing Mode.cfg] Datei erneut bearbeiten, obwohl WEB2 bereits als Offlinequelle aufgeführt ist. Dies ist ein Artefakt der Konstruktion des Produkts, das der Definition des Ausführungszeitpunkts entspricht: das letzte Mal, dass das System über Daten für alle bekannten Quellen verfügt.

Wenn Sie weitere Webserver (WEB4, WEB5, WEB6) hinzufügen und damit beginnen, Daten an den Server zu senden, [!DNL data workbench server]müssen Sie nichts tun, damit die neuen Quellen erkannt [!DNL data workbench server] werden. Das System wird sich einfach bewusst, dass es Daten aus diesen neuen Quellen erwartet, wie oben beschrieben.
