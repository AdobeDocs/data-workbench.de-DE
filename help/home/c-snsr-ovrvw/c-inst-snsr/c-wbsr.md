---
description: Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für WebSphere 5.x unter AIX 5.1 oder höher.
title: WebSphere unter AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---

# WebSphere unter AIX{#websphere-on-aix}

Detaillierte Anweisungen zum Installieren und Konfigurieren von Sensor für WebSphere 5.x unter AIX 5.1 oder höher.

Die Programm-Dateien für [!DNL Sensor] werden in einer Installationsdatei gepackt, die Sie von der Adobe-Download-Site erhalten. Wenn Sie noch nicht über die Installationsdatei [!DNL Sensor] für Ihren Webserver verfügen, laden Sie sie herunter (oder rufen Sie sie von Ihrem Kundenbetreuer ab), bevor Sie die folgenden Schritte durchführen.

>[!NOTE]
>
>Das [!DNL Sensor] für WebSphere-Server unterstützt keine kontrollierte Experimentierung. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Handbuch *Data Workbench Controlled Experiments.*

## Installieren Sie die Programm-Dateien {#section-86f69127278c41bc90b97b68bb40bc6e}

Verfahren zum Extrahieren und Installieren der Programm-Dateien von Sensorto Server Machine.

1. Melden Sie sich als Root-Benutzer oder als Benutzer mit Root-Berechtigung an.
1. Dekomprimieren und entpacken Sie die Installationsdatei mit dem folgenden Befehl:

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Kopieren Sie die entpackten Programm-Dateien in die in der folgenden Tabelle angegebenen Ordner:

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datei </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Zielgruppen-Verzeichnis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> Sammlerlastmodul </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliotheken des Sammlerladungs-Moduls </td> 
   <td colname="col3"> WebSphere/lib-Ordner </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> Transmitter-Programm </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Die Konfigurationsdatei des Sensors </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Das Zertifikat, mit dem das digitale Zertifikat validiert wird, das Insight Server während des Verbindungsprozesses präsentiert </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Das Installationspaket enthält eine Tabellendatei mit dem Namen TestExperiment.xls. Diese Tabelle ist ein Tool, mit dem Architekten ein kontrolliertes Experiment konfigurieren können. Sensor selbst verwendet diese Datei nicht, daher ist es nicht notwendig, die Datei auf dem Computer zu installieren, auf dem Sensor ausgeführt wird (obwohl Sie dies auch tun können). Sie sollten stattdessen die Datei an einen Speicherort kopieren, an dem Ihre Architekten darauf zugreifen oder die Datei nach Bedarf einfach aus dem Installationspaket extrahieren können. Weitere Informationen zum kontrollierten Experimentieren finden Sie im Insight Controlled Experiments Guide.

**Berechtigungen in den Programm-Dateien**

Falsche Berechtigungen für die Programm-Dateien verursachen die meisten Probleme bei der Installation von Sensor.

Bitte stellen Sie sicher, dass Sie die Berechtigungen genau wie in diesem Abschnitt angegeben einstellen.

Standardmäßig haben die Programm-Dateien in der tar-Datei die folgenden Berechtigungen. Je nachdem, wie Ihr System konfiguriert ist, können diese Einstellungen beim Extrahieren der Dateien geändert (nicht maskiert) werden.

Um die Berechtigungen auf die empfohlenen Standardeinstellungen zurückzusetzen, verwenden Sie die folgenden chmod-Befehle.

>[!NOTE]
>
>Vergewissern Sie sich, dass die Ordner, in denen Sie die Dateien installiert haben, mindestens diese Zugriffsebene zulassen.

| Datei | Standardberechtigungen | chmod, Befehl |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw- rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

Wenn Sie andere als die empfohlenen Standardberechtigungen verwenden möchten, lesen Sie die Informationen in den Sensor-UNIX-Dateiberechtigungen, um sicherzustellen, dass Sie wissen, wie diese Dateien verwendet werden.

## Bearbeiten Sie die Datei für die Sensorkonfiguration {#section-283c8a92fa8841c1b6034e5f834ef4e7}

Die Datei &quot;txlogd.conf&quot;enthält die Konfigurationsparameter für Sensor.

Sie müssen die Datei bearbeiten, um unter anderem die Größe der Disk-Warteschlange, die Adresse des Insight-Servers und die ID anzugeben, die an die von diesem Sensor erzeugten Daten angehängt wird.

Die Konfigurationsdatei enthält die erforderlichen Parameter und optionalen Parameter.

* Erforderliche Parameter sind Einstellungen, die Sie bei der Installation von Sensor angeben müssen. Ohne diese Einstellungen wird Sensor nicht erfolgreich ausgeführt.
* Optionale Parameter sind Einstellungen, die standardmäßig auf vordefinierte Werte (die Sie ändern können) oder optionale Funktionen angewendet werden.

