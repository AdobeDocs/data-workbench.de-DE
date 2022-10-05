---
description: Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für Apache Jakarta Tomcat 4.1 oder höher unter Windows Server 2000 oder höher.
title: Tomcat-Server unter Windows Server 2000 oder höher
uuid: 58feec67-ffbb-4f25-8f22-3d109d464e9a
exl-id: 6f4f1592-2b7d-434a-b292-9333e170f851
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1199'
ht-degree: 1%

---

# Tomcat-Server unter Windows Server 2000 oder höher{#tomcat-server-on-windows-server-or-later}

{{eol}}

Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für Apache Jakarta Tomcat 4.1 oder höher unter Windows Server 2000 oder höher.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Zu den unterstützten J2EE-Implementierungen gehören:

* JBoss Server 4.0.5 oder höher, der auf Microsoft Windows Server 2000 oder höher ausgeführt wird.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte ausführen:

## Installieren der Programmdateien {#section-2f3e85083b4f4aa989a85997330e86ae}

Verfahren zum Extrahieren und Installieren der Programmdateien für Sensor.

1. Erstellen Sie auf Ihrem Tomcat-Server einen Ordner, in dem Sie die Programmdateien des Sensor installieren können. Beachten Sie, dass sich Ihre Datenträgerwarteschlange in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Speicherplatz verfügt, um eine Warteschlange der benötigten Größe zu speichern.

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
   <td colname="col1"> visual_sciences.dll </td> 
   <td colname="col2"> Das Wächter-Lademodul. </td> 
   <td colname="col3"> In jedem Verzeichnis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliotheken des Lademoduls des Sammlers </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> Das Transmitter-Programm. </td> 
   <td colname="col3"> In jedem Verzeichnis </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für Sensor. </td> 
   <td colname="col3"> In jedem Verzeichnis </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> In jedem Verzeichnis </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen [!DNL TestExperiment.xls]. Diese Tabelle ist ein Tool, mit dem Architekten ein gesteuertes Experiment konfigurieren. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies tun können). Sie können die Datei stattdessen an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen können, oder einfach die Datei aus dem Installationspaket extrahieren. Weitere Informationen zu kontrollierten Experimenten finden Sie im Leitfaden zu kontrollierten Experimenten mit Insight.

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

1. Um sicherzustellen, dass der Transmitter ordnungsgemäß ausgeführt wird, klicken Sie auf Start > Systemsteuerung > Verwaltung > Dienste.

   >[!NOTE]
   >
   >Diese Befehlssequenz variiert je nach verwendeter Windows-Version.

   1. Suchen Sie in der Dienstliste den Eintrag für Sensor und bestätigen Sie, dass sein Status Gestartet und sein Starttyp Automatisch lautet.
   1. Schließen Sie die Systemsteuerung &quot;Dienste&quot;.

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

## Hinzufügen des Sammlers zum Webserver {#section-c5b83ae4ebce430aa764f951e849b333}

Bei JBoss-Servern fungiert der Kollektor als Filter im Servlet-Container.

Um den Wächter zu Ihrem Webserver hinzuzufügen, müssen Sie die [!DNL web.xml] wie unten beschrieben und starten Sie Ihre Webanwendung neu.

1. Öffnen Sie mithilfe eines Texteditors die [!DNL web.xml] Datei für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie Folgendes hinzu: `<filter>` und `<filter-mapping>` -Elemente in die Deskriptordatei ein. Wenn Sie txlogd.conf nicht im Verzeichnis /etc installiert haben, müssen Sie den richtigen Pfad zu dieser Datei im `<param-value>` element:

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
   >Bei diesen Zeilen wird zwischen Groß- und Kleinschreibung unterschieden. Geben Sie sie genau so ein, wie sie oben angezeigt werden.

1. Starten Sie den Webserver-Prozess neu (Sie müssen nicht den gesamten Server neu starten, sondern einfach den Webserver-Prozess neu starten). Der Kollektor wird mit dem Webserver geladen und fängt an, Ereignisdaten zu erfassen und in die Datenträgerwarteschlange zu schreiben.

## Ändern des Pfads zur Java-Bibliothek {#section-0dae181ef8884f10a57f6cfda8500969}

Anweisungen zum Hinzufügen der Datei visual_sciences.dll zum Java-Bibliothekspfad von Tomcat.

1. Navigieren Sie auf Ihrem Windows-Server zum Installationsordner von Tomcat. (Tomcat > bin)
1. Führen Sie im Ordner &quot;bin&quot;Tomcat9w.exe (Common Daemon Service Manager) aus.

   Fügen Sie auf der Registerkarte Java unter Java-Optionen eine neue Zeile hinzu:

   ```
   -Djava.library.path=C:\Sensor directory
   ```

   Wo die [!DNL C:\Sensor] directory ist der Ordner, der [!DNL visual_sciences.dll] -Datei.

## Erfassen zusätzlicher Daten {#section-9483b663cbd0432daaca50c1089c7fca}

Mit der Funktion appendToLog() können Sie zusätzliche Messdaten aus J2EE-basierten Webanwendungen erfassen.

1. Fügen Sie oben auf der JSP-Seite, von der Sie Daten erfassen möchten, den folgenden Code hinzu:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %> 
   ```

1. Verwenden Sie die Methode appendToLog() des Collector-Objekts, um die gewünschten Name-Wert-Paare an die Abfragezeichenfolge der angeforderten .jsp-Seite anzuhängen. Im folgenden Beispiel werden &quot;A=1&quot;und &quot;B=2&quot;an die Abfragezeichenfolge der angeforderten .jsp-Seite für die Seite /index.jsp angehängt:

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

   Der resultierende Anfrage-URI lautet /index.jsp?A=1&amp;B=2.

1. Wiederholen Sie dieses Verfahren für jede JSP-Seite, von der Sie zusätzliche Daten erfassen möchten.
