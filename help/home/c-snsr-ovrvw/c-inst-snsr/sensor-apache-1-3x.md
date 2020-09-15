---
description: Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für einen Apache Server 1.3.x unter RedHat Linux 7.x oder höher, SUSE Linux 9.x oder höher, Sun Solaris SPARC 2.6 oder höher, Sun Solaris x86 9 oder höher, FreeBSD 4 oder höher oder Mac OS X PowerPC.
title: Apache-Server 1.3.x unter Linux, Sun Solaris, FreeBSD oder Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---


# Apache-Server 1.3.x unter Linux, Sun Solaris, FreeBSD oder Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für einen Apache Server 1.3.x unter RedHat Linux 7.x oder höher, SUSE Linux 9.x oder höher, Sun Solaris SPARC 2.6 oder höher, Sun Solaris x86 9 oder höher, FreeBSD 4 oder höher oder Mac OS X PowerPC.

Die Programm-Dateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für den jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte auf hoher Ebene ausführen:

## Installieren der Programm-Dateien {#section-aae323e252394212bf4096d65fdd280c}

Anweisungen zum Extrahieren und Installieren der Programm-Dateien für Sensor auf dem Servercomputer.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   * Unter Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Unter Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Kopieren Sie die entpackten Programm-Dateien in die in der folgenden Tabelle angegebenen Ordner:

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Zielgruppen-Verzeichnis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Sammlerlastmodul </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Transmitter-Programm </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--ODER-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei des Sensors </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, mit dem das digitale Zertifikat validiert wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

**Berechtigungen in den Programm-Dateien**

Falsche Berechtigungen für die Programm-Dateien verursachen die meisten Probleme bei der Installation von Sensor.

Bitte stellen Sie sicher, dass Sie die Berechtigungen genau wie in diesem Abschnitt angegeben einstellen.

Standardmäßig haben die Programm-Dateien in der tar-Datei die folgenden Berechtigungen. Je nachdem, wie Ihr System konfiguriert ist, können diese Einstellungen beim Extrahieren der Dateien geändert (nicht maskiert) werden. Um die Berechtigungen auf die empfohlenen Standardeinstellungen zurückzusetzen, verwenden Sie die folgenden chmod-Befehle. Vergewissern Sie sich, dass die Ordner, in denen Sie die Dateien installiert haben, mindestens diese Zugriffsebene zulassen.

| Datei | Standardberechtigungen | chmod, Befehl |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

Die [!DNL txlogd.conf] Datei enthält die Konfigurationsparameter für Sensor.

Sie müssen die Datei bearbeiten, um unter anderem die Größe der Disk-Warteschlange, die Adresse des Insight-Servers und die ID anzugeben, die an die von diesem Sensor erzeugten Daten angehängt wird.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* Erforderliche Parameter sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* Optionale Parameter sind Einstellungen, die standardmäßig auf vordefinierte Werte (die Sie ändern können) oder optionale Funktionen angewendet werden.

So bearbeiten Sie die Konfigurationsdatei des Sensors

1. Öffnen Sie die Datei /etc/txlogd.conf in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
1. Speichern und schließen Sie die Datei.

## Beginn des Transmitters und Erstellen der Disk-Warteschlange {#section-a453d912ec3d47aa8e40ccacf527119d}

Anweisungen zum Erstellen der Disk-Warteschlange nach der Konfiguration der Datei &quot;txlogd.conf&quot;.

1. Wenn der Ordner, in dem sich die Disk-Warteschlange befindet, noch nicht vorhanden ist, erstellen Sie ihn. Stellen Sie sicher, dass der Ordner sowohl dem Sammlermodul als auch dem Transmitter-Programm Lese-/Schreibzugriff auf die Datei bietet.
1. Führen Sie auf dem Computer, auf dem Sensor installiert ist, den folgenden Befehl aus, um den Sender Beginn:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Die Option &quot;i&quot;in diesem Befehl Beginn den Transmitter im interaktiven Modus. Dieser Modus zeigt Transmittermeldungen auf dem Bildschirm an und ermöglicht Ihnen auch die Interaktion mit dem Transmitter mithilfe von Tastaturbefehlen.
   * Die Option &quot;c&quot;weist den Sender an, die Datenträgerwarteschlange zu erstellen.
   * Die Option &quot;f&quot;gibt den Speicherort der Konfigurationsdatei an.

1. Überprüfen Sie, ob der Transmitter die Disk-Warteschlange an dem im Parameter QueueFile angegebenen Speicherort und in der im Parameter QueueSize angegebenen Größe erstellt hat.
1. Wenn die Warteschlange nicht korrekt erstellt wurde, drücken Sie Strg+C, um den Transmitter zu beenden, und führen Sie dann die folgenden Schritte aus:

   1. Überprüfen Sie die Datei &quot;txtlogd.conf&quot;und stellen Sie sicher, dass die Parameter &quot;QueueFile&quot;und &quot;QueueSize&quot;korrekt eingestellt sind.
   1. Vergewissern Sie sich, dass das Gerät, dem die Disk-Warteschlange zugewiesen ist, betriebsbereit ist und über ausreichend Speicherplatz verfügt, um eine Datei der im Parameter QueueSize angegebenen Größe aufzunehmen.
   1. Nehmen Sie alle erforderlichen Korrekturen vor und wiederholen Sie diesen Vorgang.

