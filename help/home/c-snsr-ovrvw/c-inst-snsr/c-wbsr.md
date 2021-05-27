---
description: Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für WebSphere 5.x unter AIX 5.1 oder höher.
title: WebSphere unter AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---

# WebSphere unter AIX{#websphere-on-aix}

Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für WebSphere 5.x unter AIX 5.1 oder höher.

Die Programmdateien für [!DNL Sensor] werden in einer Installationsdatei zusammengefasst, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei [!DNL Sensor] für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Adobe-Support-Mitarbeiter ab), bevor Sie mit den folgenden Verfahren beginnen.

>[!NOTE]
>
>[!DNL Sensor] für WebSphere-Server unterstützt keine gesteuerte Experimentierung. Weitere Informationen zu kontrollierten Experimenten finden Sie im *Handbuch zu Data Workbench-gesteuerten Experimenten.*

## Installieren Sie die Programmdateien {#section-86f69127278c41bc90b97b68bb40bc6e}

Verfahren zum Extrahieren und Installieren der Programmdateien für Sensorto auf dem Servercomputer.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Kopieren Sie die entpackten Programmdateien in die in der folgenden Tabelle angegebenen Verzeichnisse:

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Zielverzeichnis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> Kollektorlastmodul </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliotheken des Lademoduls des Sammlers </td> 
   <td colname="col3"> Verzeichnis "WebSphere /lib" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> Das Senderprogramm </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei für den Sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, das zum Überprüfen des digitalen Zertifikats verwendet wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein gesteuertes Experiment konfigurieren. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies tun können). Sie können die Datei stattdessen an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen können, oder einfach die Datei aus dem Installationspaket extrahieren. Weitere Informationen zu kontrollierten Experimenten finden Sie im Leitfaden zu kontrollierten Experimenten mit Insight.

**Berechtigungen für die Programmdateien**

Falsche Berechtigungen für die Programmdateien verursachen die meisten Probleme bei der Installation von Sensor.

Stellen Sie sicher, dass Sie die Berechtigungen genau wie in diesem Abschnitt beschrieben festlegen.

Standardmäßig haben die Programmdateien in der Tar-Datei die folgenden Berechtigungen. Abhängig davon, wie Ihr System konfiguriert ist, können diese Einstellungen beim Extrahieren der Dateien geändert (nicht maskiert) werden.

Um die Berechtigungen auf die empfohlenen Standardeinstellungen zurückzusetzen, verwenden Sie die folgenden chmod-Befehle.

>[!NOTE]
>
>Vergewissern Sie sich, dass die Verzeichnisse, in denen Sie die Dateien installiert haben, mindestens diese Zugriffsebene zulassen.

| Datei | Standardberechtigungen | chmod, Befehl |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw- rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

Wenn Sie andere Berechtigungen als die empfohlenen Standardberechtigungen verwenden möchten, lesen Sie die Informationen unter &quot;Berechtigungen für Sensor-UNIX-Dateien&quot;, um sicherzustellen, dass Sie wissen, wie diese Dateien verwendet werden.

## Bearbeiten Sie die Datei für die Sensor-Konfiguration {#section-283c8a92fa8841c1b6034e5f834ef4e7} .

Die Datei txlogd.conf enthält die Konfigurationsparameter für Sensor.

Sie müssen die Datei bearbeiten, um unter anderem die Größe der Festplattenwarteschlange, die Adresse des Insight Servers und die Kennung anzugeben, die an die von diesem Sensor erzeugten Daten angehängt werden soll.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* Erforderliche Parameter sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* Optionale Parameter sind Einstellungen, die standardmäßig vordefinierte Werte enthalten (die Sie ändern können) oder optionale Funktionen aktivieren.

**So bearbeiten Sie die Konfigurationsdatei**

1. Öffnen Sie die Datei /etc/txlogd.conf in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
1. Speichern und schließen Sie die Datei.

## Starten Sie den Transmitter und erstellen Sie die Festplattenwarteschlange {#section-63285a2328604f20a2cb31b3d5cb80e6}

Verfahren zum Erstellen der Festplattenwarteschlange, nachdem Sie die Datei txlogd.conf konfiguriert haben.

