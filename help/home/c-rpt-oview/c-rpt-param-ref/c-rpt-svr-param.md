---
description: Informationen zu den Parametern von Report Server.cfg.
title: Parameter für „Report Server.cfg“
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 2%

---

# Parameter für „Report Server.cfg“{#report-server-cfg-parameters}

Informationen zu den Parametern von Report Server.cfg.

Das Beispiel [!DNL Report Server.cfg], das unter [Konfigurieren der Verbindung zu Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) angezeigt wird, enthält standardmäßig nur die in der Datei [!DNL Report Server.cfg] enthaltenen Parameter.

Wenn Sie den Adobe License Server über einen Proxyserver kontaktieren, müssen Sie den Lizenzvektor und dessen Parameter zum Ordner [!DNL Report Server.cfg] hinzufügen. Im Folgenden finden Sie ein Beispiel für diesen Vektor und dessen Parameter, die Sie für Ihren Lizenzvektor verwenden können:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Die folgende Tabelle enthält Beschreibungen der [!DNL Report Server.cfg]-Dateiparameter:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel-Erweiterung </td> 
   <td colname="col2"> <p>Zu den unterstützten Excel-Erweiterungen gehören: </p> <p>Excel-Erweiterung = Zeichenfolge: <span class="filepath"> .xlsx </span> </p> <p>Excel-Erweiterung = Zeichenfolge: <span class="filepath"> .xls </span> (dies ist die Standardeinstellung) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schriftarten </td> 
   <td colname="col2"> <p>Optional. Vektor, der die Schriftarten auflistet, die <span class="keyword"> Report Server </span> zum Rendern von UTF8-basierten Unicode-Sonderzeichen verwenden sollte. Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schriftart sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht in der Datei <span class="filepath"> Report Server.cfg </span> enthalten ist, verwendet <span class="keyword"> Report Server </span> nur die Konsole "Lucida Sans", um Text anzuzeigen. </p> <p> <span class="keyword"> Report Server  </span> verwendet die erste Schriftart in der Liste, um alle Zeichen wiederzugeben, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Dieses Zeichen wird dann mit der zweiten Schriftart in der Liste gerendert. Wenn diese Schriftart das Zeichen nicht rendert, verwendet <span class="keyword"> Report Server </span> die dritte Schriftart in der Liste, um dieses Zeichen usw. zu rendern, bis es das Ende der Schriftartenliste erreicht. Wenn die richtige Schriftart nicht im Vektor aufgeführt ist, zeigt <span class="keyword"> Report Server </span> den hexadezimalen Wert für das Zeichen an. </p> <p> <p>Hinweis:  Nehmen Sie keine Änderungen an diesem Parameter vor, während <span class="keyword"> Report Server </span> ausgeführt wird. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma- </span> Einstellung für die Ausgabe der  <span class="filepath"> .png- </span> Datei. Der Standardwert lautet 1.6. </p> <p> <p>Hinweis:  Es wird von Adobe nicht empfohlen, diesen Wert zu ändern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lizenzierung </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter in diesem Vektor nur ändern, wenn Sie den Lizenzserver der Adobe über einen Proxyserver kontaktieren. </p> <p>Bereichs-ID für Parameter, die Sie festlegen, um den Lizenzserver der Adobe über einen Proxyserver zu kontaktieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxy-Servers, den <span class="keyword"> Report Server </span> verwenden muss, um auf den Lizenzserver der Adobe zuzugreifen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Kennwort </td> 
   <td colname="col2"> Optional. Das Kennwort, das mit dem Proxy-Benutzernamen </span> verknüpft ist.<span class="wintitle"> </span></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Port </td> 
   <td colname="col2"> Der Port des Proxyservers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Benutzername </td> 
   <td colname="col2"> Optional. Der Benutzername, der für den Zugriff auf den Proxyserver verwendet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Netzwerkstandort </td> 
   <td colname="col2"> Der Netzwerkspeicherort, den <span class="keyword"> Report Server </span> verwendet, um den allgemeinen Namen des Servers in eine IP-Adresse aufzulösen. Netzwerkspeicherorte werden in der Adressdatei definiert, die sich im Verzeichnis Adressen auf dem Data Workbench-Servercomputer befindet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server </td> 
   <td colname="col2"> <p>Bereichs-ID für Parameter, die Sie festlegen, um zu konfigurieren, welche Data Workbench-Servercomputer <span class="keyword"> Report Server </span> eine Verbindung zum Generieren von Berichten herstellen müssen. Dazu gehört eine Zahl, die angibt, wie viele Elemente in diesem Vektor aufgelistet sind. </p> <p>Fügen Sie für jeden Server einen serverInfo -Eintrag hinzu und füllen Sie die Parameter nach Bedarf aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> IP-Adresse des Data Workbench-Servercomputers, zu dem <span class="keyword"> Report Server </span> eine Verbindung herstellen muss, um Berichte zu erstellen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Der Name, den <span class="keyword"> Report Server </span> intern verwendet, um den Data Workbench-Server zu identifizieren. Dies ist einfach eine interne Bezeichnung, sodass Sie jeden beliebigen Namen verwenden können. Zur Konsistenz empfehlen wir die Verwendung des allgemeinen Namens, der im digitalen Zertifikat des Servers aufgeführt ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anschluss </td> 
   <td colname="col2"> Port, über den <span class="keyword"> Report Server </span> mit dem Data Workbench-Server kommuniziert. Bei sicheren Verbindungen ist dieser Wert normalerweise 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxy-Servers, den <span class="keyword"> Report Server </span> verwenden muss, um auf den Data Workbench-Server zuzugreifen. Dieser Parameter ist nur erforderlich, wenn ein Proxy-Server für die Verbindung mit Ihren Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Kennwort </td> 
   <td colname="col2"> Das Kennwort für den Proxyserver. Dieser Parameter ist nur erforderlich, wenn ein Proxy-Server für die Verbindung mit Ihren Data Workbench-Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Port </td> 
   <td colname="col2"> Der Port des Proxyservers. Der Standardwert lautet 8080. Dieser Parameter ist nur erforderlich, wenn ein Proxy-Server für die Verbindung mit Ihren Data Workbench-Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Benutzername </td> 
   <td colname="col2"> Der Benutzername für den Proxyserver. Dieser Parameter ist nur erforderlich, wenn ein Proxy-Server für die Verbindung mit Ihren Data Workbench-Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Client-Zertifikat </td> 
   <td colname="col2"> Name der SSL-Zertifikatdatei für den Computer <span class="keyword"> Report Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allgemeiner SSL-Server-Name </td> 
   <td colname="col2"> <span class="wintitle"> Allgemeiner Servername, der im digitalen Zertifikat des Data Workbench-Servers  </span> aufgeführt ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL verwenden </td> 
   <td colname="col2"> Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und <span class="keyword"> Report Server </span> verwendet wird. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Result Memory Limit (KB) </td> 
   <td colname="col2"> <p>Die Speicherkapazität (in KB), die Sie für Berichte und Warnhinweise zur Verfügung stellen möchten. Der Standardwert lautet 50000. </p> <p>Beim Ausführen von Berichten überprüft <span class="keyword"> Report Server </span> diesen Wert zuerst und prüft dann den Wert im Parameter "Maximale Slice Size". Wenn Sie diesen Parameter beispielsweise auf 50.000 und die maximale Slice-Größe auf 50 festlegen, führt <span class="keyword"> Report Server </span> nur 50 Arbeitsbereiche gleichzeitig aus, selbst wenn Speicherplatz für die Ausführung weiterer Arbeitsbereiche verfügbar ist. </p> <p> <p>Hinweis:  Diese Grenze sollte niemals den im Parameter Query Memory Limit des Data Workbench-Servers festgelegten Wert überschreiten und idealerweise etwas niedriger als der Parameter <span class="wintitle"> Query Memory Limit </span> sein, um anderen Benutzern, die möglicherweise gleichzeitig Berichte ausführen, einen gewissen Spielraum zu bieten. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maximale Slice-Größe </td> 
   <td colname="col2"> Die maximale Anzahl von Bericht-Arbeitsbereichen, die <span class="keyword"> Report Server </span> gleichzeitig ausführen kann. Der Standardwert lautet 50. Weitere Informationen dazu, wie <span class="keyword"> Report Server </span> diese Einstellung verwendet, finden Sie in der Parameterbeschreibung <span class="wintitle"> Result Memory Limit (KB) </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software aktualisieren </td> 
   <td colname="col2"> <p>Gibt an, ob die <span class="keyword"> </span>-Software des Berichtsservers vom Data Workbench-Server aktualisiert werden soll. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </p> <p>Im Folgenden finden Sie ein Beispiel für diesen Parameter, mit dem Sie ein Modell verwenden können: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGL-Hardware-Rendering verwenden </td> 
   <td colname="col2"> <p>Steuert, ob <span class="keyword"> Report Server </span> Hardware-Rendering (z. B. die Grafikkarte des Computers) verwendet, um Berichtausgabe zu generieren. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </p> <p>Dieser Parameter sollte nur bei Problemen mit Ihrer Grafikkarte auf false gesetzt werden. Wenn der Wert auf false gesetzt ist, versucht <span class="keyword"> Report Server </span> nicht, Hardware-Rendering zu verwenden, und verwendet standardmäßig Software-Rendering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Berichterstellung </td> 
   <td colname="col2"> Bereichs-ID für Parameter, die Sie zum Konfigurieren der Berichterstellung festlegen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abschlussmeldungsintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden), mit der <span class="keyword"> Report Server </span> Abschlussstatusmeldungen druckt, wenn Abfragen während der Berichterstellung oder Warnhinweiserstellung ausgeführt werden. Der Standardwert ist 120 Sekunden. </p> <p>Beispiel: Workspace-Abfragen sind zu 62,145672 % abgeschlossen. </p> <p>Abschlussmeldungen werden in <span class="filepath"> reportserver.log </span> geschrieben und mit dem Server synchronisiert. Diese Einstellung steuert die <span class="filepath"> status.txt </span> -Dateien, die für jeden Berichtssatz hin und her gesendet werden, sodass der prozentuale Abschluss mit Miniaturansichten angezeigt werden kann. Die Nachrichten werden immer dann gesendet, wenn ein Berichtssatz abgeschlossen ist oder das Intervall erreicht ist (je nachdem, was zuerst eintritt). Wenn Sie diesen Wert höher einstellen, wirkt sich dies nicht auf die Rate aus, mit der der Bericht in der Client-Oberfläche durch die Miniaturansichten generiert wird, sondern auf die Anzahl der Zwischennachrichten, die Sie sehen. Die Angabe eines niedrigen Werts kann dazu führen, dass das System große Zeit mit der Datensynchronisation verbringt, da die Daten von <span class="keyword"> Report Server </span> Server für alle DPUs und alle verbundenen Clients jedes Mal, wenn sich eine <span class="filepath"> status.txt </span> -Nachricht ändert, mit dem Profil synchronisiert werden. </p> <p>Das System sendet immer eine <span class="filepath"> status.txt </span>-Datei, wenn ein Berichtssatz abgeschlossen wird, unabhängig von der Einstellung dieses Konfigurationsparameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile </td> 
   <td colname="col2"> <p>Zahl, die angibt, wie viele Elemente in diesem Vektor aufgelistet sind. Fügen Sie für jedes Profil, für das Berichte erstellt werden sollen, einen <span class="wintitle"> ReportProfile </span> -Eintrag im Profilvektor hinzu und füllen Sie die Parameter Server und Profil aus. </p> <p> <span class="wintitle"> Server  </span> - Der Name, den  <span class="keyword"> Report Server intern zur Identifizierung des Data Workbench-Servers  </span> verwendet. Dieser Name muss der gebräuchliche Servername sein, der im SSL-Zertifikat des Data Workbench-Servers aufgeführt ist. </p> <p> <span class="wintitle"> Profil  </span> - Name des Profils, für das Berichte erstellt werden sollen. Dieser Name muss mit dem benannten Profil auf dem Data Workbench-Servercomputer übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler </td> 
   <td colname="col2"> <p>Die Adresse des SMTP-Servers, von dem Sie <span class="wintitle"> Fehler des Berichtservers </span> per E-Mail senden möchten. </p> <p>Beispiel: <span class="filepath"> mail.mycompany.com </span> </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehlerkennwort </td> 
   <td colname="col2"> <p>Das Kennwort für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für von gesendete Fehler </td> 
   <td colname="col2"> Die E-Mail-Adresse, von der Sie <span class="wintitle"> Fehler vom Berichtserver </span> senden möchten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für an gesendete Fehler </td> 
   <td colname="col2"> <p>Die E-Mail-Adresse(n), an die Warnhinweise gesendet werden. </p> <p>Beispiel: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Benutzernamen "Fehler" </td> 
   <td colname="col2"> <p>Der Benutzername für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Statusintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden), mit der <span class="wintitle"> Report Server </span> Statusinformationen generiert und an den Data Workbench-Server sendet, um in <span class="wintitle"> Detaillierter Status </span> angezeigt zu werden. </p> <p>Der Standardwert ist 120 Sekunden. Es wird nicht empfohlen, diesen Wert auf einen kleinen Wert festzulegen, z. B. zwei Minuten, da die Ausführung einer Berichtswarteschlange Stunden dauern kann. In diesem Fall können Sie eine Einstellung von 600 bis 1200 Sekunden in Erwägung ziehen. </p> <p>Weitere Informationen zu <span class="wintitle"> Detaillierter Status </span> finden Sie im Kapitel "Verwaltungsschnittstellen"des <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight-Benutzerhandbuchs </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aktualisierungsintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Minuten), mit der <span class="keyword"> Report Server </span> alle im Profilvektor aufgelisteten Profile für neue Berichte und Warnhinweise überwacht. Der Standardwert ist 10 Minuten. </p> <p>Die von Ihnen angegebene Uhrzeit wird auf alle aufgelisteten Profile aufgeteilt. Wenn Ihr Intervall beispielsweise auf 10 Minuten festgelegt ist und Sie zwei Profile überwachen, wird jedes Profil fünf Minuten lang überwacht. Wenn ein Profil überwacht wird, wenn ein neuer oder geänderter Bericht oder Warnhinweis im Profil gespeichert wird, steht der Bericht oder Warnhinweis sofort zur Generierung zur Verfügung. </p> <p>Wenn das <span class="wintitle"> Aktualisierungsintervall </span> so konfiguriert ist, dass mehr als ein Profil überwacht wird, ist es wichtig, dass diese Einstellung hoch genug ist, um alle Profile innerhalb der konfigurierten Zeit zu laden. In Systemen mit vielen konfigurierten großen Dimensionen, in denen es beispielsweise mehrere Minuten dauern kann, bis die anfängliche Datenverbindung mit allen Elementnamen abgerufen wird, muss diese Einstellung ausreichend lang sein, damit eine vollständige Synchronisation stattfinden kann. Andernfalls gibt das System einen Fehler bei der Profilsynchronisierung aus. </p> </td> 
  </tr> 
 </tbody> 
</table>
