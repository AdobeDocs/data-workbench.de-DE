---
description: Eine kurze Anleitung zum Einrichten einer Abfrage-API.
title: Einrichten der Abfrage-API
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Einrichten der Abfrage-API{#query-api-setup}

{{eol}}

Eine kurze Anleitung zum Einrichten einer Abfrage-API.

Gehen Sie wie folgt vor, um die Abfrage-API einzurichten:

1. Abfrage-API-Zertifikatakquise

   E-Mail an das Tech Ops Team von Adobe Email senden - `Dataworkbench@adobe.com`.

   Geben Sie den KN-Namen an, den Sie für die Abfrage-API verwenden möchten ( geben Sie einen allgemeinen Namen wie `<Client>` Abfrage-API).

   >[!NOTE]
   >
   >Tech Ops generiert das Zertifikat und lädt es in eine URL hoch. Teilen Sie den Berater der Adobe nach Erhalt der Benachrichtigung von Tech Ops über die erfolgreiche Erstellung des Tickets mit, damit das Ticket von ihnen zurückgesendet wird.

1. Herunterladen und Extrahieren des API-Stunnel. Rufen Sie die Datei &quot;api-stunnel&quot;von Ihrem Berater ab.

   Stellen Sie sicher, dass Perl auf Ihrem Computer installiert ist.

   Kopieren Sie im extrahierten Ordner (dem Ordnerpfad, in den Sie die Datei kopieren) Ihr Abfrage-API-Zertifikat in den *stunnel* Ordner.

1. Konfigurieren von Stunnel.conf

   Es sollte eine Datei namens *stunnel.conf* innerhalb der *Stunnel* Ordner (in den Sie Ihr Zertifikat kopiert haben).

   Bearbeiten Sie die Datei im Editor.

   ![](assets/dwb_impl_API1.png)

   Ändern Sie die Parameter wie folgt: ![](assets/dwb_impl_API2.png)

   Zwei Parameter müssen in dieser Datei geändert werden.

   * *Cert* = Der Name Ihres Zertifikats. In diesem Beispiel ist es Aadhithiya Ramani QAPI Client.pem.
   * *Verbinden* =Der Servername für Ihre Haupt-DPU.

1. Kopieren der *Query.pm*.

   Die *Query.pm* -Datei im Insight API-Ordner verfügbar.

   Kopieren Sie die *Query.pm* und fügen Sie sie in Ihren Perl Library-Ordner ein (normalerweise wird dies *C:\Perl64\lib * sein, aber überprüfen Sie, wo Perl auf Ihrem Computer installiert ist).

1. Ändern Sie die *api-http.pl* file

   Die Datei api-http.pl ist im Ordner api-stunnel verfügbar.

   Nur ein Parameter, der geändert werden soll

   *Mein $profile* = Der Profilname, für den Sie die Abfrage-API konfigurieren.

1. Installieren Sie die Abfrage-API.

   Öffnen Sie die Eingabeaufforderung in Ihrem System als &quot;Administrator&quot;und navigieren Sie zu dem Ordner, in den Sie die *stunnel* wie gezeigt: ![](assets/dwb_impl_API3.png)

   Führen Sie folgenden Befehl aus *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   Nach Ausführung des Befehls erscheint ein Fenster, in dem erklärt wird, dass die *stunnel* installiert ist.

   >[!NOTE]
   >
   >Nach Ausführung des Befehls erscheint ein Fenster, in dem erklärt wird, dass die *stunnel* installiert ist.

1. Testen der Query API-Stunnel-Konfiguration

   Der letzte Schritt dieses Prozesses besteht darin, die Konfiguration der Abfrage-API zu testen. In der Eingabeaufforderung, die Sie zum Installieren des Verzeichnisses api-stunnel verwendet haben. ![](assets/dwb_impl_API5.png)

   Führen Sie das in diesem Ordner verfügbare Perl-Skript mit dem folgenden Befehl aus:* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   Nach Ausführung des Skripts sollten die Ergebnisse dem folgenden Screenshot entsprechen (die Datums- und Uhrzeitwerte im Ergebnis variieren je nach Uhrzeit und anderen Parametern im Profil, für das Sie die Abfrage-API konfiguriert haben (in Schritt 6). ![](assets/dwb_impl_API7.png)
