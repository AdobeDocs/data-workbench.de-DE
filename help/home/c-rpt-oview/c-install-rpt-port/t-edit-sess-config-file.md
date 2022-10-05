---
description: Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens global.asa , um Benutzersitzungen zu initialisieren.
title: Bearbeiten der Datei für die Sitzungskonfiguration
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Bearbeiten der Datei für die Sitzungskonfiguration{#edit-the-session-configuration-file}

{{eol}}

Das Report Portal verwendet die Informationen in einer Konfigurationsdatei namens global.asa , um Benutzersitzungen zu initialisieren.

Bei der Installation [!DNL Report Portal]müssen Sie diese Datei wie angegeben bearbeiten. Die [!DNL global.asa] -Datei im Ordner \*PortalName*\PortalASP\ gespeichert.

>[!NOTE]
>
>Ändern Sie keine anderen Parameter in dieser Konfigurationsdatei.

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, den [!DNL global.asa] in einem Texteditor wie Notepad.
1. Optional. So können Benutzer auf [!DNL Report Portal] ohne Authentifizierung ändern Sie den Parameterwert Session(&quot;In&quot;) in &quot;true&quot;. Die Standardeinstellung ist &quot;false&quot;, wodurch alle Benutzer authentifiziert werden, die versuchen, auf [!DNL Report Portal].
1. Wenn [!DNL Report Portal] auf einem anderen Laufwerk als dem Laufwerk C installiert ist, ändern Sie den Wert des Parameters Session(&quot;Drive&quot;) auf den richtigen Speicherort des Laufwerks.
1. Ändern Sie für den Parameter Session(&quot;DBPath&quot;) den Wert, um den Pfad zur Datenbank widerzuspiegeln, der die für die Authentifizierung erforderlichen Informationen enthält. [!DNL Report Portal] Benutzer. Schließen Sie den Laufwerksbuchstaben nicht ein, stellen Sie jedoch sicher, dass Sie einen nachfolgenden Schrägstrich einfügen.

   Beispiel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Speichern Sie die Datei.
1. So stellen Sie sicher, dass [!DNL Report Portal] -Dateien korrekt installiert wurden und über das dafür vorgesehene virtuelle Verzeichnis erreicht werden können, öffnen Sie die folgende Seite in Ihrem Browser:

   https://*YourServerAddress*/*YourPortalName*

   Beispiel: [!DNL https://localhost/VisualReportPortal]

   Wenn die Variable [!DNL Report Portal] ASPs ordnungsgemäß installiert wurden, sollte die Portal-Anmeldeseite angezeigt werden. Wenn diese Seite nicht angezeigt wird, überprüfen Sie, ob ASPs in Ihrem IIS aktiviert sind, und überprüfen Sie Ihre virtuellen Ordnerzuordnungen.