1. Wenn der Ordner, in dem sich die Warteschlange befindet, noch nicht vorhanden ist, erstellen Sie ihn. Stellen Sie sicher, dass der Ordner sowohl dem Collector-Modul als auch dem Transmitter-Programm Lese-/Schreibzugriff auf die Datei bietet.

1. Führen Sie auf dem Computer, auf dem Sensor installiert ist, den folgenden Befehl aus, um den Transmitter zu starten:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Die Option &quot;i&quot;in diesem Befehl startet den Transmitter im interaktiven Modus. Dieser Modus zeigt Transmitter-Nachrichten auf dem Bildschirm an und ermöglicht Ihnen auch die Interaktion mit dem Transmitter mithilfe von Tastaturbefehlen.
   * Die Option &quot;c&quot;weist den Sender an, die Datenträgerwarteschlange zu erstellen.
   * Die Option &quot;f&quot;gibt den Speicherort der Konfigurationsdatei an.

1. Stellen Sie sicher, dass der Transmitter die Festplattenwarteschlange an dem im Parameter QueueFile angegebenen Speicherort und der im Parameter QueueSize angegebenen Größe erstellt hat.
1. Wenn die Warteschlange nicht korrekt erstellt wurde, drücken Sie Strg+C, um den Transmitter zu beenden, und gehen Sie dann wie folgt vor:

   1. Überprüfen Sie die Datei txtlogd.conf und überprüfen Sie, ob die Parameter QueueFile und QueueSize richtig eingestellt sind.
   1. Überprüfen Sie, ob das Gerät, dem die Festplattenwarteschlange zugewiesen ist, betriebsbereit ist und über ausreichend Speicherplatz verfügt, um eine Datei mit der im Parameter QueueSize angegebenen Größe zu speichern.
   1. Nehmen Sie die notwendigen Korrekturen vor und wiederholen Sie diesen Vorgang.

## Fügen Sie den Kollektor zur Webanwendung {#section-d17297b1193f4e3cb150fb41f754ef12} hinzu.

Bei WebSphere-Servern fungiert der Kollektor als Filter im Servlet-Container.

Um den Kollektor zur Webanwendung hinzuzufügen, fügen Sie den Filter zum Bereitstellungsdeskriptor web.xml der Webanwendung hinzu und starten Sie die Webanwendung neu.

1. Öffnen Sie mithilfe eines Texteditors die Datei web.xml für den Webserver, dessen Ereignisse Sensor erfasst.
1. Fügen Sie die folgenden `<filter>`- und `<filter-mapping>`-Elemente zur Deskriptordatei hinzu. Wenn Sie txlogd.conf nicht im Verzeichnis /etc installiert haben, müssen Sie den richtigen Pfad zu dieser Datei im Element `<param-value>` eingeben.

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

## Deklarieren Sie den Speicherort der Sammlungs- und freigegebenen Objektdateien {#section-e641f08999d34a648aaee2111b69ca25}

Verfahren zum Bearbeiten des Websphere-Startskripts, um den Speicherort der Dateien J2EECollector.jar und libvisual_sciences.so zu deklarieren.

1. Öffnen Sie die Datei setupCmdLine.sh im Ordner Websphere /bin .
1. Fügen Sie nach der Zeile, die die Variable $WAS_CLASSPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Fügen Sie nach dem Fallblock, der die Variable $WAS_LIBPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Speichern Sie die Datei [!DNL setupCmdLine.sh].

## Testen Sie den Sensor {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}.

Verfahren zum Starten des Senders und zur Überprüfung, ob er erfolgreich eine Verbindung zum Insight Server herstellen und Ereignisdaten an ihn übertragen kann.

>[!NOTE]
>
>Um sicherzustellen, dass der Transmitter Ereignisdaten erfolgreich an den Insight Server senden kann, stellen Sie sicher, dass der Ziel-Insight Server installiert ist und ausgeführt wird, bevor Sie den folgenden Test starten.

