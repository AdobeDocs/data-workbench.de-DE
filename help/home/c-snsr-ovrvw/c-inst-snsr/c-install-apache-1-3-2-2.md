---
description: Anweisungen zum Installieren und Konfigurieren von Sensor für Apache Server 1.3, Apache Server 2.0.42 oder höher oder Apache Server 2.2 unter Microsoft Windows Server 2000 oder höher.
title: Apache Server 1.3, 2, 2.2 oder 2.4 unter Windows Server 2000 oder höher
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3, 2, 2.2 oder 2.4 unter Windows Server 2000 oder höher{#apache-server-or-on-windows-server-or-later}

Anweisungen zum Installieren und Konfigurieren von Sensor für Apache Server 1.3, Apache Server 2.0.42 oder höher oder Apache Server 2.2 unter Microsoft Windows Server 2000 oder höher.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

* Apache Server 1.3
* Apache Server 2.0.42 oder höher
* Apache Server 2.2 unter Microsoft Windows Server 2000 oder höher

## Programmdateien installieren {#section-2f3e85083b4f4aa989a85997330e86ae}

Bevor Sie die Programmdateien installieren, müssen Sie festlegen, wo Sie die Datenträgerwarteschlange unterhalten möchten, da dort auch die Programmdateien installiert werden müssen.Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor.

Zum Installieren und Konfigurieren von Sensor müssen Sie die folgenden Schritte ausführen:

1. Erstellen Sie auf Ihrem Windows-Computer einen Ordner, in dem die Dateien des Sensor-Programms installiert werden sollen. Denken Sie daran, dass sich Ihre Disk-Warteschlange auch in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Platz verfügt, um eine Warteschlange von der benötigten Größe zu halten.

   ```
   C:\VisualSensor
   ```

1. Extrahieren Sie den Inhalt der Installationsdatei in den soeben erstellten Ordner. Während dieses Schritts installiert Sensor die folgenden Dateien:

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
   <td colname="col2"> Ereignis-Viewer-Nachrichten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> Das Sammlermodul. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Eine Excel-Tabellenkalkulationsdatei, die Architekten zum Konfigurieren eines kontrollierten Experiments verwenden können. Sensor verwendet diese Datei nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses anzeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Das Transmitterprogramm </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei des Sensors </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor läuft (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

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

## Hinzufügen des Sammlers zum Webserver {#section-c5b83ae4ebce430aa764f951e849b333}

Bei Apache-Servern ist der Collector ein dynamisches freigegebenes Objekt, das Sie in Ihren Webserverprozess laden.

Um den Collector Ihrem Webserver hinzuzufügen, müssen Sie die [!DNL httpd.conf] Datei wie unten beschrieben bearbeiten und den Webserver neu starten.

>[!NOTE]
>
>Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie in einem Texteditor die [!DNL httpd.conf]Datei für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie am Dateiende die folgenden zwei Zeilen hinzu:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen ist die Groß-/Kleinschreibung zu beachten. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver-Prozess neu (Sie müssen nicht den gesamten Servercomputer neu starten, sondern den Webserver-Prozess neu starten). Der Collector wird mit dem Webserver geladen und beginnt, Ereignisdaten zu sammeln und in die Disk-Warteschlange zu schreiben.

