---
description: Neue Funktionen und Fehlerbehebungen in Data Workbench 6.73.
title: Data Workbench 6.73 - Versionshinweise
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.73 Release Notes{#data-workbench-release-notes}

Neue Funktionen und Fehlerbehebungen in Data Workbench 6.73.

## Data Workbench 6.73 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Neue Funktionen und Fehlerbehebungen in Data Workbench 6.73.

## Fehlerkorrekturen {#section-160baf6ea04c45a993777ee4260691ed}

* Es wurde ein Workstation-Problem behoben, durch das sich die Benutzer nicht bei einigen Hardwarekomponenten mit hoher Auflösung und hoher DPI-Einstellung anmelden konnten.
* Es wurde ein Problem auf dem Server behoben, bei dem E-Mail in Archivdateinamen fehlte, wenn die IMS-Anmeldung verwendet wurde.
* OpenSSL wurde auf Version 1.1.0h aktualisiert, in der verschiedene Sicherheitsrisiken behoben wurden und die neue SSL-Verschlüsselungen enthält.
* Die unten aufgelisteten Open-Source-Bibliotheken wurden auf die neuesten stabilen Versionen aktualisiert.

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Es wurde eine Fehlerprotokollierung für den Fall hinzugefügt, dass die Zeilenanzahl der Abfragedatei die 357913908 unterstützten Zeilen überschreitet.

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation Version 6.73 stellt keine Verbindung zu Data Workbench Server Version 6.61 und älter her. Der Grund dafür ist, dass ältere Serverversionen eine schwache Form von Chiffern verwenden, die in Version 6.73 nicht unterstützt wird. So aktivieren Sie die Unterstützung für ältere Versionen

   1. Überschreibt die standardmäßige SSL-Ciphers-Liste auf dem Server mit einer starken, von OpenSSL Version 1.0.1h unterstützten Chipliste. Um diese Funktion zu überschreiben, fügen Sie die Schlüsseldateien &quot;SSL Ciphers&quot;in den Ordnern &quot;Communications.cfg&quot;in den Ordnern &quot;Komponenten&quot;und &quot;Komponenten für Verarbeitungsserver&quot;hinzu. Beispiel: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Stellen Sie sicher, dass der Schlüssel auf derselben Ebene wie der SSL-Anschluss platziert wird. Weitere Informationen finden Sie unter [Kommunikationskonfigurationseinstellungen](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Platzieren Sie die aktuelle Datei &quot;trust_ca_cert.pem&quot;auf den Servern 6.61 und älter. Diese Einstellung gilt für alle Workstation 6.7x-Versionen.

Siehe [archivierte Versionshinweise](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) für Data Workbench 5.3 bis 5.52.
