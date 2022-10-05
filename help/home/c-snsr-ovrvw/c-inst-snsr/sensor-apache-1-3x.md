---
description: Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für einen Apache-Server 1.3.x unter RedHat Linux 7.x oder höher, SUSE Linux 9.x oder höher, Sun Solaris SPARC 2.6 oder höher, Sun Solaris x86 9 oder höher, FreeBSD 4 oder höher oder Mac OS X PowerPC.
title: Apache-Server 1.3.x unter Linux, Sun Solaris, FreeBSD oder Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Apache-Server 1.3.x unter Linux, Sun Solaris, FreeBSD oder Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für einen Apache-Server 1.3.x unter RedHat Linux 7.x oder höher, SUSE Linux 9.x oder höher, Sun Solaris SPARC 2.6 oder höher, Sun Solaris x86 9 oder höher, FreeBSD 4 oder höher oder Mac OS X PowerPC.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden allgemeinen Schritte ausführen:

## Installieren der Programmdateien {#section-aae323e252394212bf4096d65fdd280c}

Anweisungen zum Extrahieren und Installieren der Programmdateien für Sensor auf dem Servercomputer.

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

1. Kopieren Sie die entpackten Programmdateien in die in der folgenden Tabelle angegebenen Verzeichnisse:

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Zielverzeichnis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Kollektorlastmodul </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Das Senderprogramm </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für den Sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein gesteuertes Experiment konfigurieren. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies tun können). Sie können die Datei stattdessen an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen können, oder einfach die Datei aus dem Installationspaket extrahieren. Weitere Informationen zu kontrollierten Experimenten finden Sie im Leitfaden zu kontrollierten Experimenten mit Insight.

**Berechtigungen für die Programmdateien**

Falsche Berechtigungen für die Programmdateien verursachen die meisten Probleme bei der Installation von Sensor.

Stellen Sie sicher, dass Sie die Berechtigungen genau wie in diesem Abschnitt beschrieben festlegen.

Standardmäßig haben die Programmdateien in der Tar-Datei die folgenden Berechtigungen. Abhängig davon, wie Ihr System konfiguriert ist, können diese Einstellungen beim Extrahieren der Dateien geändert (nicht maskiert) werden. Um die Berechtigungen auf die empfohlenen Standardeinstellungen zurückzusetzen, verwenden Sie die folgenden chmod-Befehle. Vergewissern Sie sich, dass die Verzeichnisse, in denen Sie die Dateien installiert haben, mindestens diese Zugriffsebene zulassen.

| Datei | Standardberechtigungen | chmod, Befehl |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Bearbeiten Sie die Konfigurationsdatei für den Sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

Die [!DNL txlogd.conf] enthält die Konfigurationsparameter für Sensor.

Sie müssen die Datei bearbeiten, um unter anderem die Größe der Festplattenwarteschlange, die Adresse des Insight Servers und die Kennung anzugeben, die an die von diesem Sensor erzeugten Daten angehängt werden soll.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* Erforderliche Parameter sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* Optionale Parameter sind Einstellungen, die standardmäßig vordefinierte Werte enthalten (die Sie ändern können) oder optionale Funktionen aktivieren.

Bearbeiten der Sensorkonfigurationsdatei

