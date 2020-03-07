---
description: Anleitungen zum Installieren und Konfigurieren von Sensor auf Webserverfamilie, die sich aus dem ursprünglichen Netscape Enterprise Web Server entwickelt haben, der auf Linux- oder Solaris-Computern ausgeführt wird. Umfasst Netscape Enterprise-, iPlanet-, Sun ONE- und Sun Java-Systemserver unter Linux oder Solaris.
title: Netscape Enterprise unter Linux oder Solaris
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Netscape Enterprise unter Linux oder Solaris{#netscape-enteprise-on-linux-or-solaris}

Anleitungen zum Installieren und Konfigurieren von Sensor auf Webserverfamilie, die sich aus dem ursprünglichen Netscape Enterprise Web Server entwickelt haben, der auf Linux- oder Solaris-Computern ausgeführt wird. Umfasst Netscape Enterprise-, iPlanet-, Sun ONE- und Sun Java-Systemserver unter Linux oder Solaris.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

Sensor unterstützt die folgenden Server, die unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher ausgeführt werden:

* Netscape Enterprise Server 3.6 oder höher
* iPlanet Web Server 4.0 oder höher

Sensor unterstützt diese Server, die unter Red Hat Linux 7.x oder höher oder Sun Solaris 8.x oder höher ausgeführt werden:

* Sun ONE Web Server 6.0 oder höher
* Sun Java System Web Server 6.1 oder höher

Sensor unterstützt diese Server, die unter Sun Solaris x86 9 oder höher ausgeführt werden:

* Sun Java System Web Server 6.1 oder höher

>[!NOTE]
>
>Die Installationsdatei für diese Webserverfamilie wird auf der Adobe-Downloadseite als &quot;Netscape Solaris Sensor&quot;oder &quot;Netscape LINUX Sensor&quot;aufgeführt.

Zum Installieren und Konfigurieren von Sensor müssen Sie die folgenden Schritte ausführen:

## Programmdateien installieren {#section-2f3e85083b4f4aa989a85997330e86ae}

Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   ```
   gunzip installationFilename.tar.gz 
   
       tar -xf installationFilename.tar
   ```

1. Kopieren Sie die entpackten Programmdateien in die in der folgenden Tabelle angegebenen Ordner:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Zielverzeichnis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aol_visual_sciences.so </td> 
   <td colname="col2"> Das Sammlerlastmodul. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Das Transmitterprogramm. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--ODER--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für den Sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, mit dem das digitale Zertifikat validiert wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor läuft (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

**Berechtigungen in den Programmdateien**

>[!NOTE]
>
>Falsche Berechtigungen für die Programmdateien verursachen die meisten Probleme bei der Installation von Sensor. Bitte stellen Sie sicher, dass Sie die Berechtigungen genau wie in diesem Abschnitt angegeben einstellen.
>
>Standardmäßig haben die Programmdateien in der tar-Datei die folgenden Berechtigungen. Je nachdem, wie Ihr System konfiguriert ist, können diese Einstellungen beim Extrahieren der Dateien geändert (nicht maskiert) werden. Um die Berechtigungen auf die empfohlenen Standardeinstellungen zurückzusetzen, verwenden Sie die folgenden chmod-Befehle. Vergewissern Sie sich, dass die Ordner, in denen Sie die Dateien installiert haben, mindestens diese Zugriffsebene zulassen.

| Datei | Standardberechtigungen | chmod, Befehl |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Bearbeiten der Sensorkonfigurationsdatei {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Die [!DNL txlogd.conf] Datei enthält die Konfigurationsparameter für Sensor.

Sie müssen diese Datei bearbeiten, um u. a. die Größe und den Speicherort der Disk-Warteschlangendatei, die Adresse des Insight-Servers und die ID anzugeben, die an die Ereignisdaten dieses Sensors angehängt wird.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* **Erforderliche Parameter** sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* **Optionale Parameter** sind Einstellungen, die standardmäßig auf vordefinierte Werte (die Sie ändern können) oder optionale Funktionen angewendet werden.

**So bearbeiten Sie die Konfigurationsdatei des Sensors**

* Öffnen Sie die [!DNL /etc/txlogd.conf] Datei in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
* Speichern und schließen Sie die Datei.

**So bearbeiten Sie die Konfigurationsdatei des Sensors**

1. Öffnen Sie die [!DNL /etc/txlogd.conf] Datei in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
1. Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Disk-Warteschlange {#section-55630de65f264274aefd771da2002852}

Nachdem Sie die Datei &quot;txlogd.conf&quot;konfiguriert haben, können Sie das Transmitter-Programm starten, es als Windows-Dienst registrieren und die Disk-Warteschlange erstellen.

1. Wenn der Ordner, in dem sich die Disk-Warteschlange befindet, noch nicht vorhanden ist, erstellen Sie ihn. Stellen Sie sicher, dass der Ordner sowohl dem Sammlermodul als auch dem Transmitter-Programm Lese-/Schreibzugriff auf die Datei bietet.

   Weitere Informationen zu den Berechtigungen, die für die Dateien in der Datenträgerwarteschlange erforderlich sind, finden Sie unter Sensor UNIX-Dateiberechtigungen.
1. Führen Sie auf dem Computer, auf dem Sensor installiert ist, den folgenden Befehl aus, um den Transmitter zu starten:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Die Option &quot;i&quot;in diesem Befehl startet den Transmitter im interaktiven Modus. Dieser Modus zeigt Transmittermeldungen auf dem Bildschirm an und ermöglicht Ihnen auch die Interaktion mit dem Transmitter mithilfe von Tastaturbefehlen.
   * Die Option &quot;c&quot;weist den Sender an, die Datenträgerwarteschlange zu erstellen.
   * Die Option &quot;f&quot;gibt den Speicherort der Konfigurationsdatei an.
   Weitere Informationen zu den Optionen, die Sie beim Starten des Senders verwenden können, finden Sie unter Optionen für die Sensor Transmitter-Befehlszeile.

1. Überprüfen Sie, ob der Transmitter die Disk-Warteschlange an dem im Parameter QueueFile angegebenen Speicherort und in der im Parameter QueueSize angegebenen Größe erstellt hat.
1. Wenn die Warteschlange nicht korrekt erstellt wurde, drücken Sie Strg+C, um den Transmitter zu beenden, und führen Sie dann die folgenden Schritte aus:

   1. Überprüfen Sie die Datei &quot;txtlogd.conf&quot;und stellen Sie sicher, dass die Parameter &quot;QueueFile&quot;und &quot;QueueSize&quot;korrekt eingestellt sind.
   1. Vergewissern Sie sich, dass das Gerät, dem die Disk-Warteschlange zugewiesen ist, betriebsbereit ist und über ausreichend Speicherplatz verfügt, um eine Datei der im Parameter QueueSize angegebenen Größe aufzunehmen.
   1. Nehmen Sie alle erforderlichen Korrekturen vor und wiederholen Sie diesen Vorgang.

## Hinzufügen des Sammlers zum AOL-Server {#section-c5b83ae4ebce430aa764f951e849b333}

Bei AOLServer ist der Collector ein dynamisches freigegebenes Objekt, das Sie in Ihren Webserverprozess laden.

Um den Collector zu Ihrem AOL-Server hinzuzufügen, müssen Sie die Konfigurationsdatei für Ihren Server wie unten beschrieben bearbeiten und den AOL-Server neu starten. Normalerweise trägt die Konfigurationsdatei des Servers den Namen &quot;nsd.tcl&quot;und befindet sich in dem Ordner, in dem AOL Server installiert ist.

1. Öffnen Sie die Konfigurationsdatei in einem Texteditor und suchen Sie den folgenden Abschnitt:

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. Fügen Sie die folgende Zeile hinzu. (Als einzelne Anweisung hinzufügen. Umbruch ignorieren (siehe unten)

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. Erstellen Sie wie folgt einen neuen Abschnitt.

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. Fügen Sie diesem neuen Abschnitt die Zeile hinzu:

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen ist die Groß-/Kleinschreibung zu beachten. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den AOL-Server neu. Der Collector wird geladen und beginnt mit der Erfassung der Ereignisdaten und dem Schreiben in die Disk-Warteschlange.

## Sensor testen {#section-0dae181ef8884f10a57f6cfda8500969}

Vergewissern Sie sich, dass der Sammler Ereignisdaten erfasst und der Sender sie an den Ziel-Insight-Server sendet.

>[!NOTE]
>
>Um zu überprüfen, ob der Transmitter Ereignisdaten erfolgreich an den Insight-Server senden kann, stellen Sie sicher, dass der Insight-Zielserver installiert und ausgeführt wird, bevor Sie den folgenden Test starten.

1. Wenn der Transmitter noch nicht ausgeführt wird, starten Sie ihn mit dem folgenden Befehl neu:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öffnen Sie einen Browser (auf einem beliebigen Computer) und fordern Sie eine Seite vom Webserver an, auf dem Sensor ausgeführt wird (wählen Sie unbedingt eine Seite aus, die von Sensor überwacht wird).
1. Nachdem Sie die Anforderung gesendet haben, überprüfen Sie die Konsole des Senders auf Meldungen, die darauf hinweisen, dass Ereignisdaten an den Ziel-Insight-Server gesendet werden.
1. Wenn Sensor die Daten nicht erfolgreich übermittelt, überprüfen Sie, ob:

   * Das Ziel Insight Server wird ausgeführt.
   * Die Parameter ServerAddress und ServerPort werden in txtlogd.conf korrekt eingestellt. Wenn Sie &quot;ServerAddress&quot;unter einem Servernamen angegeben haben, versuchen Sie stattdessen, die zugehörige numerische IP-Adresse zu verwenden.
   * Der Wert des CertName-Parameters stimmt exakt mit dem allgemeinen Namen überein, der im digitalen Zertifikat des Ziel-Insight-Servers angezeigt wird.

## Transmitter zum Systemstartskript hinzufügen {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informationen zum automatischen Laden des Senders in Ihr Systemstartskript.

Um sicherzustellen, dass der Transmitter beim Neustart des Webservercomputers automatisch geladen wird, fügen Sie dem Systemstartskript den folgenden Befehl (der den Transmitter startet) hinzu:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Dieser Befehl startet den Transmitter als Daemon. Die vom Sender erzeugten Betriebs- und Fehlermeldungen werden in [!DNL syslog]geschrieben.

Die standardmäßige Solaris-Einstellung ist 60. Auf der Grundlage von Tests, die mit Sensor durchgeführt werden, der für jede Instanz drei Semaphores verwendet, empfiehlt Adobe, die Einstellung 1024 zu verwenden. Diese Zahl ist hoch genug, damit Sensor zusammen mit anderen Anwendungen auf dem Server, die Semaphores erfordern, funktionieren kann, hat aber keine Auswirkung auf die Leistung. Um diese Empfehlung zu unterstützen, beachten Sie bitte, dass Adrian Cockcroft in seinem Buch Sun Performance and Tuning (Prentice Hall, Oktober 1994) Folgendes angeführt hat: &quot;Datenbanken verwenden meist viele Einstellungen für gemeinsamen Speicher und Semaphore. Diese wirken sich nicht auf die Leistung aus. Solange sie groß genug sind, laufen die Programme.&quot;
