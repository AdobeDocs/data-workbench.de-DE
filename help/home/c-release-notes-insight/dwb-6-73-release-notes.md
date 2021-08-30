---
description: Neue Funktionen und Fehlerbehebungen in Data Workbench 6.73.
title: Versionshinweise zu Data Workbench 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 26%

---

# Versionshinweise zu Data Workbench 6.73{#data-workbench-release-notes}

Neue Funktionen und Fehlerbehebungen in Data Workbench 6.73.

## Fehlerbehebungen {#section-160baf6ea04c45a993777ee4260691ed}

* Es wurde ein Workstation-Problem behoben, durch das sich die Benutzer nicht bei einigen Hardwarekomponenten mit hoher Auflösung und hoher DPI-Einstellung anmelden konnten.
* Fehlerkorrektur - E-Mail fehlt jetzt in den Archivdateinamen, wenn IMS-Login verwendet wird.
* OpenSSL wurde auf Version 1.1.0h aktualisiert, in der verschiedene Sicherheitsrisiken behoben wurden und die neue SSL-Verschlüsselungen enthält.
* Die unten aufgeführten Open-Source-Bibliotheken wurden auf die neuesten stabilen Versionen aktualisiert.

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Es wurde eine Fehlerprotokollierung für den Fall hinzugefügt, dass die Zeilenanzahl der Abfragedatei die 357913908 unterstützten Zeilen überschreitet.

## Bekanntes Problem {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation Version 6.73 stellt keine Verbindung zu Data Workbench-Servern ab Version 6.61 her. Der Grund dafür ist, dass ältere Serverversionen eine schwache Form von Chiffren verwenden, die in Version 6.73 nicht unterstützt wird. Um die Unterstützung älterer Versionen zu ermöglichen,

   1. Überschreiben Sie die standardmäßige SSL-Cipher-Liste auf dem Server mit einer starken Chiffre-Liste, die von OpenSSL Version 1.0.1h unterstützt wird. Um diese Funktion zu überschreiben, fügen Sie &quot;SSL-Ciphers&quot;in die &quot;Communications.cfg&quot;-Dateien ein, die in den Verzeichnissen &quot;Komponenten&quot;und &quot;Komponenten für Verarbeitungsserver&quot;verfügbar sind. Beispiel: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Stellen Sie sicher, dass der Schlüssel auf derselben Ebene wie der SSL-Port platziert ist. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die Kommunikation](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Platzieren Sie die neueste Datei trust_ca_cert.pem auf den Servern 6.61 und älteren Servern. Diese Einstellung gilt für alle Workstation 6.7x-Versionen.

Siehe [archivierte Versionshinweise](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) für Data Workbench 5.3 bis 5.52.
