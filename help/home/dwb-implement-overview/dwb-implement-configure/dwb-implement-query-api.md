---
description: Eine kurze Anleitung zum Einrichten einer Abfrage-API.
title: Abfrage-API-Einrichtung
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abfrage-API-Einrichtung{#query-api-setup}

Eine kurze Anleitung zum Einrichten einer Abfrage-API.

Führen Sie die folgenden Schritte aus, um die Abfrage-API einzurichten:

1. Abfrage-API-Zertifikatakquise

   Senden Sie eine E-Mail an das Tech Ops Team von Adobe Email - `Dataworkbench@adobe.com`.

   Bitte geben Sie den KN-Namen an, den Sie für die Abfrage-API verwenden möchten (geben Sie einen allgemeinen Namen wie die `<Client>` Abfrage-API ein).

   >[!NOTE]
   >
   >Tech Ops generiert das Zertifikat und lädt es in eine URL hoch. Teilen Sie den Adobe-Beratern bitte mit, nachdem sie die Benachrichtigung von Tech Ops über die erfolgreiche Erstellung des Tickets erhalten haben, damit das Ticket von ihnen zurückgeschickt wird.

1. Herunterladen und Extrahieren des API-Stunnel. Rufen Sie die Datei api-stunnel von Ihrem Berater ab.

   Stellen Sie sicher, dass Perl auf Ihrem Computer installiert ist.

   Kopieren Sie im extrahierten Ordner (dem Ordnerpfad, in den Sie die Datei kopieren) das Abfrage-API-Zertifikat in den *Stunnel* -Ordner.

1. Stunnel.conf konfigurieren

   Es sollte eine Datei mit dem Namen *stunnel.conf* im *Stunnel* -Ordner (in den Sie Ihr Zertifikat kopiert haben) geben.

   Bearbeiten Sie die Datei im Editor.

   ![](assets/dwb_impl_API1.png)

   Ändern Sie die Parameter wie folgt: ![](assets/dwb_impl_API2.png)

   Zwei Parameter müssen in dieser Datei geändert werden.

   * *Cert* = Der Name in Ihrem Zertifikat. In diesem Beispiel ist es Aadhithiya Ramani QAPI Client.pem.
   * *Connect* = Der Servername für die Haupt-DPU.

1. Kopieren der Datei *Query.pm*.

   Die Datei *Query.pm* steht im Insight API-Ordner zur Verfügung.

   Kopieren Sie die *Datei &quot;Query.pm* &quot;und fügen Sie sie in Ihren Perl Library-Ordner ein (normalerweise ist dies *C:\Perl64\lib *, aber überprüfen Sie, wo die Perl auf Ihrem Computer installiert ist).

1. Die Datei *api-http.pl* ändern

   Die Datei &quot;api-http.pl&quot;ist im Ordner &quot;api-stunnel&quot;verfügbar.

   Nur ein Parameter, der geändert werden soll

   *Mein $profile* = Der Profilname, für den Sie die Abfrage-API konfigurieren.

1. Installieren Sie die Abfrage-API.

   Öffnen Sie die Eingabeaufforderung in Ihrem System als &quot;Administrator&quot;und navigieren Sie zu dem Ordner, in dem Sie den *Stunnel* extrahiert haben, wie folgt: ![](assets/dwb_impl_API3.png)

   Führen Sie folgenden Befehl aus *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   Nach dem Ausführen des Befehls erscheint ein Fenster, in dem angegeben wird, dass der *Stunnel* installiert ist.

   >[!NOTE]
   >
   >Nach dem Ausführen des Befehls erscheint ein Fenster, in dem angegeben wird, dass der *Stunnel* installiert ist.

1. Testen der Query API-Stunnel-Konfiguration

   Der letzte Schritt dieses Prozesses besteht darin, die Konfiguration der Abfrage-API zu testen. In der Eingabeaufforderung, die Sie zum Installieren des api-stunnel-Ordners verwendet haben. ![](assets/dwb_impl_API5.png)

   Führen Sie das in diesem Ordner verfügbare Perl-Skript mit dem folgenden Befehl* perl api-http.pl* aus. ![](assets/dwb_impl_API6.png)

   Nach der Ausführung des Skripts sollten die Ergebnisse dem Screenshot unten entsprechen (die Datums- und Werte im Ergebnis variieren je nach Zeitraum und andere Parameter im Profil, für das Sie die Abfrage-API konfiguriert haben (in Schritt 6). ![](assets/dwb_impl_API7.png)

