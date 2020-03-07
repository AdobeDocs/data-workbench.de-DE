---
description: Anweisungen zum Installieren und Konfigurieren von Apache Server 2.0.40, 2.0.42 oder höher, Apache Server 2.2 oder Apache Server 2.4 unter Linux, Sun Solaris oder FreeBSD.
title: Apache Server 2.0.40, 2.0.42 oder höher und Apache Server 2.2 oder 2.4 unter Linux, Solaris oder FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 2.0.40, 2.0.42 oder höher und Apache Server 2.2 oder 2.4 unter Linux, Solaris oder FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

Anweisungen zum Installieren und Konfigurieren von Apache Server 2.0.40, 2.0.42 oder höher, Apache Server 2.2 oder Apache Server 2.4 unter Linux, Sun Solaris oder FreeBSD.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte auf hoher Ebene ausführen:

Die folgenden Apache-Server werden unterstützt:

* Apache Server 2.0.40 unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher.
* Apache Server 2.0.40, 2.0.42 oder höher, Apache Server 2.2 oder Apache Server 2.4 unter Linux, Sun Solaris oder FreeBSD
* Apache Server 2.0.42 oder höher, der unter RedHat Linux 7.x oder höher, Sun Solaris SPARC 2.6 oder höher, SUSE Linux 9.x oder höher oder FreeBSD 5.3 ausgeführt wird.
* Apache Server 2.0.42 oder höher mit 64-Bit Versionen von RedHat Linux ES 4 und ES 5.
* Apache Server 2.2 unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher.
* Apache Server 2.4 unter RedHat Linux 7.x oder höher, Sun Solaris x86_64 oder FreeBSD

>[!NOTE]
>
>Obwohl die Anweisungen zur Installation von Sensoren auf Webservern mit den Apache Server-Versionen 2.0.40, 2.0.42 oder höher (32-Bit und 64-Bit) oder 2.2 identisch sind (sofern in den folgenden Verfahren nicht anders angegeben), unterscheiden sich die Installationsdateien für jede Version. Bevor Sie den Sensor installieren, stellen Sie sicher, dass Sie die richtigen Installationsdateien für die Apache Server- und Betriebssystemversionen erhalten haben, die Sie ausführen.

## Programmdateien installieren {#section-2f3e85083b4f4aa989a85997330e86ae}

Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   * Unter Linux:

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * Unter Solaris:

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
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Das Sammlerlastmodul. </td> 
   <td colname="col3"> <i> IBMHttpServer/Module</i> </td> 
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

## Aktivieren der Protokollierung auf dem Sametime-Server {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Schritte, mit denen Sie sich beim Sametime-Server anmelden können.

1. Verwenden Sie den Lotus Domino Administrator-Client, um eine Verbindung zum Lotus Domino-Server herzustellen, auf dem Sametime ausgeführt wird.
1. Klicken Sie im Lotus Domino Administrator auf die Registerkarte Dateien und doppelklicken Sie dann auf Sametime Configuration - stconfig.nsf, um die Sametime-Konfigurationsdatei zu öffnen.
1. Öffnen Sie in der Datei &quot;Sametime-Konfiguration&quot;das Formular &quot;Community Services&quot;und doppelklicken Sie auf eine beliebige Stelle im Formular, um in den Bearbeitungsmodus zu wechseln.
1. Setzen Sie die Chat-Protokollierungsmarkierung auf &quot;strikt&quot;und den Capture-Diensttyp auf &quot;0x1000&quot;.
1. Speichern und schließen Sie das Community Services-Formular und schließen Sie dann die Sametime-Konfigurationsdatei.
1. Starten Sie den Sametime-Server neu.

## Bearbeiten der Sensorkonfigurationsdatei {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

## Hinzufügen des Sammlers zum Webserver {#section-c5b83ae4ebce430aa764f951e849b333}

Bei IBM HTTP-Servern ist der Collector ein dynamisches freigegebenes Objekt, das Sie in Ihren Webserverprozess laden.

Um den Collector Ihrem Webserver hinzuzufügen, müssen Sie die Datei &quot;httpd.conf&quot;wie unten beschrieben bearbeiten und den Webserver neu starten.

Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie in einem Texteditor die Datei &quot;httpd.conf&quot;für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie am Dateiende die folgenden zwei Zeilen hinzu:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen ist die Groß-/Kleinschreibung zu beachten. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver-Prozess neu (Sie müssen nicht den gesamten Servercomputer neu starten, sondern den Webserver-Prozess neu starten). Der Collector wird mit dem Webserver geladen und beginnt, Ereignisdaten zu sammeln und in die Disk-Warteschlange zu schreiben.

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

Dieser Befehl startet den Transmitter als Daemon. Die vom Sender erzeugten Betriebs- und Fehlermeldungen werden in syslog geschrieben.