1. Öffnen Sie die Datei /etc/txlogd.conf in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
1. Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Festplattenwarteschlange. {#section-a453d912ec3d47aa8e40ccacf527119d}

Anweisungen zum Erstellen der Datenträgerwarteschlange nach der Konfiguration der Datei &quot;txlogd.conf&quot;.

1. Wenn der Ordner, in dem sich die Warteschlange befindet, noch nicht vorhanden ist, erstellen Sie ihn. Stellen Sie sicher, dass der Ordner sowohl dem Collector-Modul als auch dem Transmitter-Programm Lese-/Schreibzugriff auf die Datei bietet.
1. Führen Sie auf dem Computer, auf dem Sensor installiert ist, den folgenden Befehl aus, um den Transmitter zu starten:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Die Option &quot;i&quot;in diesem Befehl startet den Transmitter im interaktiven Modus. Dieser Modus zeigt Transmitter-Nachrichten auf dem Bildschirm an und ermöglicht Ihnen auch die Interaktion mit dem Transmitter mithilfe von Tastaturbefehlen.
   * Die Option &quot;c&quot;weist den Sender an, die Datenträgerwarteschlange zu erstellen.
   * Die Option &quot;f&quot;gibt den Speicherort der Konfigurationsdatei an.

1. Stellen Sie sicher, dass der Transmitter die Festplattenwarteschlange an dem im Parameter QueueFile angegebenen Speicherort und der im Parameter QueueSize angegebenen Größe erstellt hat.
1. Wenn die Warteschlange nicht korrekt erstellt wurde, drücken Sie Strg+C, um den Transmitter zu beenden, und gehen Sie dann wie folgt vor:

   1. Überprüfen Sie die Datei txtlogd.conf und überprüfen Sie, ob die Parameter QueueFile und QueueSize richtig eingestellt sind.
   1. Überprüfen Sie, ob das Gerät, dem die Festplattenwarteschlange zugewiesen ist, betriebsbereit ist und über ausreichend Speicherplatz verfügt, um eine Datei mit der im Parameter QueueSize angegebenen Größe zu speichern.
   1. Nehmen Sie die notwendigen Korrekturen vor und wiederholen Sie diesen Vorgang.

## Hinzufügen des Sammlers zum Webserver {#section-a7fb6425956f4f518ae3a7db091b33d2}

Bei Apache-Servern ist der Kollektor ein dynamisches gemeinsames Objekt, das Sie in Ihren Webserverprozess laden.

Um den Wächter zu Ihrem Webserver hinzuzufügen, müssen Sie die Datei &quot;httpd.conf&quot;wie unten beschrieben bearbeiten und den Webserver neu starten.

Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie mithilfe eines Texteditors die [!DNL httpd.conf] Datei für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie die folgenden Zeilen am Ende der Datei hinzu:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen wird zwischen Groß- und Kleinschreibung unterschieden. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver neu. Der Kollektor wird mit dem Webserver geladen und beginnt mit der Erfassung von Ereignisdaten und dem Schreiben in die Datenträgerwarteschlange.

## Testen des Sensors {#section-83d9f60b39a6474f9c76bee3e19b2575}

Starten Sie den Transmitter, stellen Sie sicher, dass er eine erfolgreiche Verbindung zum Insight Server herstellen und Ereignisdaten an ihn übertragen kann.

>[!NOTE]
>
>Um sicherzustellen, dass der Transmitter Ereignisdaten erfolgreich an den Insight Server senden kann, stellen Sie sicher, dass der Ziel-Insight Server installiert ist und ausgeführt wird, bevor Sie den folgenden Test starten.

1. Wenn der Transmitter noch nicht ausgeführt wird, starten Sie ihn mit dem folgenden Befehl neu:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öffnen Sie einen Browser (auf einem beliebigen Computer) und fordern Sie eine Seite vom Webserver an, auf dem Sensor ausgeführt wird (wählen Sie unbedingt eine Seite aus, die von Sensor überwacht wird).
1. Nachdem Sie die Anforderung ausgegeben haben, überprüfen Sie die Konsole des Senders auf Meldungen, die darauf hinweisen, dass Ereignisdaten an den Ziel-Insight Server gesendet werden.
1. Wenn Sensor Daten nicht erfolgreich übermittelt, überprüfen Sie Folgendes:

   * Der Insight Server-Zielserver wird ausgeführt.
   * Die [!DNL ServerAddress] und [!DNL ServerPort] -Parameter korrekt in [!DNL txtlogd.conf].

   * Wenn Sie [!DNL ServerAddress] Verwenden Sie einen Servernamen und versuchen Sie stattdessen die numerische IP-Adresse zu verwenden. Der Wert der [!DNL CertName] entspricht dem allgemeinen Namen, der im digitalen Zertifikat des Ziel-Insight-Servers genau angezeigt wird.

## Hinzufügen des Transmitters zum Systemstartskript {#section-4e1ffa6e043941ab91411d91d596477a}

Informationen, die sicherstellen, dass der Transmitter automatisch geladen wird, wenn der Webserver-Computer neu gestartet wird.

Fügen Sie den folgenden Befehl (der den Transmitter startet) zu Ihrem Systemstartskript hinzu.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Dieser Befehl startet den Transmitter als Daemon. Vom Transmitter generierte Betriebs- und Fehlermeldungen werden in syslog geschrieben.

>[!NOTE]
>
>Bei einigen Solaris-Benutzern tritt möglicherweise der Fehler &quot;unfähig, mutex zu erfassen&quot;auf. Damit Sensor auf diesen Systemen ordnungsgemäß funktioniert, muss die folgende Zeile entweder in der Datei /etc/system hinzugefügt oder bearbeitet werden:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>Die standardmäßige Solaris-Einstellung ist 60. Basierend auf Tests, die mit Sensor durchgeführt wurden und für jede Instanz drei Semaphores verwenden, empfiehlt Adobe, die Einstellung 1024 zu verwenden. Diese Zahl ist hoch genug, damit Sensor zusammen mit anderen Anwendungen auf dem Server funktioniert, die möglicherweise Semaphores erfordern, aber keine Auswirkungen auf die Leistung haben. Um diese Empfehlung zu unterstützen, beachten Sie bitte, dass Adrian Cockcroft in seinem Buch Sun Performance and Tuning (Prentice Hall, Oktober 1994) Folgendes angegeben hat: &quot;Datenbanken verwenden in der Regel viel gemeinsamen Speicher und Semaphore-Einstellungen. Diese wirken sich nicht auf die Leistung aus. Solange sie groß genug sind, laufen die Programme.&quot;
