---
description: Anweisungen zum Installieren und Konfigurieren von Apache Server 2.0.40, 2.0.42 oder höher, Apache Server 2.2 oder Apache Server 2.4 unter Linux, Sun Solaris oder FreeBSD.
title: Apache-Server 2.0.40, 2.0.42 oder höher und Apache-Server 2.2 oder 2.4 unter Linux, Solaris oder FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
exl-id: d5b943be-e9ca-4601-88c7-bb2bfdc0d080
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 2%

---

# Apache-Server 2.0.40, 2.0.42 oder höher und Apache-Server 2.2 oder 2.4 unter Linux, Solaris oder FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

{{eol}}

Anweisungen zum Installieren und Konfigurieren von Apache Server 2.0.40, 2.0.42 oder höher, Apache Server 2.2 oder Apache Server 2.4 unter Linux, Sun Solaris oder FreeBSD.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden allgemeinen Schritte ausführen:

Die folgenden Apache-Server werden unterstützt:

* Apache-Server 2.0.40, der unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher ausgeführt wird.
* Apache-Server 2.0.40, 2.0.42 oder höher, Apache-Server 2.2 oder Apache-Server 2.4 unter Linux, Sun Solaris oder FreeBSD
* Apache Server 2.0.42 oder höher, der unter RedHat Linux 7.x oder höher, Sun Solaris SPARC 2.6 oder höher, SUSE Linux 9.x oder höher oder FreeBSD 5.3 ausgeführt wird.
* Apache Server 2.0.42 oder höher, die unter 64-Bit-Versionen von RedHat Linux ES 4 und ES 5 ausgeführt werden.
* Apache Server 2.2 wird unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher ausgeführt.
* Apache-Server 2.4, der unter RedHat Linux 7.x oder höher ausgeführt wird, oder Sun Solaris x86_64 oder FreeBSD

>[!NOTE]
>
>Obwohl die Anweisungen zum Installieren von Sensoren auf Webservern mit den Apache Server-Versionen 2.0.40, 2.0.42 oder höher (32-Bit und 64-Bit) oder 2.2 identisch sind (sofern in den folgenden Verfahren nicht angegeben), unterscheiden sich die Installationsdateien für jede Version. Stellen Sie vor der Installation des Sensors sicher, dass Sie die richtigen Installationsdateien für den Apache-Server und die Betriebssystemversionen erhalten haben, die Sie ausführen.

## Installieren der Programmdateien {#section-2f3e85083b4f4aa989a85997330e86ae}

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

1. Kopieren Sie die entpackten Programmdateien in die in der folgenden Tabelle angegebenen Verzeichnisse:

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
   <td colname="col2"> Das Wächter-Lademodul. </td> 
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Das Transmitter-Programm. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für Sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein gesteuertes Experiment konfigurieren. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies tun können). Sie können die Datei stattdessen an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen können, oder einfach die Datei aus dem Installationspaket extrahieren. Weitere Informationen zu kontrollierten Experimenten finden Sie im Leitfaden zu kontrollierten Experimenten mit Insight.

**Berechtigungen für die Programmdateien**

>[!NOTE]
>
>Falsche Berechtigungen für die Programmdateien verursachen die meisten Probleme bei der Installation von Sensor. Stellen Sie sicher, dass Sie die Berechtigungen genau wie in diesem Abschnitt beschrieben festlegen.
>
>Standardmäßig haben die Programmdateien in der Tar-Datei die folgenden Berechtigungen. Abhängig davon, wie Ihr System konfiguriert ist, können diese Einstellungen beim Extrahieren der Dateien geändert (nicht maskiert) werden. Um die Berechtigungen auf die empfohlenen Standardeinstellungen zurückzusetzen, verwenden Sie die folgenden chmod-Befehle. Vergewissern Sie sich, dass die Verzeichnisse, in denen Sie die Dateien installiert haben, mindestens diese Zugriffsebene zulassen.