**So bearbeiten Sie die Konfigurationsdatei**

1. Öffnen Sie die Datei /etc/txlogd.conf in einem Texteditor und legen Sie die erforderlichen Parameter sowie die gewünschten optionalen Parameter fest.
1. Speichern und schließen Sie die Datei.

## Beginn des Transmitters und Erstellen der Disk-Warteschlange {#section-63285a2328604f20a2cb31b3d5cb80e6}

Verfahren zum Erstellen der Disk-Warteschlange, nachdem Sie die Datei &quot;txlogd.conf&quot;konfiguriert haben.

1. Wenn der Ordner, in dem sich die Disk-Warteschlange befindet, noch nicht vorhanden ist, erstellen Sie ihn. Stellen Sie sicher, dass der Ordner sowohl dem Sammlermodul als auch dem Transmitter-Programm Lese-/Schreibzugriff auf die Datei bietet.

1. Führen Sie auf dem Computer, auf dem Sensor installiert ist, den folgenden Befehl aus, um den Sender Beginn:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Die Option &quot;i&quot;in diesem Befehl Beginn den Transmitter im interaktiven Modus. Dieser Modus zeigt Transmittermeldungen auf dem Bildschirm an und ermöglicht Ihnen auch die Interaktion mit dem Transmitter mithilfe von Tastaturbefehlen.
   * Die Option &quot;c&quot;weist den Sender an, die Datenträgerwarteschlange zu erstellen.
   * Die Option &quot;f&quot;gibt den Speicherort der Konfigurationsdatei an.

1. Überprüfen Sie, ob der Transmitter die Disk-Warteschlange an dem im Parameter QueueFile angegebenen Speicherort und in der im Parameter QueueSize angegebenen Größe erstellt hat.
1. Wenn die Warteschlange nicht korrekt erstellt wurde, drücken Sie Strg+C, um den Transmitter zu beenden, und führen Sie dann die folgenden Schritte aus:

   1. Überprüfen Sie die Datei &quot;txtlogd.conf&quot;und stellen Sie sicher, dass die Parameter &quot;QueueFile&quot;und &quot;QueueSize&quot;korrekt eingestellt sind.
   1. Vergewissern Sie sich, dass das Gerät, dem die Disk-Warteschlange zugewiesen ist, betriebsbereit ist und über ausreichend Speicherplatz verfügt, um eine Datei der im Parameter QueueSize angegebenen Größe aufzunehmen.
   1. Nehmen Sie alle erforderlichen Korrekturen vor und wiederholen Sie diesen Vorgang.

## hinzufügen Sie den Sammler auf die Webanwendung {#section-d17297b1193f4e3cb150fb41f754ef12}

Bei WebSphere-Servern fungiert der Collector als Filter im Servlet-Container.

Um den Collector der Webanwendung hinzuzufügen, fügen Sie den Filter dem Web.xml-Bereitstellungsdeskriptor der Webanwendung hinzu und starten Sie die Webanwendung neu.

1. Öffnen Sie in einem Texteditor die Datei &quot;web.xml&quot;für den Webserver, dessen Ereignisse Sensor erfasst.
1. hinzufügen Sie die folgenden `<filter>`- und `<filter-mapping>`-Elemente in die Deskriptordatei ein. Wenn Sie txlogd.conf nicht im Ordner /etc installiert haben, müssen Sie den richtigen Pfad zu dieser Datei im Element `<param-value>` eingeben.

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

1. Starten Sie die Webanwendung neu. Der Collector wird mit der Anwendung geladen und beginnt mit der Erfassung von Ereignis-Daten und dem Schreiben in die Disk-Warteschlange.

## Speicherort der Sammlungs- und freigegebenen Objektdateien {#section-e641f08999d34a648aaee2111b69ca25} deklarieren

Verfahren zum Bearbeiten des Websphere-Startskripts, um den Speicherort der Dateien J2EECollector.jar und libvisual_sciences.so zu deklarieren.

1. Öffnen Sie die Datei &quot;setupCmdLine.sh&quot;im Ordner &quot;WebSphere/bin&quot;.
1. Fügen Sie nach der Zeile, die die Variable $WAS_CLASSPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Fügen Sie nach dem Fallblock, der die Variable $WAS_LIBPATH definiert, die folgende Zeile hinzu:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Speichern Sie die Datei [!DNL setupCmdLine.sh].

## Sensor {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5} testen

Verfahren zum Beginn des Senders und zur Überprüfung, ob er erfolgreich eine Verbindung zum Insight-Server herstellen und Ereignis-Daten an ihn übertragen kann.

>[!NOTE]
>
>Um zu überprüfen, ob der Transmitter erfolgreich Ereignis-Daten an den Insight-Server senden kann, stellen Sie sicher, dass die Zielgruppe Insight Server installiert und ausgeführt wird, bevor Sie den folgenden Test starten.

