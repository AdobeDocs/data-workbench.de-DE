---
description: Informationen zu den Parametern Report Server.cfg.
title: Parameter für „Report Server.cfg“
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 2%

---

# Parameter für „Report Server.cfg“{#report-server-cfg-parameters}

Informationen zu den Parametern Report Server.cfg.

Das Beispiel [!DNL Report Server.cfg], das unter [Verbindung zu Insight Server konfigurieren](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) angezeigt wird, enthält standardmäßig nur die Parameter, die in der Datei [!DNL Report Server.cfg] enthalten sind.

Wenn Sie den Adobe License Server über einen Proxyserver kontaktieren, müssen Sie den Lizenzvektor und dessen Parameter dem [!DNL Report Server.cfg] hinzufügen. Im Folgenden finden Sie ein Beispiel für diesen Vektor und seine Parameter, mit denen Sie ein Modell für Ihren Licensing-Vektor verwenden können:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Die folgende Tabelle enthält Beschreibungen der Dateiparameter [!DNL Report Server.cfg]:

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
   <td colname="col2"> <p>Zu den unterstützten Excel-Erweiterungen gehören: </p> <p>Excel Extension = Zeichenfolge: <span class="filepath"> .xlsx </span> </p> <p>Excel Extension = Zeichenfolge: <span class="filepath"> .xls </span> (dies ist die Standardeinstellung) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schriftarten </td> 
   <td colname="col2"> <p>Optional. Vector listet die Schriften auf, die <span class="keyword"> Report Server </span> zum Rendern von UTF8-basierten Unicode-Sonderzeichen verwenden sollten. Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schrift sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht in der Datei <span class="filepath"> Report Server.cfg </span> enthalten ist, verwendet <span class="keyword"> Report Server </span> nur die Lucida Sans-Konsole, um Text anzuzeigen. </p> <p> <span class="keyword"> Report Server  </span> verwendet die erste Schrift in der Liste, um alle Zeichen wiederzugeben, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Anschließend wird das Zeichen mit der zweiten Schrift in der Liste gerendert. Wenn diese Schrift das Zeichen nicht wiedergibt, verwendet <span class="keyword"> Report Server </span> die dritte Schrift in der Liste, um dieses Zeichen usw. darzustellen, bis es das Ende der Schrift-Liste erreicht. Wenn die richtige Schrift nicht im Vektor aufgeführt ist, zeigt <span class="keyword"> Report Server </span> den Hexadezimalwert für das Zeichen an. </p> <p> <p>Hinweis:  Nehmen Sie keine Änderungen an diesem Parameter vor, während <span class="keyword"> Report Server </span> ausgeführt wird. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma- </span> Einstellung für  <span class="filepath"> .png- </span> Dateiausgabe. Der Standardwert lautet 1.6. </p> <p> <p>Hinweis:  Es wird nicht empfohlen, diesen Wert zu ändern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lizenzierung </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter in diesem Vektor nur ändern, wenn Sie den Lizenzserver der Adobe über einen Proxyserver kontaktieren. </p> <p>Abschnittskennung für Parameter, die Sie festlegen, um den Lizenzserver der Adobe über einen Proxyserver zu kontaktieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxyservers, der für den Zugriff auf den Lizenzserver der Adobe verwendet werden muss.<span class="keyword"></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Kennwort </td> 
   <td colname="col2"> Optional. Das mit dem Proxy-Benutzernamen </span> verknüpfte Kennwort.<span class="wintitle"> </span></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyanschluss </td> 
   <td colname="col2"> Der Anschluss des Proxyservers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Benutzername </td> 
   <td colname="col2"> Optional. Der Benutzername, mit dem auf den Proxyserver zugegriffen wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Netzwerkspeicherort </td> 
   <td colname="col2"> Der Netzwerkspeicherort, der von <span class="keyword"> Report Server </span> verwendet wird, um den gemeinsamen Namen des Servers in eine IP-Adresse aufzulösen. Netzwerkspeicherorte werden in der Adressdatei definiert, die sich im Adressverzeichnis des Datenbasis-Servercomputers befindet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server </td> 
   <td colname="col2"> <p>Abschnittskennung für Parameter, die Sie festlegen, um zu konfigurieren, welche Data Workbench-Servercomputer <span class="keyword"> Report Server </span> eine Verbindung herstellen müssen, um Berichte zu erstellen. Dazu gehört eine Zahl, die angibt, wie viele Elemente in diesem Vektor aufgelistet sind. </p> <p>Fügen Sie für jeden Server einen "serverInfo"-Eintrag hinzu und füllen Sie die Parameter nach Bedarf aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> IP-Adresse des Data Workbench-Servercomputers, zu dem <span class="keyword"> Report Server </span> eine Verbindung herstellen muss, um Berichte zu erstellen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Der Name, den <span class="keyword"> Report Server </span> intern zur Identifizierung des Data Workbench-Servers verwendet. Dies ist einfach eine interne Bezeichnung, sodass Sie jeden beliebigen Namen verwenden können. Aus Gründen der Konsistenz sollten Sie den im digitalen Zertifikat des Servers angegebenen gemeinsamen Namen verwenden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anschluss </td> 
   <td colname="col2"> Anschluss, über den <span class="keyword"> Report Server </span> mit dem Data Workbench-Server kommuniziert. Bei sicheren Verbindungen ist dieser Wert in der Regel 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxyservers, die <span class="keyword"> Report Server </span> verwenden muss, um auf den Data Workbench-Server zuzugreifen. Dieser Parameter ist nur erforderlich, wenn ein Proxyserver für die Verbindung mit Ihren Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Kennwort </td> 
   <td colname="col2"> Das Kennwort für den Proxyserver. Dieser Parameter ist nur erforderlich, wenn ein Proxyserver für die Verbindung mit den Datenbasis-Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyanschluss </td> 
   <td colname="col2"> Der Anschluss des Proxyservers. Der Standardwert lautet 8080. Dieser Parameter ist nur erforderlich, wenn ein Proxyserver für die Verbindung mit den Datenbasis-Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Benutzername </td> 
   <td colname="col2"> Der Benutzername für den Proxyserver. Dieser Parameter ist nur erforderlich, wenn ein Proxyserver für die Verbindung mit den Datenbasis-Servercomputern erforderlich ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Client-Zertifikat </td> 
   <td colname="col2"> Name der SSL-Zertifikatdatei für den Computer <span class="keyword"> Report Server </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Server - Allgemeiner Name </td> 
   <td colname="col2"> <span class="wintitle"> Server Common Name  </span> aufgelistet im digitalen Zertifikat des Data Workbench-Servers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL verwenden </td> 
   <td colname="col2"> Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und dem <span class="keyword"> Report Server </span> verwendet wird. Die Optionen sind "true"oder "false". Der Standardwert ist true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maximaler Arbeitsspeicher (KB) </td> 
   <td colname="col2"> <p>Der Arbeitsspeicher (in KB), den Sie für Berichte und Warnungen zur Verfügung stellen möchten. Der Standardwert lautet 50000. </p> <p>Bei der Ausführung von Berichten überprüft <span class="keyword"> Report Server </span> diesen Wert zuerst und prüft dann den Wert im Parameter "Maximum Slice Size". Wenn Sie diesen Parameter z. B. auf 50.000 und die maximale Slice-Größe auf 50 festlegen, werden von <span class="keyword"> Report Server </span> nur 50 Arbeitsflächen gleichzeitig ausgeführt, auch wenn genügend Platz zum Ausführen weiterer Arbeitsflächen vorhanden ist. </p> <p> <p>Hinweis:  Dieser Grenzwert sollte niemals den im Abfrage Memory Limit-Parameter des Data Workbench-Servers festgelegten Wert überschreiten und sollte idealerweise ein wenig niedriger als der Wert <span class="wintitle"> für die Speicherkapazität der Abfrage </span> eingestellt werden, um anderen Benutzern, die gleichzeitig Berichte ausführen, Spielraum zu bieten. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max. Slice-Größe </td> 
   <td colname="col2"> Die maximale Anzahl von Report Workspaces, die <span class="keyword"> Report Server </span> gleichzeitig ausführen können. Der Standardwert lautet 50. Weitere Informationen dazu, wie <span class="keyword"> Report Server </span> diese Einstellung verwendet, finden Sie in der Parameterbeschreibung <span class="wintitle"> Result Memory Limit (KB) </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software aktualisieren </td> 
   <td colname="col2"> <p>Gibt an, ob die <span class="keyword"> Report Server-Software </span> vom Data Workbench-Server aktualisiert werden soll. Die Optionen sind "true"oder "false". Der Standardwert ist true. </p> <p>Im Folgenden finden Sie ein Beispiel für diesen Parameter, mit dem Sie ein Modell verwenden können: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGL-Hardware-Rendering verwenden </td> 
   <td colname="col2"> <p>Steuert, ob <span class="keyword"> Report Server </span> Hardware-Rendering (z. B. die Grafikkarte des Computers) verwendet wird, um die Berichtausgabe zu erzeugen. Die Optionen sind "true"oder "false". Der Standardwert ist true. </p> <p>Dieser Parameter sollte nur dann auf "false"gesetzt werden, wenn Probleme mit der Grafikkarte auftreten. Bei Festlegung auf "false"versucht <span class="keyword"> Report Server </span> nicht, das Hardware-Rendering zu verwenden, und verwendet standardmäßig das Software-Rendering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Berichterstellung </td> 
   <td colname="col2"> Abschnittskennung für Parameter, die Sie zum Konfigurieren von Berichte festlegen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervall für Abschlussmeldung </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden), mit der <span class="keyword"> Berichtsserver </span> Abschlussstatusmeldungen druckt, wenn Abfragen während der Berichterstellung oder Warnhinweiserstellung ausgeführt werden. Der Standardwert ist 120 Sekunden. </p> <p>Beispiel: Workspace-Abfragen sind zu 62,145672 % abgeschlossen. </p> <p>Abschlussmeldungen werden in die Datei <span class="filepath"> reportserver.log </span> geschrieben und mit dem Server synchronisiert. Diese Einstellung steuert die <span class="filepath"> status.txt </span>-Dateien, die für jeden Berichtssatz hin- und hergesendet werden, damit der Prozentwert vollständig mit Miniaturen angezeigt werden kann. Die Meldungen werden immer dann gesendet, wenn ein Berichtsatz abgeschlossen ist oder das Intervall erreicht wird (je nachdem, was zuerst eintritt). Wenn Sie diesen Wert höher einstellen, hat dies keine Auswirkungen auf die Rate, mit der der Bericht in der Client-Oberfläche durch die Miniaturansichten generiert wurde, sondern wirkt sich auf die Anzahl der Zwischenmeldungen aus. Wenn Sie einen niedrigen Wert angeben, verbringt das System einen großen Teil der Zeit mit der Synchronisierung der Daten, da die Daten von <span class="keyword"> Report Server </span> mit dem Profil, über alle DPUs und alle angeschlossenen Clients bei jeder Änderung der Meldung <span class="filepath"> status.txt </span> synchronisiert werden. </p> <p>Das System sendet immer eine Datei <span class="filepath"> status.txt </span>, wenn ein Bericht abgeschlossen ist, unabhängig von der Einstellung dieses Konfigurationsparameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile </td> 
   <td colname="col2"> <p>Zahl, die angibt, wie viele Elemente in diesem Vektor aufgeführt sind. Fügen Sie für jedes Profil, für das Berichte erstellt werden sollen, einen <span class="wintitle"> ReportProfile </span>-Eintrag im Profil-Vektor hinzu und füllen Sie die Server- und Profil-Parameter aus. </p> <p> <span class="wintitle"> Server  </span> - Der Name, den  <span class="keyword"> Report Server intern zur Identifizierung des Data Workbench-Servers  </span> verwendet. Dieser Name muss der gebräuchliche Servername sein, der im SSL-Zertifikat des Data Workbench-Servers aufgeführt ist. </p> <p> <span class="wintitle"> Profil  </span> - Name des Profils, für das Berichte erstellt werden sollen. Dieser Name muss mit dem benannten Profil auf dem Datenbasis-Servercomputer übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler </td> 
   <td colname="col2"> <p>Die Adresse des SMTP-Servers, von dem Sie <span class="wintitle"> Berichtserver </span>-Fehler per E-Mail senden möchten. </p> <p>Beispiel: <span class="filepath"> mail.mycompany.com </span> </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler-Kennwort </td> 
   <td colname="col2"> <p>Das Kennwort für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler, die von </td> 
   <td colname="col2"> Die E-Mail-Adresse, von der Sie <span class="wintitle"> Berichtserver </span>-Fehler senden möchten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler, die an </td> 
   <td colname="col2"> <p>Die E-Mail-Adresse(n), an die Warnungen gesendet werden. </p> <p>Beispiel: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Benutzernamen "Fehler" </td> 
   <td colname="col2"> <p>Der Benutzername für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Statusintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden), mit der <span class="wintitle"> Report Server </span> Statusinformationen generiert und an den Data Workbench-Server sendet, damit diese in <span class="wintitle"> Detaillierter Status </span> angezeigt werden. </p> <p>Der Standardwert ist 120 Sekunden. Es wird nicht empfohlen, diesen Wert auf einen kleinen Wert (z. B. zwei Minuten) festzulegen, da die Ausführung der Warteschlange eines Berichte mehrere Stunden dauern kann. In diesem Fall sollten Sie eine Einstellung von 600 bis 1200 Sekunden in Erwägung ziehen. </p> <p>Weitere Informationen zu <span class="wintitle"> Detailliertem Status </span> finden Sie im Kapitel "Administrative Schnittstellen"des <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight-Benutzerhandbuchs </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aktualisierungsintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Minuten), mit der <span class="keyword"> Berichtsserver </span> alle im Profil-Vektor aufgelisteten Profil auf neue Berichte und Warnungen überwacht. Der Standardwert ist 10 Minuten. </p> <p>Die von Ihnen angegebene Zeit wird auf alle aufgelisteten Profil aufgeteilt. Wenn Ihr Intervall beispielsweise auf 10 Minuten festgelegt ist und Sie zwei Profil überwachen, wird jedes Profil fünf Minuten lang überwacht. Wenn ein Profil überwacht wird, wenn ein neuer oder geänderter Bericht oder Warnhinweis im Profil gespeichert wird, steht der Bericht oder Warnhinweis sofort zur Generierung zur Verfügung. </p> <p>Wenn das <span class="wintitle"> Update-Intervall </span> für die Überwachung von mehr als einem Profil konfiguriert ist, ist es wichtig, dass diese Einstellung hoch genug ist, um alle Profil innerhalb der konfigurierten Zeit zu laden. Bei Systemen mit vielen konfigurierten großen Dimensionen, bei denen es z. B. mehrere Minuten dauern kann, die anfängliche Datenverbindung mit allen Elementnamen abzurufen, muss diese Einstellung ausreichend lang sein, damit eine vollständige Synchronisierung stattfinden kann. Andernfalls gibt das System einen Profil-Synchronisierungsfehler aus. </p> </td> 
  </tr> 
 </tbody> 
</table>