| Datei | Standardberechtigungen | chmod, Befehl |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Aktivieren Sie die Protokollierung auf dem Sametime-Server. {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Schritte, die die Anmeldung beim Sametime Server ermöglichen.

1. Verwenden Sie den Client &quot;Lotus Domino Administrator&quot;, um eine Verbindung zum Lotus Domino-Server herzustellen, auf dem Sametime ausgeführt wird.
1. Klicken Sie im Lotus Domino Administrator auf die Registerkarte Dateien und doppelklicken Sie dann auf Sametime Configuration - stconfig.nsf , um die Datei Sametime Configuration zu öffnen.
1. Öffnen Sie in der Datei &quot;Sametime Configuration&quot;das Formular &quot;Community Services&quot;und doppelklicken Sie auf eine beliebige Stelle des Formulars, um in den Bearbeitungsmodus zu wechseln.
1. Setzen Sie das Chat Logging Flag auf &quot;strict&quot;und den Capture Service-Typ auf &quot;0x1000&quot;.
1. Speichern und schließen Sie das Formular Community-Services und schließen Sie dann die Datei Sametime-Konfiguration .
1. Starten Sie den Sametime-Server neu.

## Bearbeiten der Datei für die Sensor-Konfiguration {#section-de0eb4a646394b61abb6cd5a2b706de0}

Die [!DNL txlogd.conf] enthält die Konfigurationsparameter für Sensor.

Sie müssen diese Datei bearbeiten, um unter anderem die Größe und den Speicherort der Warteschlangendatei der Festplatte, die Adresse des Insight-Servers und die ID anzugeben, die an die von diesem Sensor erzeugten Ereignisdaten angehängt werden.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* **Erforderliche Parameter** sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* **Optionale Parameter** sind Einstellungen, die standardmäßig vordefinierte Werte enthalten (die Sie ändern können) oder optionale Funktionen aktivieren.

**Bearbeiten der Sensorkonfigurationsdatei**

* Öffnen Sie die [!DNL /etc/txlogd.conf] in einem Texteditor speichern und die erforderlichen Parameter sowie die gewünschten optionalen Parameter festlegen.
* Speichern und schließen Sie die Datei.

**Bearbeiten der Sensorkonfigurationsdatei**

1. Öffnen Sie die [!DNL /etc/txlogd.conf] in einem Texteditor speichern und die erforderlichen Parameter sowie die gewünschten optionalen Parameter festlegen.
1. Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Festplattenwarteschlange. {#section-55630de65f264274aefd771da2002852}

Nachdem Sie die Datei txlogd.conf konfiguriert haben, können Sie das Transmitter-Programm starten, sie als Windows-Dienst registrieren und die Disk-Warteschlange erstellen.

1. Wenn der Ordner, in dem sich die Warteschlange befindet, noch nicht vorhanden ist, erstellen Sie ihn. Stellen Sie sicher, dass der Ordner sowohl dem Collector-Modul als auch dem Transmitter-Programm Lese-/Schreibzugriff auf die Datei bietet.

   Weitere Informationen zu den Berechtigungen, die für die Dateiwarteschlangendateien erforderlich sind, finden Sie unter Berechtigungen für Sensor-UNIX-Dateien .
1. Führen Sie auf dem Computer, auf dem Sensor installiert ist, den folgenden Befehl aus, um den Transmitter zu starten:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Die Option &quot;i&quot;in diesem Befehl startet den Transmitter im &quot;interaktiven Modus&quot;. Dieser Modus zeigt Transmitter-Nachrichten auf dem Bildschirm an und ermöglicht Ihnen auch die Interaktion mit dem Transmitter mithilfe von Tastaturbefehlen.
   * Die Option &quot;c&quot;weist den Sender an, die Datenträgerwarteschlange zu erstellen.
   * Die Option &quot;f&quot;gibt den Speicherort der Konfigurationsdatei an.

   Weitere Informationen zu den Optionen, die Sie beim Starten des Senders verwenden können, finden Sie unter Befehlszeilenoptionen für Sensor-Transmitter .

1. Stellen Sie sicher, dass der Transmitter die Festplattenwarteschlange an dem im Parameter QueueFile angegebenen Speicherort und der im Parameter QueueSize angegebenen Größe erstellt hat.
1. Wenn die Warteschlange nicht korrekt erstellt wurde, drücken Sie Strg+C, um den Transmitter zu beenden, und führen Sie dann die folgenden Schritte aus:

   1. Überprüfen Sie die Datei txtlogd.conf und überprüfen Sie, ob die Parameter QueueFile und QueueSize richtig eingestellt sind.
   1. Überprüfen Sie, ob das Gerät, dem die Festplattenwarteschlange zugewiesen ist, betriebsbereit ist und über ausreichend Speicherplatz verfügt, um eine Datei mit der im Parameter QueueSize angegebenen Größe zu speichern.
   1. Nehmen Sie die notwendigen Korrekturen vor und wiederholen Sie diesen Vorgang.

## Hinzufügen des Sammlers zum Webserver {#section-c5b83ae4ebce430aa764f951e849b333}

Bei IBM-HTTP-Servern ist der Kollektor ein dynamisches freigegebenes Objekt, das Sie in Ihren Webserverprozess laden.

Um den Wächter zu Ihrem Webserver hinzuzufügen, müssen Sie die Datei &quot;httpd.conf&quot;wie unten beschrieben bearbeiten und den Webserver neu starten.

Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie mithilfe eines Texteditors die Datei &quot;httpd.conf&quot;für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie die folgenden beiden Zeilen am Ende der Datei hinzu:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen wird zwischen Groß- und Kleinschreibung unterschieden. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver-Prozess neu (Sie müssen nicht den gesamten Server neu starten, sondern einfach den Webserver-Prozess neu starten). Der Kollektor wird mit dem Webserver geladen und fängt an, Ereignisdaten zu erfassen und in die Datenträgerwarteschlange zu schreiben.

## Testen des Sensors {#section-0dae181ef8884f10a57f6cfda8500969}

Vergewissern Sie sich, dass der Sammler Ereignisdaten erfasst und der Sender sie an den Ziel-Insight Server sendet.

>[!NOTE]
>
>Um sicherzustellen, dass der Transmitter Ereignisdaten erfolgreich an den Insight Server senden kann, stellen Sie sicher, dass der Ziel-Insight Server installiert ist und ausgeführt wird, bevor Sie den folgenden Test starten.

1. Wenn der Transmitter noch nicht ausgeführt wird, starten Sie ihn mit dem folgenden Befehl neu:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öffnen Sie einen Browser (auf einem beliebigen Computer) und fordern Sie eine Seite vom Webserver an, auf dem Sensor ausgeführt wird (wählen Sie unbedingt eine Seite aus, die von Sensor überwacht wird).
1. Nachdem Sie die Anforderung ausgegeben haben, überprüfen Sie die Konsole des Senders auf Meldungen, die darauf hinweisen, dass Ereignisdaten an den Ziel-Insight Server gesendet werden.
1. Wenn Sensor Daten nicht erfolgreich übermittelt, überprüfen Sie, ob:

   * Der Insight Server-Zielserver wird ausgeführt.
   * Die Parameter ServerAddress und ServerPort werden in txtlogd.conf korrekt festgelegt. Wenn Sie &quot;ServerAddress&quot;mit einem Servernamen angegeben haben, versuchen Sie stattdessen, die zugehörige numerische IP-Adresse zu verwenden.
   * Der Wert des CertName-Parameters entspricht dem allgemeinen Namen, der im digitalen Zertifikat des Ziel-Insight-Servers exakt angezeigt wird.

## Hinzufügen des Transmitters zum Systemstartskript {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informationen zum automatischen Laden des Senders in Ihr System-Startskript.

Um sicherzustellen, dass der Transmitter beim Neustart des Webserver-Computers automatisch geladen wird, fügen Sie den folgenden Befehl (der den Transmitter startet) zu Ihrem Systemstartskript hinzu:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Dieser Befehl startet den Transmitter als Daemon. Vom Transmitter generierte Betriebs- und Fehlermeldungen werden in syslog geschrieben.
