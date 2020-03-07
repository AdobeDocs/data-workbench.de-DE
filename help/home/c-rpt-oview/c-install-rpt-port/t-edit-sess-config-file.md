---
description: Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens "global.asa", um Benutzersitzungen zu initialisieren.
solution: Analytics
title: Sitzungskonfigurationsdatei bearbeiten
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sitzungskonfigurationsdatei bearbeiten{#edit-the-session-configuration-file}

Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens &quot;global.asa&quot;, um Benutzersitzungen zu initialisieren.

Bei der Installation [!DNL Report Portal]müssen Sie diese Datei wie angegeben bearbeiten. Die [!DNL global.asa] Datei befindet sich im Ordner \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ändern Sie keine anderen Parameter in dieser Konfigurationsdatei.

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die [!DNL global.asa] Datei in einem Texteditor wie Notepad.
1. Optional. Um Benutzern den Zugriff [!DNL Report Portal] ohne Authentifizierung zu ermöglichen, ändern Sie den Parameterwert Session(&quot;In&quot;) in true. Die Standardeinstellung ist &quot;false&quot;. Dadurch werden alle Benutzer authentifiziert, die versuchen, Zugriff zu erhalten [!DNL Report Portal].
1. Wenn Ihr Laufwerk auf einem anderen Laufwerk als dem Laufwerk C installiert [!DNL Report Portal] ist, ändern Sie den Wert des Parameters Session(&quot;Drive&quot;) in den richtigen Laufwerksort.
1. Ändern Sie für den Parameter Session(&quot;DBPath&quot;) den Wert, um den Pfad zur Datenbank anzuzeigen, der die zum Authentifizieren von [!DNL Report Portal] Benutzern erforderlichen Informationen enthält. Geben Sie nicht den Laufwerksbuchstaben ein, sondern achten Sie darauf, einen nachfolgenden Schrägstrich einzufügen.

   Beispiel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Speichern Sie die Datei.
1. Um zu überprüfen, ob die [!DNL Report Portal] Dateien korrekt installiert wurden und über den angegebenen virtuellen Ordner erreicht werden können, öffnen Sie die folgende Seite in Ihrem Browser:

   http://*YourServerAddress*/*YourPortalName*

   Beispiel: [!DNL http://localhost/VisualReportPortal]

   Wenn die [!DNL Report Portal] ASPs korrekt installiert wurden, sollte die Portal-Anmeldeseite angezeigt werden. Wenn diese Seite nicht angezeigt wird, stellen Sie sicher, dass ASPs in Ihrem IIS aktiviert sind, und überprüfen Sie die Zuordnungen der virtuellen Ordner.

