---
description: Anweisungen zum Installieren und Konfigurieren von Sensor für Sun Java System Application Server Standard Edition 7 unter Windows Server 2000 oder höher.
title: Sun Java-Server unter Windows Server 2000 oder höher
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
exl-id: 33f24073-8eff-4bf6-8f83-7a122d1505d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---

# Sun Java-Server unter Windows Server 2000 oder höher{#sun-java-server-on-windows-server-or-later}

{{eol}}

Anweisungen zum Installieren und Konfigurieren von Sensor für Sun Java System Application Server Standard Edition 7 unter Windows Server 2000 oder höher.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Sensor unterstützt die folgenden Server, die unter RedHat Linux 7.x oder höher oder Sun Solaris SPARC 2.6 oder höher ausgeführt werden:

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte ausführen:

## Installieren der Programmdateien {#section-2f3e85083b4f4aa989a85997330e86ae}

Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor auf dem Server.

1. Erstellen Sie auf Ihrem Netscape Enterprise, iPlanet, Sun ONE oder Sun Java System Server einen Ordner, in dem Sie die Dateien des Sensor-Programms installieren können. Beachten Sie, dass sich Ihre Datenträgerwarteschlange in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Speicherplatz verfügt, um eine Warteschlange der benötigten Größe zu speichern.

   ```
   C:\VisualSensor
   ```

1. Extrahieren Sie den Inhalt der Installationsdatei in das soeben erstellte Verzeichnis. Während dieses Schritts installiert Sensor die folgenden Dateien:

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
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> Das Wächter-Lademodul. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
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

1. Wählen Sie unter Windows im Menü Start die Option Zubehör > Eingabeaufforderung aus.
1. Navigieren Sie im Eingabeaufforderungsfenster zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

   ```
   txlog /regserver
   ```

   Dieser Befehl startet den Transmitter, erstellt die Festplattenwarteschlange und registriert Sensor als Windows-Dienst.

1. Um sicherzustellen, dass der Transmitter ordnungsgemäß ausgeführt wird, klicken Sie auf Start > Systemsteuerung > Verwaltung > Dienste. Suchen Sie in der Dienstliste den Eintrag für Sensor und bestätigen Sie, dass sein Status Gestartet und sein Starttyp Automatisch lautet. Schließen Sie dann das Bedienfeld Dienste .
1. Um zu überprüfen, ob Transmitter beim Start Fehler erhalten hat, klicken Sie auf Start > Systemsteuerung > Verwaltung > Ereignis-Viewer , um die Ereignisanzeige zu öffnen.

   1. Wählen Sie im linken Bereich des Fensters Ereignis-Viewer das Protokoll Anwendungen aus.
   1. Suchen Sie im rechten Bereich nach Ereignissen mit &quot;Adobe&quot;in der Quellspalte.
   1. Doppelklicken Sie auf die Fehlermeldung &quot;Adobe&quot;, um das Fenster Ereigniseigenschaften anzuzeigen. In diesem Fenster erhalten Sie detaillierte Informationen zum Fehler.

1. Wenn Sie die Prüfung des Anwendungsprotokolls abgeschlossen haben, schließen Sie die Ereignisanzeige.
1. Stellen Sie sicher, dass der Transmitter die Festplattenwarteschlange (Diskq2000.log) in dem Verzeichnis erstellt hat, in dem Sie die Dateien des Sensor-Programms installiert haben, und dass es sich um die Größe handelt, die Sie im Parameter QueueSize in der Datei txlogd.conf angegeben haben.

   Wenn die Warteschlange nicht korrekt erstellt wurde:

   1. Überprüfen Sie die Datei txtlogd.conf und überprüfen Sie, ob der Parameter QueueSize richtig eingestellt ist.
   1. Vergewissern Sie sich, dass auf dem Gerät, auf dem Sie Sensor installiert haben, ausreichend Speicherplatz für eine Datei zur Verfügung steht, die der im Parameter QueueSize angegebenen Größe entspricht.
   1. Beenden Sie den Transmitter über das Bedienfeld Dienste in Windows.
   1. Löschen Sie die Warteschlangendatei.
   1. Registrieren Sie Sensor als Windows-Dienst erneut: Wählen Sie unter Windows im Menü Start die Option Zubehör > Eingabeaufforderung aus. Navigieren Sie im Eingabeaufforderungsfenster zum Ordner, in dem Sie Sensor installiert haben, und führen Sie den folgenden Befehl aus:

      ```
      txlog /regserver
      ```

Der Transmitter ist für eine kontinuierliche Ausführung ausgelegt. Wenn Sie den Computer neu starten, wird der Transmitter automatisch neu gestartet. Wenn Sie den Transmitter manuell starten und anhalten müssen, können Sie dies über die Systemsteuerung Dienste in Windows tun.

## Ändern des Startskripts {#section-19a38f27c9f44adf88f8910f5ed483a3}

Fügen Sie in der Datei init.conf (z. B. C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf) die folgenden Zeilen am Ende der Datei hinzu:

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

Fügen Sie in der Datei &quot;obj.conf&quot;(z. B. C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf) die folgenden Zeilen direkt unterhalb der vorhandenen hinzu `<Object name="default">` Linie:

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```