## hinzufügen der Sammlung auf dem Webserver {#section-a7fb6425956f4f518ae3a7db091b33d2}

Bei Apache-Servern ist der Collector ein dynamisches freigegebenes Objekt, das Sie in Ihren Webserverprozess laden.

Um den Collector Ihrem Webserver hinzuzufügen, müssen Sie die Datei &quot;httpd.conf&quot;wie unten beschrieben bearbeiten und den Webserver neu starten.

Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie mit einem Texteditor die [!DNL httpd.conf] Datei für den Webserver, dessen Ereignisses Sensor erfasst.
1. hinzufügen die folgenden Zeilen am Dateiende:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen ist die Groß-/Kleinschreibung zu beachten. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver neu. Der Collector wird mit dem Webserver geladen und beginnt damit, Ereignis-Daten zu sammeln und in die Disk-Warteschlange zu schreiben.

## Sensor testen {#section-83d9f60b39a6474f9c76bee3e19b2575}

Beginn des Senders und vergewissern Sie sich, dass er erfolgreich eine Verbindung zum Insight-Server herstellen und Ereignis-Daten übermitteln kann.

>[!NOTE]
>
>Um zu überprüfen, ob der Transmitter erfolgreich Ereignis-Daten an den Insight-Server senden kann, stellen Sie sicher, dass die Zielgruppe Insight Server installiert und ausgeführt wird, bevor Sie den folgenden Test starten.

1. Wenn der Transmitter noch nicht ausgeführt wird, starten Sie ihn mit dem folgenden Befehl neu:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öffnen Sie einen Browser (auf einem beliebigen Computer) und fordern Sie eine Seite vom Webserver an, auf dem Sensor ausgeführt wird (wählen Sie unbedingt eine Seite aus, die von Sensor überwacht wird).
1. Nachdem Sie die Anforderung gesendet haben, überprüfen Sie die Konsole des Senders auf Meldungen, die darauf hinweisen, dass Ereignis-Daten an die Zielgruppe Insight Server gesendet werden.
1. Wenn Sensor die Daten nicht erfolgreich übermittelt, überprüfen Sie, ob:

   * Der Zielgruppe Insight Server wird ausgeführt.
   * Die [!DNL ServerAddress] Parameter und [!DNL ServerPort] Parameter werden in korrekt eingestellt [!DNL txtlogd.conf].

   * Wenn Sie einen Servernamen [!DNL ServerAddress] angegeben haben, versuchen Sie stattdessen, seine numerische IP-Adresse zu verwenden. Der [!DNL CertName] Parameterwert stimmt exakt mit dem allgemeinen Namen überein, der im digitalen Zertifikat der Zielgruppe Insight Server angezeigt wird.

## Transmitter in Ihr Systemstartskript Hinzufügen {#section-4e1ffa6e043941ab91411d91d596477a}

Informationen, die sicherstellen, dass der Transmitter beim Neustart des Webservercomputers automatisch geladen wird.

hinzufügen Sie den folgenden Befehl (der den Transmitter startet) an Ihr Systemstartskript.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Dieser Befehl Beginn den Sender als Daemon. Die vom Sender erzeugten Betriebs- und Fehlermeldungen werden in syslog geschrieben.

>[!NOTE]
>
>Bei einigen Solaris-Benutzern tritt möglicherweise der Fehler &quot;Mutex kann nicht erfasst werden&quot;auf. Damit Sensor auf diesen Systemen ordnungsgemäß funktioniert, muss die folgende Zeile entweder der Datei &quot;/etc/system&quot;hinzugefügt oder in ihr bearbeitet werden:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>Die standardmäßige Solaris-Einstellung ist 60. Basierend auf Tests, die mit Sensor durchgeführt werden, der drei Semaphores für jede Instanz verwendet, empfiehlt Adobe, 1024 als Einstellung zu verwenden. Diese Zahl ist hoch genug, damit Sensor zusammen mit anderen Anwendungen auf dem Server, die Semaphores erfordern, funktionieren kann, hat aber keine Auswirkung auf die Leistung. Um diese Empfehlung zu unterstützen, beachten Sie bitte, dass Adrian Cockcroft in seinem Buch Sun Performance and Tuning (Prentice Hall, Oktober 1994) Folgendes angeführt hat: &quot;Datenbanken verwenden meist viele Einstellungen für gemeinsamen Speicher und Semaphore. Diese wirken sich nicht auf die Leistung aus. Solange sie groß genug sind, laufen die Programme.&quot;