1. Wenn der Transmitter noch nicht ausgeführt wird, starten Sie ihn mit dem folgenden Befehl neu:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öffnen Sie einen Browser (auf einem beliebigen Computer) und fordern Sie eine Seite vom Webserver an, auf dem Sensor ausgeführt wird (wählen Sie unbedingt eine Seite aus, die von Sensor überwacht wird).
1. Nachdem Sie die Anforderung ausgegeben haben, überprüfen Sie die Konsole des Senders auf Meldungen, die darauf hinweisen, dass Ereignisdaten an den Ziel-Insight Server gesendet werden.
1. Wenn Sensor Daten nicht erfolgreich übermittelt, überprüfen Sie Folgendes:

   * Der Insight Server-Zielserver wird ausgeführt.
   * Die Parameter ServerAddress und ServerPort werden in txtlogd.conf korrekt festgelegt. Wenn Sie &quot;ServerAddress&quot;mit einem Servernamen angegeben haben, versuchen Sie stattdessen, die zugehörige numerische IP-Adresse zu verwenden.
   * Der Wert des CertName-Parameters entspricht dem allgemeinen Namen, der im digitalen Zertifikat des Ziel-Insight-Servers exakt angezeigt wird.

## Fügen Sie den Transmitter zu Ihrem Systemstartskript hinzu {#section-23bb905100d04f018af93873dd4d5f68}

Informationen, die sicherstellen, dass der Transmitter automatisch geladen wird, wenn der Webserver-Computer neu gestartet wird.

Fügen Sie den folgenden Befehl (der den Transmitter startet) zu Ihrem Systemstartskript hinzu.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Dieser Befehl startet den Transmitter als Daemon. Vom Transmitter generierte Betriebs- und Fehlermeldungen werden in syslog geschrieben.

## Erfassen zusätzlicher Daten {#section-d5ccf8ee50914a87938e0c17480757e6}

Sensoren für alle Plattformen können alle Daten erfassen, die in den HTTP-Anforderungs- und Antwortheadern verfügbar sind.

Die Sensoren für die J2EE-Plattform bieten einen Mechanismus zum Erfassen von Daten, die auf anderen Plattformen nicht verfügbar sind. Der Kollektor für die J2EE-Plattform (J2EE Collector) befindet sich auf der Anwendungsebene, wodurch er sensible Daten erfassen kann, die nur für die Anwendung verfügbar sind und nicht über Seiten-Tagging oder in den Kopfzeilen verfügbar gemacht werden sollten.

>[!NOTE]
>
>Auch wenn die Daten durch Seiten-Tags und die Kopfzeilenänderung ausgeblendet werden können, stehen sie weiterhin denjenigen zur Verfügung, die den Quellcode einer Seite untersuchen oder die Kopfzeilen mithilfe von Browser-Plug-in-Tools betrachten.

Beispielsweise kann der J2EE-Sammler zur Erfassung von CPC-Daten (Cost per Click) für Links verwendet werden, die auf einer Seite angezeigt werden, sowie für vertrauliche Partnerinformationen auf einer Seite und viele andere Datenpunkte. Die J2EE-Umgebung erleichtert es Ihnen, Ihre WEBAPP zu ändern, um diese benutzerdefinierten Daten mithilfe unserer Sammlerklasse zu erfassen.

Wenn ein Sensor für die J2EE-Plattform eine Anforderung erhält, ruft er eine Sammlerklasse auf, die die Funktion appendToLog importiert. Die Funktion appendToLog hängt an die ursprüngliche Anfrage die in der Funktion appendToLog angegebenen Abfragezeichenfolgenparameter an. Dies führt zur URI der ursprünglichen Anfrage, die zusätzliche Name-Wert-Paare der Abfragezeichenfolge enthält, die den Namen und Werten der erfassten Daten entsprechen. Beispielsweise würde CPC=20 an die ursprüngliche Anfrage angehängt, wenn der Wert einer bestimmten Anzeigenplatzierung oder eines Clickthrough-Links 20 Cent beträgt. Insight Server verarbeitet diese Werte zur Analyse in den Datensatz. Ein weiterer Vorteil dieser Erfassungsmethodik besteht darin, dass sie die Erfassung zusätzlicher Daten ermöglicht, ohne zusätzliche Protokolleinträge zu erstellen, wie dies möglicherweise mithilfe von Methoden zum Taggen von Seiten möglich ist.

Weitere Informationen zur Verarbeitung finden Sie im *Handbuch zur Datensatzkonfiguration*.

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
