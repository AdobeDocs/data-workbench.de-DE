---
description: Anweisungen zum Installieren und Konfigurieren des IBM HTTP-Servers unter IBM AIX 5.1 oder höher, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird.
title: IBM HTTP-Server unter AIX 5.1 oder höher
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
exl-id: 1d0c3aa9-de2d-45c0-b52d-b6e3fd4fd453
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1764'
ht-degree: 1%

---

# IBM HTTP-Server unter AIX 5.1 oder höher{#ibm-http-server-on-aix-or-later}

{{eol}}

Anweisungen zum Installieren und Konfigurieren des IBM HTTP-Servers unter IBM AIX 5.1 oder höher, der unter Microsoft Windows Server 2000 oder höher ausgeführt wird.

Die Programmdateien für Sensor werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei für den Sensor für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie mit den folgenden Verfahren beginnen.

Um Sensor zu installieren und zu konfigurieren, müssen Sie die folgenden allgemeinen Schritte ausführen:

## Installieren der Programmdateien {#section-2f3e85083b4f4aa989a85997330e86ae}

Erstellen Sie auf Ihrem IBM AIX-Server einen Ordner, in dem Sie die Programmdateien für Sensor installieren können. Beachten Sie, dass sich Ihre Datenträgerwarteschlange auch in diesem Verzeichnis befindet. Stellen Sie daher sicher, dass das gewählte Gerät über ausreichend Speicherplatz verfügt, um eine Warteschlange mit der benötigten Größe zu speichern.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   ```
   tar -zxf installationFilename
   ```

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

## Hinzufügen des Sammlers zur Webanwendung {#section-c5b83ae4ebce430aa764f951e849b333}

Bei WebSphere-Servern fungiert der Kollektor als Filter im Servlet-Container.

Um den Wächter zu Ihrer Web-App hinzuzufügen, öffnen Sie die Datei web.xml für den Webserver, dessen Ereignisse Sensor erfasst.

Wenn Sensor Daten für mehrere Webserver auf dem Servercomputer erfasst, müssen Sie für jeden Webserver das folgende Verfahren durchführen.

1. Öffnen Sie mithilfe eines Texteditors die Datei &quot;httpd.conf&quot;für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie Folgendes hinzu: `<filter>` und `<filter-mapping>` -Elemente in die Deskriptordatei ein. Wenn Sie txlogd.conf nicht im Verzeichnis /etc installiert haben, müssen Sie den richtigen Pfad zu dieser Datei im `<param-value>` -Element.

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

1. Starten Sie die Webanwendung neu. Der Kollektor wird mit der Anwendung geladen und beginnt mit der Erfassung von Ereignisdaten und dem Schreiben in die Datenträgerwarteschlange.

## Speicherort der Sammlungs- und freigegebenen Objektdateien deklarieren {#section-b9c298fa645f4670b2503647d967846f}

Bearbeiten Sie das Websphere-Startskript, um den Speicherort der Dateien J2EECollector.jar und libvisual_sciences.so zu deklarieren.

1. Öffnen Sie die Datei setupCmdLine.sh im Ordner Websphere /bin .
1. Fügen Sie nach der Zeile, die die Variable $WAS_CLASSPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Fügen Sie nach dem Fallblock, der die Variable $WAS_LIBPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Speichern Sie die Datei setupCmdLine.sh .

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

## Erfassen zusätzlicher Daten {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

Sensoren für alle Plattformen können alle Daten erfassen, die in den HTTP-Anforderungs- und Antwortheadern verfügbar sind.

Die Sensoren für die J2EE-Plattform bieten einen Mechanismus zum Erfassen von Daten, die auf anderen Plattformen nicht verfügbar sind. Der Kollektor für die J2EE-Plattform (J2EE Collector) befindet sich auf der Anwendungsebene, wodurch er sensible Daten erfassen kann, die nur für die Anwendung verfügbar sind und nicht über Seiten-Tagging oder in den Kopfzeilen verfügbar gemacht werden sollten.

>[!NOTE]
>
>Auch wenn die Daten durch Seiten-Tags und die Kopfzeilenänderung ausgeblendet werden können, stehen sie weiterhin denjenigen zur Verfügung, die den Quellcode einer Seite untersuchen oder die Kopfzeilen mithilfe von Browser-Plug-in-Tools betrachten.

Beispielsweise kann der J2EE-Sammler zur Erfassung von CPC-Daten (Cost per Click) für Links verwendet werden, die auf einer Seite angezeigt werden, sowie für vertrauliche Partnerinformationen auf einer Seite und viele andere Datenpunkte. Die J2EE-Umgebung erleichtert es Ihnen, Ihre WEBAPP zu ändern, um diese benutzerdefinierten Daten mithilfe unserer Sammlerklasse zu erfassen.

Wenn ein Sensor für die J2EE-Plattform eine Anforderung erhält, ruft er eine Sammlerklasse auf, die die Funktion appendToLog importiert. Die Funktion appendToLog hängt an die ursprüngliche Anfrage die in der Funktion appendToLog angegebenen Abfragezeichenfolgenparameter an. Dies führt zur URI der ursprünglichen Anfrage, die zusätzliche Name-Wert-Paare der Abfragezeichenfolge enthält, die den Namen und Werten der erfassten Daten entsprechen. Beispielsweise würde CPC=20 an die ursprüngliche Anfrage angehängt, wenn der Wert einer bestimmten Anzeigenplatzierung oder eines Clickthrough-Links 20 Cent beträgt. Insight Server verarbeitet diese Werte zur Analyse in den Datensatz. Ein weiterer Vorteil dieser Erfassungsmethodik besteht darin, dass sie die Erfassung zusätzlicher Daten ermöglicht, ohne zusätzliche Protokolleinträge zu erstellen, wie dies möglicherweise mithilfe von Methoden zum Taggen von Seiten möglich ist.

Weitere Informationen zur Verarbeitung finden Sie im Handbuch zur Datensatzkonfiguration .

So erfassen Sie zusätzliche Daten von einer Seite:

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
