---
description: Anweisungen zum Installieren und Konfigurieren von Sensor für Sun Java System Application Server Standard Edition 7 unter Windows Server 2000 oder höher.
title: Sun Java-Server unter Windows Server 2000 oder höher
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---


# Sun Java-Server unter Windows Server 2000 oder höher{#sun-java-server-on-windows-server-or-later}

Anweisungen zum Installieren und Konfigurieren von Sensor für Sun Java System Application Server Standard Edition 7 unter Windows Server 2000 oder höher.

Die Programm-Dateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für den jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Sensor unterstützt die folgenden Server, die unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher ausgeführt werden:

Zum Installieren und Konfigurieren von Sensor müssen Sie die folgenden Schritte ausführen:

## Installieren der Programm-Dateien {#section-2f3e85083b4f4aa989a85997330e86ae}

Verfahren zum Extrahieren und Installieren der Programm-Dateien für Sensor auf dem Server.

1. Erstellen Sie auf Ihrem Netscape Enterprise-, iPlanet-, Sun ONE- oder Sun Java-Systemserver einen Ordner, in dem Sie die Sensor-Programm-Dateien installieren können. Denken Sie daran, dass sich Ihre Disk-Warteschlange in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Platz verfügt, um eine Warteschlange von der benötigten Größe zu halten.

   ```
   C:\VisualSensor
   ```

1. Extrahieren Sie den Inhalt der Installationsdatei in den soeben erstellten Ordner. Während dieses Schritts installiert Sensor die folgenden Dateien:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Zielgruppen-Verzeichnis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> Das Sammlerlastmodul. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Das Transmitter-Programm. </td> 
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

## Edit the Sensor Configuration File {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Die [!DNL txlogd.conf] Datei enthält die Konfigurationsparameter für Sensor.

Sie müssen diese Datei bearbeiten, um u. a. die Größe und den Speicherort der Disk-Warteschlangendatei, die Adresse des Insight-Servers und die ID anzugeben, die an die von diesem Sensor erzeugten Ereignis-Daten angehängt wird.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* **Erforderliche Parameter** sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* **Optionale Parameter** sind Einstellungen, die standardmäßig auf vordefinierte Werte (die Sie ändern können) oder optionale Funktionen angewendet werden.

**So bearbeiten Sie die Konfigurationsdatei des Sensors**

* Öffnen Sie die [!DNL /etc/txlogd.conf] Datei in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
* Speichern und schließen Sie die Datei.

**So bearbeiten Sie die Konfigurationsdatei des Sensors**

1. Öffnen Sie die [!DNL /etc/txlogd.conf] Datei in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
1. Speichern und schließen Sie die Datei.

## Beginn des Transmitters und Erstellen der Disk-Warteschlange {#section-55630de65f264274aefd771da2002852}

Nachdem Sie die Datei &quot;txlogd.conf&quot;konfiguriert haben, können Sie das Transmitter-Programm zum Beginn verwenden, es als Windows-Dienst registrieren und die Disk-Warteschlange erstellen.

1. Wählen Sie unter Windows im Menü &quot;Beginn&quot;Zubehör > Eingabeaufforderung.
1. Navigieren Sie im Fenster mit der Eingabeaufforderung zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

   ```
   txlog /regserver
   ```

   Dieser Befehl Beginn den Sender, erstellt die Disk-Warteschlange und registriert Sensor als Windows-Dienst.

1. Um zu bestätigen, dass der Transmitter ordnungsgemäß ausgeführt wird, klicken Sie auf Beginn > Systemsteuerung > Verwaltung > Dienste. Suchen Sie in der Dienst-Liste den Eintrag für Sensor und vergewissern Sie sich, dass dessen Status &quot;Started&quot;und der Starttyp &quot;Automatic&quot;lautet. Schließen Sie dann das Bedienfeld &quot;Dienste&quot;.
1. Um zu überprüfen, ob Transmitter während des Beginns Fehler auftraten, klicken Sie auf Beginn > Systemsteuerung > Verwaltung > Ereignis-Viewer, um den Ereignis-Viewer zu öffnen.

   1. Wählen Sie im linken Bereich des Ereignis-Viewer-Fensters das Anwendungsprotokoll aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Spalte &quot;Quelle&quot;.
   1. Wenn die Fehlermeldung &quot;Adobe&quot;angezeigt wird, klicken Sie bei gedrückter Dublette auf den Fehler, um das Fenster &quot;Ereignis-Eigenschaften&quot;anzuzeigen. Dieses Fenster enthält detaillierte Informationen zum Fehler.

1. Wenn Sie die Prüfung des Anwendungsprotokolls abgeschlossen haben, schließen Sie den Ereignis-Viewer.
1. Überprüfen Sie, ob der Sender die Disk-Warteschlange (Diskq2000.log) in dem Ordner erstellt hat, in dem Sie die Sensor-Programm-Dateien installiert haben, und ob diese die im Parameter QueueSize in der Datei txlogd.conf angegebene Größe hat.

   Wenn die Warteschlange nicht korrekt erstellt wurde:

   1. Überprüfen Sie die Datei &quot;txtlogd.conf&quot;und stellen Sie sicher, dass der Parameter QueueSize korrekt eingestellt ist.
   1. Vergewissern Sie sich, dass auf dem Gerät, auf dem Sie Sensor installiert haben, ausreichend Speicherplatz für eine Datei der im Parameter QueueSize angegebenen Größe zur Verfügung steht.
   1. Beenden Sie den Transmitter über das Bedienfeld &quot;Dienste&quot;in Windows.
   1. Löschen Sie die Warteschlangendatei.
   1. Sensor erneut als Windows-Dienst registrieren: Wählen Sie unter Windows im Menü Beginn die Option Zubehör > Eingabeaufforderung. Navigieren Sie im Fenster mit der Eingabeaufforderung zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

      ```
      txlog /regserver
      ```

Der Transmitter ist für einen kontinuierlichen Betrieb ausgelegt. Wenn Sie den Computer neu starten, wird der Transmitter automatisch neu gestartet. Wenn Sie den Transmitter manuell Beginn und anhalten müssen, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun.

## Startskript ändern {#section-19a38f27c9f44adf88f8910f5ed483a3}

Fügen Sie in der Datei init.conf (z. B. C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf) die folgenden Zeilen am Dateiende hinzu:

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

Fügen Sie in der Datei &quot;obj.conf&quot;(z. B. C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf) die folgenden Zeilen direkt unter der vorhandenen `<Object name="default">` Zeile hinzu:

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```

