---
description: Informationen zu den Parametern von Report Server.cfg.
title: Parameter für „Report Server.cfg“
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Parameter für „Report Server.cfg“{#report-server-cfg-parameters}

{{eol}}

Informationen zu den Parametern von Report Server.cfg.

Beispiel [!DNL Report Server.cfg] angezeigt in [Konfigurieren der Verbindung zu Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) enthält nur die Parameter, die im [!DNL Report Server.cfg] -Datei.

Wenn Sie den Adobe License Server über einen Proxyserver kontaktieren, müssen Sie den Lizenzvektor und seine Parameter zum [!DNL Report Server.cfg]. Im Folgenden finden Sie ein Beispiel für diesen Vektor und dessen Parameter, die Sie für Ihren Lizenzvektor verwenden können:

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
   <td colname="col2"> <p>Zu den unterstützten Excel-Erweiterungen gehören: </p> <p>Excel-Erweiterung = Zeichenfolge: <span class="filepath"> .xlsx </span> </p> <p>Excel-Erweiterung = Zeichenfolge: <span class="filepath"> .xls </span> (dies ist die Standardeinstellung) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schriftarten </td> 
   <td colname="col2"> <p>Optional. Vektor, der die Schriften auflistet, die <span class="keyword"> Berichtsserver </span> sollte zum Rendern von UTF8-basierten Unicode-Sonderzeichen verwendet werden. Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schriftart sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht im <span class="filepath"> Report Server.cfg </span> Datei, <span class="keyword"> Berichtsserver </span> verwendet nur die Konsole "Lucida Sans", um Text anzuzeigen. </p> <p> <span class="keyword"> Berichtsserver </span> verwendet die erste Schriftart in der Liste, um alle Zeichen wiederzugeben, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Dieses Zeichen wird dann mit der zweiten Schriftart in der Liste gerendert. Wenn diese Schrift das Zeichen nicht rendert, <span class="keyword"> Berichtsserver </span> verwendet die dritte Schriftart in der Liste, um dieses Zeichen usw. zu rendern, bis es das Ende der Schriftartenliste erreicht. Wenn die richtige Schriftart nicht im Vektor aufgeführt ist, <span class="keyword"> Berichtsserver </span> zeigt den Hexadezimalwert für das Zeichen an. </p> <p> <p>Hinweis: Nehmen Sie keine Änderungen an diesem Parameter vor, während <span class="keyword"> Berichtsserver </span> läuft. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma </span> Einstellung für <span class="filepath"> .png </span> Dateiausgabe. Der Standardwert lautet 1.6. </p> <p> <p>Hinweis: Es wird von Adobe nicht empfohlen, diesen Wert zu ändern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lizenzierung </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter in diesem Vektor nur ändern, wenn Sie den Lizenzserver der Adobe über einen Proxyserver kontaktieren. </p> <p>Bereichs-ID für Parameter, die Sie festlegen, um den Lizenzserver der Adobe über einen Proxyserver zu kontaktieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxyservers, der <span class="keyword"> Berichtsserver </span> muss für den Zugriff auf den Lizenzserver der Adobe verwendet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Kennwort </td> 
   <td colname="col2"> Optional. Das Kennwort, das mit dem <span class="wintitle"> Proxy-Benutzername </span>. </td> 
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
   <td colname="col2"> Der Netzwerkspeicherort, unter dem <span class="keyword"> Berichtsserver </span> verwendet , um den allgemeinen Namen des Servers in eine IP-Adresse aufzulösen. Netzwerkspeicherorte werden in der Adressdatei definiert, die sich im Verzeichnis Adressen auf dem Data Workbench-Servercomputer befindet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server </td> 
   <td colname="col2"> <p>Abschnittskennung für Parameter, die Sie zum Konfigurieren der Server-Maschinen für Data Workbench festlegen <span class="keyword"> Berichtsserver </span> muss eine Verbindung herstellen, um Berichte zu generieren. Dazu gehört eine Zahl, die angibt, wie viele Elemente in diesem Vektor aufgelistet sind. </p> <p>Fügen Sie für jeden Server einen serverInfo -Eintrag hinzu und füllen Sie die Parameter nach Bedarf aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> IP-Adresse des Data Workbench-Servercomputers, an den <span class="keyword"> Berichtsserver </span> muss eine Verbindung herstellen, um Berichte zu generieren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Der Name, der <span class="keyword"> Berichtsserver </span> verwendet intern, um den Data Workbench-Server zu identifizieren. Dies ist einfach eine interne Bezeichnung, sodass Sie jeden beliebigen Namen verwenden können. Zur Konsistenz empfehlen wir die Verwendung des allgemeinen Namens, der im digitalen Zertifikat des Servers aufgeführt ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Hafen, <span class="keyword"> Berichtsserver </span> kommuniziert mit dem Data Workbench-Server. Bei sicheren Verbindungen ist dieser Wert normalerweise 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy-Adresse </td> 
   <td colname="col2"> Die Adresse eines Proxyservers, der <span class="keyword"> Berichtsserver </span> muss für den Zugriff auf den Data Workbench-Server verwendet werden. Dieser Parameter ist nur erforderlich, wenn ein Proxy-Server für die Verbindung mit Ihren Servercomputern erforderlich ist. </td> 
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
   <td colname="col2"> Name der SSL-Zertifikatdatei für die <span class="keyword"> Berichtsserver </span> Maschine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allgemeiner SSL-Server-Name </td> 
   <td colname="col2"> <span class="wintitle"> Server Common Name </span> auf dem digitalen Zertifikat des Data Workbench-Servers aufgelistet ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL verwenden </td> 
   <td colname="col2"> Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und <span class="keyword"> Berichtsserver </span>. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Result Memory Limit (KB) </td> 
   <td colname="col2"> <p>Die Speicherkapazität (in KB), die Sie für Berichte und Warnhinweise zur Verfügung stellen möchten. Der Standardwert lautet 50000. </p> <p>Beim Ausführen von Berichten <span class="keyword"> Berichtsserver </span> überprüft diesen Wert zuerst und überprüft dann den Wert im Parameter Maximale Slice Size . Wenn Sie diesen Parameter beispielsweise auf 50.000 und die maximale Slice-Größe auf 50 festlegen, <span class="keyword"> Berichtsserver </span> führt nur 50 Arbeitsbereiche gleichzeitig aus, selbst wenn genügend Platz für die Ausführung weiterer Arbeitsbereiche zur Verfügung steht. </p> <p> <p>Hinweis: Diese Grenze sollte niemals den im Abfragespeicherlimitierungsparameter des Data Workbench-Servers festgelegten Wert überschreiten und idealerweise etwas niedriger als der Wert <span class="wintitle"> Speicherbegrenzung für Abfrage </span> , um anderen Benutzern, die möglicherweise gleichzeitig Berichte ausführen, einen gewissen Spielraum zu bieten. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maximale Slice-Größe </td> 
   <td colname="col2"> Die maximale Anzahl von Bericht-Arbeitsbereichen, die <span class="keyword"> Berichtsserver </span> kann gleichzeitig ausgeführt werden. Der Standardwert lautet 50. Weitere Informationen zum <span class="keyword"> Berichtsserver </span> verwendet diese Einstellung, siehe <span class="wintitle"> Result Memory Limit (KB) </span> Parameterbeschreibung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software aktualisieren </td> 
   <td colname="col2"> <p>Gibt an, ob dies zulässig ist <span class="keyword"> Die </span> Software, die vom Data Workbench-Server aktualisiert werden soll. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </p> <p>Im Folgenden finden Sie ein Beispiel für diesen Parameter, mit dem Sie ein Modell verwenden können: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGL-Hardware-Rendering verwenden </td> 
   <td colname="col2"> <p>Steuert, ob <span class="keyword"> Berichtsserver </span> verwendet Hardware-Rendering (z. B. die Grafikkarte des Computers), um eine Berichtsausgabe zu erstellen. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </p> <p>Dieser Parameter sollte nur bei Problemen mit Ihrer Grafikkarte auf false gesetzt werden. Wenn auf false festgelegt, <span class="keyword"> Berichtsserver </span> versucht nicht, Hardware-Rendering zu verwenden und verwendet standardmäßig Software-Rendering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Berichterstellung </td> 
   <td colname="col2"> Bereichs-ID für Parameter, die Sie zum Konfigurieren der Berichterstellung festlegen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abschlussmeldungsintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden) mit der <span class="keyword"> Berichtsserver </span> druckt Statusnachrichten, wenn Abfragen während der Berichterstellung oder Warnhinweiserstellung ausgeführt werden. Der Standardwert ist 120 Sekunden. </p> <p>Beispiel: Workspace-Abfragen sind zu 62,145672 % abgeschlossen. </p> <p>Abschlussmeldungen werden in die <span class="filepath"> reportserver.log </span> und werden mit dem Server synchronisiert. Diese Einstellung steuert die <span class="filepath"> status.txt </span> -Dateien, die für jeden Berichtssatz hin- und hergesendet werden, sodass der prozentuale Abschluss mit Miniaturansichten angezeigt werden kann. Die Nachrichten werden immer dann gesendet, wenn ein Berichtssatz abgeschlossen ist oder das Intervall erreicht ist (je nachdem, was zuerst eintritt). Wenn Sie diesen Wert höher setzen, wirkt sich dies nicht auf die Rate aus, mit der der Bericht in der Client-Oberfläche durch Miniaturansichten generiert wird, sondern auf die Anzahl der Zwischennachrichten, die Sie sehen. Die Angabe eines niedrigen Werts kann dazu führen, dass das System große Zeit mit der Datensynchronisation verbringt, da die Daten aus <span class="keyword"> Berichtsserver </span> dem Profil, allen DPUs und allen verbundenen Clients jedes Mal <span class="filepath"> status.txt </span> Nachrichtenänderungen. </p> <p>Das System sendet immer eine <span class="filepath"> status.txt </span> -Datei, wenn ein Berichtssatz abgeschlossen wird, unabhängig von der Einstellung dieses Konfigurationsparameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile </td> 
   <td colname="col2"> <p>Zahl, die angibt, wie viele Elemente in diesem Vektor aufgelistet sind. Fügen Sie für jedes Profil, für das Berichte erstellt werden sollen, eine <span class="wintitle"> ReportProfile </span> in den Profilvektor ein und füllen Sie die Parameter Server und Profil aus. </p> <p> <span class="wintitle"> Server </span> - der Name, <span class="keyword"> Berichtsserver </span> verwendet intern, um den Data Workbench-Server zu identifizieren. Dieser Name muss der gebräuchliche Servername sein, der im SSL-Zertifikat des Data Workbench-Servers aufgeführt ist. </p> <p> <span class="wintitle"> Profil </span> - Name des Profils, für das Berichte erstellt werden sollen. Dieser Name muss mit dem benannten Profil auf dem Data Workbench-Servercomputer übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehler </td> 
   <td colname="col2"> <p>Die Adresse des SMTP-Servers, von dem Sie senden möchten <span class="wintitle"> Berichtsserver </span> Fehler per E-Mail. </p> <p>Beispiel: <span class="filepath"> mail.mycompany.com </span> </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für Fehlerkennwort </td> 
   <td colname="col2"> <p>Das Kennwort für die Anmeldung beim SMTP-Server. Dieser Parameter ist optional, es sei denn, die Anmeldung ist zum Senden von E-Mails erforderlich. </p> <p>Für die Verwendung der beschriebenen Funktionen ist ein SMTP-Server erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-Server für von gesendete Fehler </td> 
   <td colname="col2"> Die E-Mail-Adresse, von der Sie senden möchten <span class="wintitle"> Berichtsserver </span> Fehler. </td> 
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
   <td colname="col2"> <p>Die Häufigkeit (in Sekunden) mit der <span class="wintitle"> Berichtsserver </span> generiert Statusinformationen und sendet diese an den Data Workbench-Server, der in angezeigt werden soll. <span class="wintitle"> Detaillierter Status </span>. </p> <p>Der Standardwert ist 120 Sekunden. Es wird nicht empfohlen, diesen Wert auf einen kleinen Wert festzulegen, z. B. zwei Minuten, da die Ausführung einer Berichtswarteschlange Stunden dauern kann. In diesem Fall können Sie eine Einstellung von 600 bis 1200 Sekunden in Erwägung ziehen. </p> <p>Weitere Informationen finden Sie unter <span class="wintitle"> Detaillierter Status </span>, siehe das Kapitel "Verwaltungsschnittstellen"im Abschnitt <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight-Benutzerhandbuch </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aktualisierungsintervall </td> 
   <td colname="col2"> <p>Die Häufigkeit (in Minuten) mit der <span class="keyword"> Berichtsserver </span> überwacht alle im Profilvektor aufgelisteten Profile auf neue Berichte und Warnhinweise. Der Standardwert ist 10 Minuten. </p> <p>Die von Ihnen angegebene Uhrzeit wird auf alle aufgelisteten Profile aufgeteilt. Wenn Ihr Intervall beispielsweise auf 10 Minuten festgelegt ist und Sie zwei Profile überwachen, wird jedes Profil fünf Minuten lang überwacht. Wenn ein Profil überwacht wird, wenn ein neuer oder geänderter Bericht oder Warnhinweis im Profil gespeichert wird, steht der Bericht oder Warnhinweis sofort zur Generierung zur Verfügung. </p> <p>Wenn die Variable <span class="wintitle"> Aktualisierungsintervall </span> konfiguriert wurde, um mehr als ein Profil zu überwachen. Es ist wichtig, dass diese Einstellung hoch genug ist, um alle Profile innerhalb der konfigurierten Zeit zu laden. In Systemen mit vielen konfigurierten großen Dimensionen, in denen es beispielsweise mehrere Minuten dauern kann, bis die anfängliche Datenverbindung mit allen Elementnamen abgerufen wird, muss diese Einstellung ausreichend lang sein, damit eine vollständige Synchronisation stattfinden kann. Andernfalls gibt das System einen Fehler bei der Profilsynchronisierung aus. </p> </td> 
  </tr> 
 </tbody> 
</table>
