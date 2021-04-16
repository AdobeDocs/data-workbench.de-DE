---
description: Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens "global.asa", um Benutzersitzungen zu initialisieren.
title: Bearbeiten der Datei für die Sitzungskonfiguration
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Bearbeiten der Datei für die Sitzungskonfiguration{#edit-the-session-configuration-file}

Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens &quot;global.asa&quot;, um Benutzersitzungen zu initialisieren.

Wenn Sie [!DNL Report Portal] installieren, müssen Sie diese Datei wie angegeben bearbeiten. Die Datei [!DNL global.asa] befindet sich im Ordner \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ändern Sie keine anderen Parameter in dieser Konfigurationsdatei.

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL global.asa] in einem Texteditor wie Notepad.
1. Optional. Um Benutzern den Zugriff auf [!DNL Report Portal] ohne Authentifizierung zu ermöglichen, ändern Sie den Parameterwert Session(&quot;In&quot;) in true. Die Standardeinstellung ist &quot;false&quot;. Dadurch werden alle Benutzer authentifiziert, die versuchen, auf [!DNL Report Portal] zuzugreifen.
1. Wenn Ihr [!DNL Report Portal] auf einem anderen Laufwerk als dem C-Laufwerk installiert ist, ändern Sie den Wert des Parameters Session(&quot;Drive&quot;) in den richtigen Speicherort des Laufwerks.
1. Ändern Sie für den Parameter Session(&quot;DBPath&quot;) den Wert, um den Pfad zur Datenbank anzuzeigen, der die zum Authentifizieren von [!DNL Report Portal]-Benutzern erforderlichen Informationen enthält. Geben Sie nicht den Laufwerksbuchstaben ein, sondern achten Sie darauf, einen nachfolgenden Schrägstrich einzufügen.

   Beispiel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Speichern Sie die Datei.
1. Um zu überprüfen, ob die [!DNL Report Portal]-Dateien korrekt installiert wurden und über den angegebenen virtuellen Ordner erreicht werden können, öffnen Sie die folgende Seite in Ihrem Browser:

   http://*YourServerAddress*/*YourPortalName*

   Beispiel: [!DNL http://localhost/VisualReportPortal]

   Wenn die [!DNL Report Portal]-ASPs korrekt installiert wurden, sollte die Portal-Anmeldeseite angezeigt werden. Wenn diese Seite nicht angezeigt wird, überprüfen Sie, ob ASPs in Ihrem IIS aktiviert sind, und überprüfen Sie bei der Dublette die Zuordnung der virtuellen Verzeichnisse.
