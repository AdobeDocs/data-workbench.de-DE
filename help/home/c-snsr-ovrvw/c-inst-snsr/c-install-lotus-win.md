---
description: Anleitung zum Installieren und Konfigurieren von Sensor for Lotus Sametime für Windows 3.1 oder höher unter Microsoft Windows Server 2000 oder höher.
title: Lotus Sametime unter Windows Server 2000 oder höher
uuid: 5e24da54-7ef6-42cf-b693-cc4fd267af93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lotus Sametime unter Windows Server 2000 oder höher{#lotus-sametime-on-windows-server-or-later}

Anleitung zum Installieren und Konfigurieren von Sensor for Lotus Sametime für Windows 3.1 oder höher unter Microsoft Windows Server 2000 oder höher.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte auf hoher Ebene ausführen:

## Programmdateien installieren {#section-2f3e85083b4f4aa989a85997330e86ae}

Beim Ausführen von Sensor unter Sametime müssen sich die Programmdateien und die Datei mit der Disk-Warteschlange im selben Ordner befinden.

Daher müssen Sie vor der Installation der Programmdateien festlegen, wo Sie die Datenträgerwarteschlange unterhalten möchten, da dort auch die Programmdateien installiert werden müssen.

Verwenden Sie das folgende Verfahren, um die Programmdateien für Sensor zu extrahieren und zu installieren.

1. Beenden Sie den Lotus Domino Server und den Sametime Chat Logging Service.
1. Löschen oder sichern Sie auf Ihrem Windows-Computer im Verzeichnis Lotus Domino die Datei StChatLog.dll.
1. Extrahieren Sie den Inhalt der Installationsdatei in den Ordner &quot;Lotus Domino&quot;. Während dieses Schritts installiert Sensor die folgenden Dateien:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Ereignis-Viewer-Nachrichten </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stchatlog.dll </td> 
   <td colname="col2"> Sammlermodul </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Eine Excel-Tabellenkalkulationsdatei, die Architekten zum Konfigurieren eines kontrollierten Experiments verwenden können </p> <p>Sensor verwendet diese Datei nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, mit dem das digitale Zertifikat validiert wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Das Transmitterprogramm </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.conf </p> </td> 
   <td colname="col2"> Die Konfigurationsdatei des Sensors </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor läuft (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

## Aktivieren der Protokollierung auf dem Sametime-Server {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Schritte, mit denen Sie sich beim Sametime-Server anmelden können.

1. Verwenden Sie den Lotus Domino Administrator-Client, um eine Verbindung zum Lotus Domino-Server herzustellen, auf dem Sametime ausgeführt wird.
1. Klicken Sie im Lotus Domino Administrator auf die Registerkarte Dateien und doppelklicken Sie dann auf Sametime Configuration - stconfig.nsf, um die Sametime-Konfigurationsdatei zu öffnen.
1. Öffnen Sie in der Datei &quot;Sametime-Konfiguration&quot;das Formular &quot;Community Services&quot;und doppelklicken Sie auf eine beliebige Stelle im Formular, um in den Bearbeitungsmodus zu wechseln.
1. Setzen Sie die Chat-Protokollierungsmarkierung auf &quot;strikt&quot;und den Capture-Diensttyp auf &quot;0x1000&quot;.
1. Speichern und schließen Sie das Community Services-Formular und schließen Sie dann die Sametime-Konfigurationsdatei.
1. Starten Sie den Sametime-Server neu.

## Bearbeiten der Sensorkonfigurationsdatei {#section-de0eb4a646394b61abb6cd5a2b706de0}

Die Datei &quot;txlogd.conf&quot;enthält die Konfigurationsparameter für Sensor.

Sie müssen diese Datei bearbeiten, um u. a. die Größe und den Speicherort der Disk-Warteschlangendatei, die Adresse des Insight-Servers und die ID anzugeben, die an die Ereignisdaten dieses Sensors angehängt wird.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* **Erforderliche Parameter** sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* **Optionale Parameter** sind Einstellungen, die standardmäßig auf vordefinierte Werte (die Sie ändern können) oder optionale Funktionen angewendet werden.

**So bearbeiten Sie die Konfigurationsdatei des Sensors**

* Öffnen Sie die `<Sensor directory>/txlogd.conf` Datei in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
* Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Disk-Warteschlange {#section-55630de65f264274aefd771da2002852}

Nachdem Sie die Datei &quot;txlogd.conf&quot;konfiguriert haben, können Sie das Transmitter-Programm starten, es als Windows-Dienst registrieren und die Disk-Warteschlange erstellen.

1. Wählen Sie unter Windows im Startmenü Zubehör > Eingabeaufforderung.
1. Navigieren Sie im Fenster mit der Eingabeaufforderung zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

   ```
   txlog /regserver
   ```

   Dieser Befehl startet den Transmitter, erstellt die Disk-Warteschlange und registriert Sensor als Windows-Dienst.

1. Um sicherzustellen, dass der Transmitter ordnungsgemäß ausgeführt wird, klicken Sie auf Start > Systemsteuerung > Verwaltung > Dienste.

   >[!NOTE]
   >
   >Diese Befehlssequenz kann je nach verwendeter Windows-Version unterschiedlich sein.

   1. Suchen Sie in der Dienstliste den Eintrag für Sensor und vergewissern Sie sich, dass der Status Started und der Starttyp Automatisch ist.
   1. Schließen Sie das Bedienfeld &quot;Dienste&quot;.

1. Um zu überprüfen, ob Transmitter während des Starts Fehler auftraten, klicken Sie auf Start > Systemsteuerung > Verwaltung > Ereignisanzeige, um die Ereignisanzeige zu öffnen.

   >[!NOTE]
   >
   >Diese Befehlssequenz kann je nach verwendeter Windows-Version unterschiedlich sein.

   1. Wählen Sie im linken Bereich des Fensters &quot;Ereignisanzeige&quot;das Anwendungsprotokoll aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Spalte &quot;Quelle&quot;.
   1. Wenn Sie eine Fehlermeldung von &quot;Adobe&quot;erhalten, doppelklicken Sie auf den Fehler, um das Fenster &quot;Ereigniseigenschaften&quot;anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

1. Schließen Sie nach Abschluss der Überprüfung des Anwendungsprotokolls die Ereignisanzeige.
1. Vergewissern Sie sich, dass der Sender die Disk-Warteschlange (Diskq2000.log) in dem Ordner erstellt hat, in dem Sie die Sensor-Programmdateien installiert haben, und dass diese die Größe hat, die Sie im Parameter QueueSize in der Datei txlogd.conf angegeben haben.

   Wenn die Warteschlange nicht korrekt erstellt wurde:

   1. Überprüfen Sie die Datei &quot;txtlogd.conf&quot;und stellen Sie sicher, dass der Parameter QueueSize korrekt eingestellt ist.
   1. Vergewissern Sie sich, dass auf dem Gerät, auf dem Sensor installiert ist, ausreichend Speicherplatz für eine Datei der im Parameter QueueSize angegebenen Größe zur Verfügung steht.
   1. Beenden Sie den Transmitter über das Bedienfeld &quot;Dienste&quot;in Windows.
   1. Löschen Sie die Warteschlangendatei.
   1. Sensor erneut als Windows-Dienst registrieren: Wählen Sie unter Windows im Startmenü Zubehör > Eingabeaufforderung. Navigieren Sie im Fenster mit der Eingabeaufforderung zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

      ```
      txlog /regserver
      ```

      Der Transmitter ist für einen kontinuierlichen Betrieb ausgelegt. Wenn Sie den Computer neu starten, wird der Transmitter automatisch neu gestartet. Wenn Sie den Transmitter manuell starten und anhalten müssen, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun.

1. Starten Sie den Lotus Domino-Server und den Sametime Chat-Protokolldienst neu.

