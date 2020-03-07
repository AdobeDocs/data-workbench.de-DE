---
description: Dies ist eine schnelle Anleitung, die Ihnen die Mindestanforderungen für die Validierung der internen und externen FTP-Einrichtung gibt.
title: Validierung interner und externer FTP-Server
uuid: bc381c1d-df27-4009-920b-1a804b36c204
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Validierung interner und externer FTP-Server{#validation-of-internal-and-external-ftp-servers}

Dies ist eine schnelle Anleitung, die Ihnen die Mindestanforderungen für die Validierung der internen und externen FTP-Einrichtung gibt.

Ein internes FTP wird verwendet, wenn ein Berater/Architekt, der mit Adobe intern arbeitet, eine Verbindung zur FTP-Site zum Hochladen oder Herunterladen von Dateien herstellen muss, während ein externes FTP hauptsächlich für Sie als Benutzer zum Hochladen der erforderlichen Datendateien erforderlich ist.

Weitere Informationen zum Einrichten von FTP-Servern finden Sie unter [Dateiübertragungsprotokoll](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html).

## Validierungsschritte - Externes FTP {#section-24428111b5c542ce81a765cd63424b97}

1. Öffnen Sie eine Eingabeaufforderung. (Windows+R und geben Sie cmd ein)
1. Type ftp `<ftp server>`
1. Geben Sie Benutzernamen und Kennwort ein. ![](assets/dwb_impl_ftp1.png)

1. Ändern Sie den lokalen Ordner, aus dem eine Datei verschoben werden kann. Verwenden Sie diesen Befehl:

[!DNL ftp> lcd C:\Users\andixit\Desktop]

lokalen Ordner jetzt [!DNL C:\Users\andixit\Desktop].

1. Kopieren Sie die Datei vom lokalen zum Remote-Speicherort. ![](assets/dwb_impl_ftp2.png)

1. Abmelden vom Remote-Server. (Befehl unten verwenden)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Eine andere Möglichkeit, FTP zu validieren, ist die Verwendung von FileZilla. Geben Sie Hostnamen, Benutzernamen, Kennwort und Anschluss an. Die rechte Seite des Bedienfelds ist eine Remote-Site und die linke Seite ist eine lokale Site. Zur Validierung von FTP ziehen Sie Dateien per Drag &amp; Drop von einer lokalen zu einer Remote-Site und v.v.

![](assets/dwb_impl_ftp3.png)

## Validierungsschritte - Internes FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

Die oben genannten Schritte können zur Validierung der internen FTP-Funktion von jedem Adobe-Server ausgeführt werden.