1. Wenn der Transmitter noch nicht ausgeführt wird, starten Sie ihn mit dem folgenden Befehl neu:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öffnen Sie einen Browser (auf einem beliebigen Computer) und fordern Sie eine Seite vom Webserver an, auf dem Sensor ausgeführt wird (wählen Sie unbedingt eine Seite aus, die von Sensor überwacht wird).
1. Nachdem Sie die Anforderung gesendet haben, überprüfen Sie die Konsole des Senders auf Meldungen, die darauf hinweisen, dass Ereignis-Daten an die Zielgruppe Insight Server gesendet werden.
1. Wenn Sensor die Daten nicht erfolgreich übermittelt, überprüfen Sie, ob:

   * Der Zielgruppe Insight Server wird ausgeführt.
   * Die Parameter ServerAddress und ServerPort werden in txtlogd.conf korrekt eingestellt. Wenn Sie &quot;ServerAddress&quot;unter einem Servernamen angegeben haben, versuchen Sie stattdessen, die zugehörige numerische IP-Adresse zu verwenden.
   * Der Wert des CertName-Parameters entspricht dem allgemeinen Namen, der im digitalen Zertifikat der Zielgruppe Insight Server exakt angegeben ist.

## hinzufügen Sie den Transmitter an Ihr Systemstartskript {#section-23bb905100d04f018af93873dd4d5f68}

Informationen, die sicherstellen, dass der Transmitter beim Neustart des Webservercomputers automatisch geladen wird.

hinzufügen Sie den folgenden Befehl (der den Transmitter startet) an Ihr Systemstartskript.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Dieser Befehl Beginn den Sender als Daemon. Die vom Sender erzeugten Betriebs- und Fehlermeldungen werden in syslog geschrieben.

## Erfassen zusätzlicher Daten {#section-d5ccf8ee50914a87938e0c17480757e6}

Sensoren für alle Plattformen können alle Daten erfassen, die in den HTTP-Anforderungs- und -Antwort-Headern verfügbar sind.

Die Sensoren für die J2EE-Plattform bieten einen Mechanismus zur Erfassung von Daten, die auf anderen Plattformen nicht verfügbar sind. Der Collector für die J2EE-Plattform (J2EE Collector) sitzt auf der Anwendungsebene, wodurch vertrauliche Daten gesammelt werden können, die nur für die Anwendung verfügbar sind und nicht über Seiten-Tagging oder in den Headern verfügbar sein sollten.

>[!NOTE]
>
>Die Daten können zwar durch Seiten-Tags und die Änderung der Kopfzeile ausgeblendet werden, stehen aber dennoch denjenigen zur Verfügung, die den Quellcode einer Seite prüfen oder die Kopfzeilen mithilfe der Browser-Plugin-Tools betrachten.

Der J2EE-Collector kann beispielsweise zur Erfassung von CPC-Daten (Cost per Click) für Links verwendet werden, die auf einer Seite angezeigt werden, sowie für sensible Partnerinformationen auf einer Seite und viele andere Datenpunkte. Mit der J2EE-Umgebung können Sie Ihre WEBAPP so ändern, dass diese benutzerspezifischen Daten mit unserer Collector-Klasse erfasst werden.

Wenn ein Sensor für die J2EE-Plattform eine Anforderung empfängt, ruft er eine Collector-Klasse auf, die die Funktion appendToLog importiert. Die Funktion appendToLog hängt an die ursprüngliche Anforderung die in der Funktion appendToLog angegebenen Zeichenfolgenparameter der Abfrage an. Dies führt dazu, dass der URI der ursprünglichen Anforderung zusätzliche Abfragen-Zeichenfolgennamenpaare enthält, die den Namen und Werten der erfassten Daten entsprechen. Beispiel: CPC=20 wird an die ursprüngliche Anforderung angehängt, wenn der Wert einer bestimmten Anzeigenplatzierung oder eines Clickthrough-Links 20 Cent beträgt. Insight Server verarbeitet diese Werte zur Analyse in den Datensatz. Ein weiterer Vorteil dieser Erfassungsmethodik besteht darin, dass sie die Erfassung zusätzlicher Daten ohne Erstellung zusätzlicher Protokolleinträge ermöglicht, da diese möglicherweise mit Seitenmarkierungsmethoden erstellt werden.

Weitere Informationen zur Verarbeitung finden Sie im Handbuch *Konfiguration von Datasets*.

1. hinzufügen Sie den folgenden Code oben auf der JSP-Seite, von der Sie Daten erfassen möchten:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Verwenden Sie die Methode appendToLog() des Collector-Objekts, um die gewünschten Name-Wert-Paare an die Abfrage-Zeichenfolge der angeforderten JSP-Seite anzuhängen. Im folgenden Beispiel werden die Abfragen &quot;A=1&quot;und &quot;B=2&quot;an die Zeichenfolge der angeforderten JSP-Seite für die Seite /index.jsp angehängt:

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
