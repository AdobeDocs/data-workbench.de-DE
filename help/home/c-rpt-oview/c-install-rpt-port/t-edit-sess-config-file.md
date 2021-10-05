---
description: Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens global.asa , um Benutzersitzungen zu initialisieren.
title: Bearbeiten der Datei für die Sitzungskonfiguration
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Bearbeiten der Datei für die Sitzungskonfiguration{#edit-the-session-configuration-file}

Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens global.asa , um Benutzersitzungen zu initialisieren.

Wenn Sie [!DNL Report Portal] installieren, müssen Sie diese Datei wie angegeben bearbeiten. Die Datei [!DNL global.asa] befindet sich im Ordner \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ändern Sie keine anderen Parameter in dieser Konfigurationsdatei.

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL global.asa] in einem Texteditor wie Notepad.
1. Optional. Damit Benutzer ohne Authentifizierung auf [!DNL Report Portal] zugreifen können, ändern Sie den Parameterwert Session(&quot;In&quot;) in &quot;true&quot;. Der Standardwert ist &quot;false&quot;, was alle Benutzer authentifiziert, die versuchen, auf [!DNL Report Portal] zuzugreifen.
1. Wenn Ihr [!DNL Report Portal] auf einem anderen Laufwerk als dem Laufwerk C installiert ist, ändern Sie den Wert des Parameters Session(&quot;Drive&quot;) an den richtigen Laufwerksort.
1. Ändern Sie für den Parameter Session(&quot;DBPath&quot;) den Wert, um den Pfad zur Datenbank widerzuspiegeln, der die zum Authentifizieren von [!DNL Report Portal]-Benutzern erforderlichen Informationen enthält. Schließen Sie den Laufwerksbuchstaben nicht ein, stellen Sie jedoch sicher, dass Sie einen nachfolgenden Schrägstrich einfügen.

   Beispiel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Speichern Sie die Datei.
1. Um sicherzustellen, dass die [!DNL Report Portal]-Dateien ordnungsgemäß installiert wurden und über das dafür vorgesehene virtuelle Verzeichnis erreicht werden können, öffnen Sie die folgende Seite in Ihrem Browser:

   https://*YourServerAddress*/*YourPortalName*

   Beispiel: [!DNL https://localhost/VisualReportPortal]

   Wenn die [!DNL Report Portal] ASPs korrekt installiert wurden, sollte die Portal-Anmeldeseite angezeigt werden. Wenn diese Seite nicht angezeigt wird, überprüfen Sie, ob ASPs in Ihrem IIS aktiviert sind, und überprüfen Sie Ihre virtuellen Ordnerzuordnungen.
