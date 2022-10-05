---
description: Anweisungen zum Installieren und Konfigurieren von Sensor für Apache Server 1.3, Apache Server 2.0.42 oder höher oder Apache Server 2.2, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird.
title: Apache-Server 1.3, 2, 2.2 oder 2.4 unter Windows Server 2000 oder höher
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
exl-id: d1bd0fc1-da5b-4183-8270-73c46195f724
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 1%

---

# Apache-Server 1.3, 2, 2.2 oder 2.4 unter Windows Server 2000 oder höher{#apache-server-or-on-windows-server-or-later}

{{eol}}

Anweisungen zum Installieren und Konfigurieren von Sensor für Apache Server 1.3, Apache Server 2.0.42 oder höher oder Apache Server 2.2, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

* Apache Server 1.3
* Apache Server 2.0.42 oder höher
* Apache Server 2.2, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird

## Installieren der Programmdateien {#section-2f3e85083b4f4aa989a85997330e86ae}

Vor der Installation der Programmdateien müssen Sie bestimmen, wo Sie die Festplattenwarteschlange unterhalten möchten, da dort auch die Programmdateien installiert werden müssen. Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte ausführen:

1. Erstellen Sie auf Ihrem Windows-Computer einen Ordner, in dem Sie die Programmdateien des Sensor installieren können. Beachten Sie, dass sich Ihre Datenträgerwarteschlange auch in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Speicherplatz verfügt, um eine Warteschlange mit der benötigten Größe zu speichern.

   ```
   C:\VisualSensor
   ```

1. Extrahieren Sie den Inhalt der Installationsdatei in das soeben erstellte Verzeichnis. Während dieses Schritts installiert Sensor die folgenden Dateien:

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
   <td colname="col2"> <p>Eine Excel-Tabellenkalkulationsdatei, mit der Architekten ein gesteuertes Experiment konfigurieren können. Sensor verwendet diese Datei nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses präsentiert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Das Senderprogramm </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für den Sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein gesteuertes Experiment konfigurieren. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies tun können). Sie können die Datei stattdessen an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen können, oder einfach die Datei aus dem Installationspaket extrahieren. Weitere Informationen zu kontrollierten Experimenten finden Sie im Leitfaden zu kontrollierten Experimenten mit Insight.

## Bearbeiten der Datei für die Sensor-Konfiguration {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

Bei Apache-Servern ist der Kollektor ein dynamisches gemeinsames Objekt, das Sie in Ihren Webserverprozess laden.

Um den Wächter zu Ihrem Webserver hinzuzufügen, müssen Sie die [!DNL httpd.conf] wie unten beschrieben und starten Sie Ihren Webserver neu.

>[!NOTE]
>
>Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie mithilfe eines Texteditors die [!DNL httpd.conf]Datei für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie die folgenden beiden Zeilen am Ende der Datei hinzu:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen wird zwischen Groß- und Kleinschreibung unterschieden. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver-Prozess neu (Sie müssen nicht den gesamten Server neu starten, sondern einfach den Webserver-Prozess neu starten). Der Kollektor wird mit dem Webserver geladen und fängt an, Ereignisdaten zu erfassen und in die Datenträgerwarteschlange zu schreiben.
