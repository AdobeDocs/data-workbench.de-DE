---
description: Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für WebLogic Server 6.x oder höher unter Microsoft Windows Server 2000 oder höher.
title: WebLogic Server unter Windows Server 2000 oder höher
uuid: 80dbf544-bd09-4af8-bb05-4032eb49dd5d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# WebLogic Server unter Windows Server 2000 oder höher{#weblogic-server-on-windows-server-or-later}

Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für WebLogic Server 6.x oder höher unter Microsoft Windows Server 2000 oder höher.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

Zum Installieren und Konfigurieren von Sensor müssen Sie die folgenden Schritte ausführen:

## Programmdateien installieren {#section-2f3e85083b4f4aa989a85997330e86ae}

Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor.

1. Erstellen Sie auf Ihrem WebLogic Server einen Ordner, in dem die Dateien des Sensor-Programms installiert werden sollen. Denken Sie daran, dass sich Ihre Disk-Warteschlange in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Platz verfügt, um eine Warteschlange von der benötigten Größe zu halten.

   ```
   C:\VisualSensor
   ```

1. Extrahieren Sie den Inhalt der Installationsdatei in den soeben erstellten Ordner. Während dieses Schritts installiert Sensor die folgenden Dateien:

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
   <td colname="col1"> visual_sciences.dll </td> 
   <td colname="col2"> Das Sammlerlastmodul. </td> 
   <td colname="col3"> In jedem Verzeichnis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliotheken des Sammlerladungs-Moduls </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> Das Transmitterprogramm. </td> 
   <td colname="col3"> In einem beliebigen Verzeichnis </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für den Sensor. </td> 
   <td colname="col3"> In einem beliebigen Verzeichnis </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, mit dem das digitale Zertifikat validiert wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> In einem beliebigen Verzeichnis </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellenkalkulationsdatei mit dem Namen [!DNL TestExperiment.xls]. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor läuft (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

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

## Hinzufügen des Sammlers zum Webserver {#section-c5b83ae4ebce430aa764f951e849b333}

Bei JBoss-Servern fungiert der Collector als Filter im Servlet-Container.

Um den Collector Ihrem Webserver hinzuzufügen, müssen Sie die [!DNL web.xml] Datei wie unten beschrieben bearbeiten und die Webanwendung neu starten.

1. Öffnen Sie mit einem Texteditor die [!DNL web.xml] Datei für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie der Deskriptordatei die folgenden Elemente `<filter>` und `<filter-mapping>` Elemente hinzu. Wenn Sie txlogd.conf nicht im Ordner /etc installiert haben, müssen Sie den richtigen Pfad zu dieser Datei im `<param-value>` Element eingeben:

   ```
   <filter> 
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
   ```

   >[!NOTE]
   >
   >Bei diesen Zeilen ist die Groß-/Kleinschreibung zu beachten. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver-Prozess neu (Sie müssen nicht den gesamten Servercomputer neu starten, sondern den Webserver-Prozess neu starten). Der Collector wird mit dem Webserver geladen und beginnt, Ereignisdaten zu sammeln und in die Disk-Warteschlange zu schreiben.

## Startskript ändern {#section-0dae181ef8884f10a57f6cfda8500969}

Anweisungen zur Änderung des Startskripts.

Bearbeiten Sie im Skript, das zum Starten von WebLogic verwendet wird (z. B. C:\bea\user_projects\mydomain\startServer.cmd), die Zeile &quot;set JAVA_OPTIONS=&quot;, um die Definition java.library.path auf den Ordner mit der Datei visual_sciences.dll festzulegen.

```
set JAVA_OPTIONS=-Djava.library.path=C:\Sensor 
    directory
```

## Erfassen zusätzlicher Daten {#section-9483b663cbd0432daaca50c1089c7fca}

Mit der Funktion appendToLog() können Sie zusätzliche Messungsdaten aus J2EE-basierten Webanwendungen erfassen.

1. Fügen Sie oben auf der JSP-Seite, von der Sie Daten erfassen möchten, den folgenden Code hinzu:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %> 
   ```

1. Verwenden Sie die Methode appendToLog() des Collector-Objekts, um die gewünschten Name-Wert-Paare an die Abfragezeichenfolge der angeforderten JSP-Seite anzuhängen. Im folgenden Beispiel wird der Abfragezeichenfolge der angeforderten JSP-Seite für die Seite /index.jsp die Zeichenfolge &quot;A=1&quot;und &quot;B=2&quot;angefügt:

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html> 
   ```

   Die resultierende Anforderungs-URI lautet /index.jsp?A=1&amp;B=2.

1. Wiederholen Sie diesen Vorgang für jede JSP-Seite, von der Sie zusätzliche Daten erfassen möchten.

