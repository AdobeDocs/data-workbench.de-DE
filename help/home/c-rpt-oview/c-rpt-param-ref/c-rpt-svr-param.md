---
description: Informationen zu den Parametern Report Server.cfg.
solution: Analytics
title: Report Server.cfg-Parameter
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Report Server.cfg-Parameter{#report-server-cfg-parameters}

Informationen zu den Parametern Report Server.cfg.

Das Beispiel [!DNL Report Server.cfg] unter Verbindung mit Insight [konfigurieren](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) enthält standardmäßig nur die in der [!DNL Report Server.cfg] Datei enthaltenen Parameter.

Wenn Sie den Adobe License Server über einen Proxyserver kontaktieren, müssen Sie den Lizenzvektor und dessen Parameter zum [!DNL Report Server.cfg]Server hinzufügen. Im Folgenden finden Sie ein Beispiel für diesen Vektor und seine Parameter, mit denen Sie ein Modell für Ihren Licensing-Vektor verwenden können:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Die folgende Tabelle enthält Beschreibungen der [!DNL Report Server.cfg] Dateiparameter:

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
   <td colname="col2"> <p>Zu den unterstützten Excel-Erweiterungen gehören: </p> <p>Excel Extension = Zeichenfolge: <span class="filepath"> .xlsx </span> </p> <p>Excel Extension = Zeichenfolge: <span class="filepath"> .xls </span> (Standard) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schriftarten </td> 
   <td colname="col2"> <p>Optional. Vector, der die Schriftarten auflistet, die <span class="keyword"> Report Server zum Rendern UTF8-basierter Unicode-Sonderzeichen verwenden </span> sollte. Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schrift sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht in der <span class="filepath"> Report Server.cfg- </span> Datei enthalten ist, verwendet <span class="keyword"> </span> Report Server nur die Lucida Sans-Konsole, um Text anzuzeigen. </p> <p> <span class="keyword"> Report Server </span> verwendet die erste Schrift in der Liste, um alle Zeichen wiederzugeben, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Anschließend wird das Zeichen mit der zweiten Schriftart in der Liste wiedergegeben. Wenn diese Schrift das Zeichen nicht wiedergibt, <span class="keyword"> </span> verwendet Report Server die dritte Schrift in der Liste, um das Zeichen usw. zu rendern, bis es das Ende der Schriftliste erreicht. Wenn die richtige Schrift nicht im Vektor aufgeführt ist, zeigt <span class="keyword"> Report Server den Hexadezimalwert für das Zeichen </span> an. </p> <p> <p>Hinweis:  Nehmen Sie keine Änderungen an diesem Parameter vor, während <span class="keyword"> Report Server ausgeführt </span> wird. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma- </span> Einstellung für <span class="filepath"> .png- </span> Dateiausgabe. Der Standardwert lautet 1.6. </p> <p> <p>Hinweis:  Adobe empfiehlt nicht, diesen Wert zu ändern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lizenzierung </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter in diesem Vektor nur ändern, wenn Sie den Lizenzserver von Adobe über einen Proxyserver kontaktieren. </p> <p>Abschnittskennung für Parameter, die Sie festlegen, um den Adobe-Lizenzserver über einen Proxyserver zu kontaktieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxyservers, den <span class="keyword"> Report Server für den Zugriff auf den Adobe-Lizenzserver verwenden </span> muss. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Kennwort </td> 
   <td colname="col2"> Optional. Das Kennwort für den <span class="wintitle"> Proxybenutzernamen </span>. </td> 
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
   <td colname="col2"> Der Netzwerkspeicherort, den <span class="keyword"> Report Server </span> verwendet, um den gemeinsamen Namen des Servers in eine IP-Adresse aufzulösen. Netzwerkspeicherorte werden in der Adressdatei definiert, die sich im Adressverzeichnis des Datenbasis-Servercomputers befindet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server </td> 
   <td colname="col2"> <p>Abschnittskennung für Parameter, die Sie festlegen, um zu konfigurieren, welche Datenbasis-Servercomputer <span class="keyword"> Report Server eine Verbindung zum Generieren von Berichten herstellen </span> müssen. Dazu gehört eine Zahl, die angibt, wie viele Elemente in diesem Vektor aufgelistet sind. </p> <p>Fügen Sie für jeden Server einen "serverInfo"-Eintrag hinzu und füllen Sie die Parameter nach Bedarf aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> IP-Adresse des Data Workbench-Servercomputers, mit dem sich <span class="keyword"> Report Server verbinden </span> muss, um Berichte zu erstellen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Der Name, den <span class="keyword"> Report Server intern zur Identifizierung des Data Workbench-Servers </span> verwendet. Dies ist einfach eine interne Bezeichnung, sodass Sie jeden beliebigen Namen verwenden können. Aus Gründen der Konsistenz sollten Sie den im digitalen Zertifikat des Servers angegebenen gemeinsamen Namen verwenden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anschluss </td> 
   <td colname="col2"> Anschluss, über den <span class="keyword"> Report Server mit dem Data Workbench-Server </span> kommuniziert. Bei sicheren Verbindungen ist dieser Wert in der Regel 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxyservers, den <span class="keyword"> Report Server für den Zugriff auf den Data Workbench-Server verwenden </span> muss. Dieser Parameter ist nur erforderlich, wenn ein Proxyserver für die Verbindung mit Ihren Servercomputern erforderlich ist. </td> 
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
   <td colname="col2"> Name der SSL-Zertifikatdatei für den <span class="keyword"> Report Server- </span> Computer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Server - Allgemeiner Name </td> 
   <td colname="col2"> <span class="wintitle"> Server Common Name </span> aufgelistet im digitalen Zertifikat des Data Workbench-Servers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL verwenden </td> 
   <td colname="col2"> Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und dem <span class="keyword"> Report Server verwendet wird </span>. Die Optionen sind "true"oder "false". Der Standardwert ist true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maximaler Arbeitsspeicher (KB) </td> 
   <td colname="col2"> <p>Der Arbeitsspeicher (in KB), den Sie für Berichte und Warnungen zur Verfügung stellen möchten. Der Standardwert lautet 50000. </p> <p>Bei der Ausführung von Berichten überprüft <span class="keyword"> </span> Report Server diesen Wert zuerst und prüft dann den Wert im Parameter "Maximum Slice Size". Wenn Sie diesen Parameter z. B. auf 50.000 und die maximale Slice-Größe auf 50 festlegen, <span class="keyword"> </span> führt Report Server nur 50 Arbeitsflächen aus, selbst wenn genügend Platz zum Ausführen weiterer Arbeitsflächen vorhanden ist. </p> <p> <p>Hinweis:  Diese Beschränkung sollte niemals den im Abfragespeicherlimit des Data Workbench-Servers festgelegten Wert überschreiten und sollte idealerweise etwas niedriger als die <span class="wintitle"> Abfragespeichergrenze eingestellt werden, </span> um anderen Benutzern, die gleichzeitig Berichte ausführen, Spielraum zu geben. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max. Slice-Größe </td> 
   <td colname="col2"> Die maximale Anzahl von Bericht-Arbeitsbereichen, die <span class="keyword"> Report Server gleichzeitig ausführen </span> kann. Der Standardwert lautet 50. Weitere Informationen darüber, wie <span class="keyword"> Report Server diese Einstellung </span> verwendet, finden Sie in der Beschreibung des <span class="wintitle"> Result Memory Limit (KB)- </span> Parameters. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software aktualisieren </td> 
   <td colname="col2"> <p>Gibt an, ob die Aktualisierung der <span class="keyword"> Software dieses </span> Berichtsservers durch den Data Workbench-Server zulässig ist. Die Optionen sind "true"oder "false". Der Standardwert ist true. </p> <p>Im Folgenden finden Sie ein Beispiel für diesen Parameter, mit dem Sie ein Modell verwenden können: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGL-Hardware-Rendering verwenden </td> 
   <td colname="col2"> <p>Steuert, ob <span class="keyword"> Report Server die Hardware-Wiedergabe (z. B. die Grafikkarte des Computers) zum Erzeugen der Berichtsausgabe </span> verwendet. Die Optionen sind "true"oder "false". Der Standardwert ist true. </p> <p>Dieser Parameter sollte nur dann auf "false"gesetzt werden, wenn Probleme mit der Grafikkarte auftreten. Bei Festlegung auf "false"versucht <span class="keyword"> Report Server </span> nicht, Hardware-Rendering zu verwenden, und verwendet standardmäßig Software-Rendering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Berichterstellung </td> 
   <td colname="col2"> Abschnittskennung für Parameter, die Sie zum Konfigurieren der Berichterstellung festlegen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervall für Abschlussmeldung </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden), mit der <span class="keyword"> Report Server Abschlussstatusmeldungen </span> ausdruckt, wenn Abfragen während der Berichterstellung oder Warnhinweiserstellung ausgeführt werden. Der Standardwert ist 120 Sekunden. </p> <p>Beispiel: Arbeitsbereichabfragen sind zu 62,145672 % abgeschlossen. </p> <p>Abschlussmeldungen werden in die Datei " <span class="filepath"> reportserver.log"geschrieben </span> und mit dem Server synchronisiert. Diese Einstellung steuert die <span class="filepath"> Datei "status.txt", die für jeden Berichtssatz hin- und hergesendet </span> wird, damit der Prozentsatz "complete"mit Miniaturen angezeigt werden kann. Die Meldungen werden immer dann gesendet, wenn ein Berichtsatz abgeschlossen ist oder das Intervall erreicht wird (je nachdem, was zuerst eintritt). Wenn Sie diesen Wert höher einstellen, hat dies keine Auswirkungen auf die Rate, mit der der Bericht in der Client-Oberfläche durch die Miniaturansichten generiert wurde, sondern wirkt sich auf die Anzahl der Zwischenmeldungen aus. Die Angabe eines niedrigen Werts kann dazu führen, dass das System einen großen Teil der Zeit mit der Synchronisierung von Daten verbringt, da die Daten jedes Mal, wenn sich eine <span class="keyword"> status.txt- </span> Meldung ändert, vom <span class="filepath"> Report Server- </span> Server mit dem Profil, über alle DPUs und alle angeschlossenen Clients synchronisiert werden. </p> <p>Das System sendet immer eine <span class="filepath"> Datei "status.txt" </span> , wenn ein Bericht abgeschlossen ist, unabhängig von der Einstellung dieses Konfigurationsparameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile </td> 
   <td colname="col2"> <p>Zahl, die angibt, wie viele Elemente in diesem Vektor aufgeführt sind. Fügen Sie für jedes Profil, für das Berichte erstellt werden sollen, im Profilvektor einen Eintrag <span class="wintitle"> ReportProfile </span> hinzu und füllen Sie die Parameter Server und Profile aus. </p> <p> <span class="wintitle"> Server </span> - Der Name, den <span class="keyword"> Report Server intern zur Identifizierung des Data Workbench-Servers </span> verwendet. Dieser Name muss der gebräuchliche Servername sein, der im SSL-Zertifikat des Data Workbench-Servers aufgeführt ist. </p> <p> <span class="wintitle"> Profil </span> - Name des Profils, für das Berichte erstellt werden sollen. Dieser Name muss mit dem benannten Profil auf dem Datenbasis-Servercomputer übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler </td> 
   <td colname="col2"> <p>Die Adresse des SMTP-Servers, von dem Sie <span class="wintitle"> Report Server- </span> Fehler per E-Mail senden möchten. </p> <p>Beispiel: <span class="filepath"> mail.mycompany.com </span> </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler-Kennwort </td> 
   <td colname="col2"> <p>Das Kennwort für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler, die von </td> 
   <td colname="col2"> Die E-Mail-Adresse, von der Sie <span class="wintitle"> Berichtsserver- </span> Fehler senden möchten. </td> 
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
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden), mit der <span class="wintitle"> Report Server Statusinformationen </span> generiert und an den Data Workbench-Server sendet, um im <span class="wintitle"> Detailstatus angezeigt zu werden </span>. </p> <p>Der Standardwert ist 120 Sekunden. Es wird nicht empfohlen, diesen Wert auf einen kleinen Wert (z. B. zwei Minuten) festzulegen, da die Ausführung einer Berichtwarteschlange Stunden dauern kann. In diesem Fall sollten Sie eine Einstellung von 600 bis 1200 Sekunden in Erwägung ziehen. </p> <p>Weitere Informationen zum <span class="wintitle"> Detailliertem Status </span>finden Sie im Kapitel "Verwaltungsschnittstellen"des <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight-Benutzerhandbuchs </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aktualisierungsintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Minuten), mit der <span class="keyword"> Report Server alle im Profilvektor aufgelisteten Profile auf neue Berichte und Warnungen </span> überwacht. Der Standardwert ist 10 Minuten. </p> <p>Die von Ihnen angegebene Zeit wird auf alle aufgelisteten Profile aufgeteilt. Wenn Ihr Intervall beispielsweise auf 10 Minuten eingestellt ist und Sie zwei Profile überwachen, wird jedes Profil für 5 Minuten überwacht. Wenn ein Profil überwacht wird, wenn ein neuer oder geänderter Bericht oder Warnhinweis im Profil gespeichert wird, steht der Bericht oder Warnhinweis sofort zur Generierung zur Verfügung. </p> <p>Wenn das <span class="wintitle"> Aktualisierungsintervall so konfiguriert </span> ist, dass mehr als ein Profil überwacht wird, ist es wichtig, dass diese Einstellung hoch genug ist, um alle Profile innerhalb der konfigurierten Zeit zu laden. Bei Systemen mit vielen konfigurierten großen Dimensionen, bei denen es z. B. mehrere Minuten dauern kann, die anfängliche Datenverbindung mit allen Elementnamen abzurufen, muss diese Einstellung ausreichend lang sein, damit eine vollständige Synchronisierung stattfinden kann. Andernfalls gibt das System einen Fehler bei der Profilsynchronisierung aus. </p> </td> 
  </tr> 
 </tbody> 
</table>

