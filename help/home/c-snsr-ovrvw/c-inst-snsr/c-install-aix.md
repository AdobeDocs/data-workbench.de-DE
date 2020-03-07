---
description: Anweisungen zum Installieren und Konfigurieren des IBM HTTP-Servers auf IBM AIX 5.1 oder höher, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird.
title: IBM HTTP Server unter AIX 5.1 oder höher
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IBM HTTP Server unter AIX 5.1 oder höher{#ibm-http-server-on-aix-or-later}

Anweisungen zum Installieren und Konfigurieren des IBM HTTP-Servers auf IBM AIX 5.1 oder höher, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird.

Die Programmdateien für Sensor werden in einer Installationsdatei verpackt, die Sie von der Adobe-Downloadseite erhalten. Wenn Sie noch nicht über die Sensor-Installationsdatei für Ihren jeweiligen Webserver verfügen, laden Sie diese herunter (oder rufen Sie sie von Ihrem Adobe-Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden Schritte auf hoher Ebene ausführen:

## Programmdateien installieren {#section-2f3e85083b4f4aa989a85997330e86ae}

Erstellen Sie auf Ihrem IBM AIX-Server einen Ordner, in dem die Dateien des Sensor-Programms installiert werden sollen. Denken Sie daran, dass sich Ihre Disk-Warteschlange auch in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Platz verfügt, um eine Warteschlange von der benötigten Größe zu halten.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   ```
   tar -zxf installationFilename
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

<table id="table_F4A46DBDE0874133B616235C32B6D9F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Standardberechtigungen </th> 
   <th colname="col3" class="entry"> chmod, Befehl </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> <p>chmod 711 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> chmod 711 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
 </tbody> 
</table>

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

## Hinzufügen des Sammlers zur Webanwendung {#section-c5b83ae4ebce430aa764f951e849b333}

Bei WebSphere-Servern fungiert der Collector als Filter im Servlet-Container.

Um den Collector zu Ihrer Web-App hinzuzufügen, öffnen Sie die Datei &quot;web.xml&quot;für den Webserver, dessen Ereignisse Sensor erfasst.

Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie in einem Texteditor die Datei &quot;httpd.conf&quot;für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie der Deskriptordatei die folgenden Elemente `<filter>` und `<filter-mapping>` Elemente hinzu. Wenn Sie txlogd.conf nicht im Ordner /etc installiert haben, müssen Sie den richtigen Pfad zu dieser Datei im `<param-value>` Element eingeben.

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

1. Starten Sie die Webanwendung neu. Der Collector wird mit der Anwendung geladen und beginnt mit der Erfassung der Ereignisdaten und dem Schreiben in die Disk-Warteschlange.

## Speicherort der Sammlungs- und freigegebenen Objektdateien deklarieren {#section-b9c298fa645f4670b2503647d967846f}

Bearbeiten Sie das Websphere-Startskript, um den Speicherort der Dateien J2EECollector.jar und libvisual_sciences.so anzugeben.

1. Öffnen Sie die Datei &quot;setupCmdLine.sh&quot;im Ordner &quot;WebSphere/bin&quot;.
1. Fügen Sie nach der Zeile, die die Variable $WAS_CLASSPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Fügen Sie nach dem Fallblock, der die Variable $WAS_LIBPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Speichern Sie die Datei &quot;setupCmdLine.sh&quot;.

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

## Erfassen zusätzlicher Daten {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

Sensoren für alle Plattformen können alle Daten erfassen, die in den HTTP-Anforderungs- und -Antwort-Headern verfügbar sind.

Die Sensoren für die J2EE-Plattform bieten einen Mechanismus zur Erfassung von Daten, die auf anderen Plattformen nicht verfügbar sind. Der Collector für die J2EE-Plattform (J2EE Collector) sitzt auf der Anwendungsebene, wodurch vertrauliche Daten gesammelt werden können, die nur für die Anwendung verfügbar sind und nicht über Seiten-Tagging oder in den Headern verfügbar sein sollten.

>[!NOTE]
>
>Die Daten können zwar durch Seiten-Tags und die Änderung der Kopfzeile ausgeblendet werden, stehen aber dennoch denjenigen zur Verfügung, die den Quellcode einer Seite prüfen oder die Kopfzeilen mithilfe der Browser-Plugin-Tools betrachten.

Der J2EE-Collector kann beispielsweise zur Erfassung von CPC-Daten (Cost per Click) für Links verwendet werden, die auf einer Seite angezeigt werden, sowie für sensible Partnerinformationen auf einer Seite und viele andere Datenpunkte. Die J2EE-Umgebung ermöglicht es Ihnen, Ihre WEBAPP zu ändern, um diese benutzerspezifischen Daten mit unserer Collector-Klasse zu erfassen.

Wenn ein Sensor für die J2EE-Plattform eine Anforderung empfängt, ruft er eine Collector-Klasse auf, die die Funktion appendToLog importiert. Die Funktion appendToLog hängt an die ursprüngliche Anforderung die in der Funktion appendToLog angegebenen Abfragezeichenfolgenparameter an. Dies ergibt den URI der ursprünglichen Anforderung, der zusätzliche Paare aus Name und Wert der Abfragezeichenfolge enthält, die den Namen und Werten der erfassten Daten entsprechen. Beispiel: CPC=20 wird an die ursprüngliche Anforderung angehängt, wenn der Wert einer bestimmten Anzeigenplatzierung oder eines Clickthrough-Links 20 Cent beträgt. Insight Server verarbeitet diese Werte zur Analyse in den Datensatz. Ein weiterer Vorteil dieser Erfassungsmethodik besteht darin, dass sie die Erfassung zusätzlicher Daten ohne Erstellung zusätzlicher Protokolleinträge ermöglicht, da diese möglicherweise mit Seitenmarkierungsmethoden erstellt werden.

Weitere Informationen zur Verarbeitung finden Sie im Handbuch zur Konfiguration von DataSet.

So erfassen Sie zusätzliche Daten von einer Seite:

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

