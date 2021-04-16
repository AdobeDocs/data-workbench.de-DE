---
description: Legen Sie die Parameter in der Datei "Insight.cfg"fest, um die Konfigurationseinstellungen für die Netzwerkverbindung und die Data Workbench festzulegen.
title: Konfigurationsparameter
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Konfigurationsparameter{#configuration-parameters}

Legen Sie die Parameter in der Datei &quot;Insight.cfg&quot;fest, um die Konfigurationseinstellungen für die Netzwerkverbindung und die Data Workbench festzulegen.

Das folgende Beispiel enthält standardmäßig nur die Parameter, die in der Datei [!DNL Insight.cfg] enthalten sind.

**Neue Layout-Ansicht**

![](assets/config_tree_new_layout.png)

**Ansicht des Originallayouts**

![](assets/cfg_Workstation_AddServer.png)

Einige der in der neuen [!DNL Insight.cfg]-Datei verfügbaren Parameter stehen in Ihrer Version der [!DNL Insight.cfg]-Datei möglicherweise nicht zur Verfügung. Wenn einer dieser Parameter benötigt wird, müssen Sie ihn der Datei [!DNL Insight.cfg] mit [!DNL Add Custom Key] hinzufügen, indem Sie mit der rechten Maustaste auf einen Parameter klicken und dann den Namen und den Typ angeben. Sie können Parameter auch hinzufügen, indem Sie die Datei [!DNL .cfg] (im Installationsordner der Data Workbench) mit einem Texteditor öffnen.

Im Folgenden finden Sie ein Beispiel für alle Parameter, die für die Datei [!DNL Insight.cfg] verfügbar sind und die Sie als Modell zum Hinzufügen von Parametereinträgen verwenden können:

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

Die folgende Tabelle enthält Beschreibungen der verfügbaren [!DNL Insight.cfg]-Dateiparameter in alphabetischer Reihenfolge.

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>Der Hostname oder die numerische IP-Adresse des Data Workbench-Servercomputers. </p> <p>Beispiel: <span class="filepath"> vsServer.mycompany.com oder 192.168.1.90</span> </p> <p>Wenn <span class="wintitle"> Address</span> nicht angegeben ist, verwendet <span class="keyword"> der Client</span> den im Parameter SSL-Server Common Name angegebenen gemeinsamen Namen, wenn Use Address File auf false festgelegt ist. </p> <p> <p>Hinweis: Wenn der Parameter "Adressdatei verwenden"auf "true"gesetzt ist, kann der im Parameter "Adresse"eingegebene Text entfernt werden, nachdem das erste Profil auf dem Client <span class="keyword"> geöffnet wurde. </span> Dann bestimmt die Einstellung für "Network Location Parameter", welche Adressen aus der Adressdatei des Clusters für die Verbindung mit dem Übergeordnet-Server verwendet werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Farbsatz </p> </td> 
   <td colname="col2"> <p>Gibt die Hintergrundfarbe der Clientanwendung <span class="keyword"></span> an. Die Optionen lauten wie folgt: </p> <p>0 = schwarz </p> <p>1 = weiß </p> <p>2 = Monochrom </p> <p>Der Standardwert ist 0, schwarz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardstufe Online </p> </td> 
   <td colname="col2"> <p>Optional. Ermöglicht es Ihnen, Ihre Instanz der Data Workbench beim Öffnen standardmäßig als Streaming, offline oder online zu verwenden. Die Optionen sind Streaming, Online oder Offline. Die Standardkonfiguration für die Data Workbench ist die Offline-Funktion. </p> <p> <p>Hinweis: Bevor Sie sich dafür entscheiden, standardmäßig online zu arbeiten, stellen Sie sicher, dass die unter <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Offline arbeiten und Online</a> beschriebenen Vorteile und Folgen abgewogen werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schriftarten </p> </td> 
   <td colname="col2"> <p>Optional. Vector listet die Schriften auf, die der Client <span class="keyword"> zum Rendern von UTF8-basierten Unicode-Sonderzeichen verwenden sollte. </span> Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schrift sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht in der Datei <span class="filepath"> Insight.cfg</span> enthalten ist, verwendet Data Workbench zur Textdarstellung nur die Lucida Sans-Konsole. </p> <p> Data Workbench verwendet die erste Schrift in der Liste, um alle Zeichen zu rendern, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Es verwendet die zweite Schrift in der Liste, um dieses Zeichen zu rendern. Wenn diese Schrift das Zeichen nicht wiedergibt, verwendet Data Workbench die dritte Schrift in der Liste, um das Zeichen usw. darzustellen, bis es das Ende der Schrift-Liste erreicht. Wenn die richtige Schrift nicht im Vektor aufgeführt ist, zeigt Data Workbench den Hexadezimalwert des Zeichens an. </p> <p> <p>Hinweis:  Ändern Sie diesen Parameter nicht, während die Data Workbench ausgeführt wird. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Gamma-Einstellung für die Anzeige der Data Workbench. Der Standardwert ist 1.6. Es wird nicht empfohlen, diesen Wert zu ändern. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lizenzierung </p> </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter im Lizenzierungsvektor nur ändern, wenn Sie den Lizenzserver der Adobe über einen Proxyserver kontaktieren. </p> <p>Abschnittskennung für Parameter, die es Ihrem <span class="keyword">-Client</span> ermöglichen, den Adobe License Server über einen Proxyserver zu kontaktieren. Erweitern Sie den Knoten Lizenzierung und führen Sie die folgenden Parameter aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Adresse </p> </td> 
   <td colname="col2"> <p>Optional. Die Adresse des Proxyservers, die <span class="keyword"> client</span> verwenden muss, um auf die Adobe License Server zuzugreifen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyanschluss </p> </td> 
   <td colname="col2"> <p>Optional. Der Anschluss des Proxyservers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Benutzername </p> </td> 
   <td colname="col2"> <p>Optional. Der Benutzername für den Proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Kennwort </p> </td> 
   <td colname="col2"> <p>Optional. Das Kennwort, das dem Proxy-Benutzernamen zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximale Stichprobengröße (MB) </p> </td> 
   <td colname="col2"> <p>Gibt die maximal zulässige Größe im Datencache an, der von dem auf einem einzelnen Computer ausgeführten Client <span class="keyword"> verwendet wird.</span> </p> <p>Während der Parameter "Beispielbyte"in der Datei <span class="filepath"> server.cfg</span> die Datencache-Größe aller <span class="keyword">-Clients</span>, die eine Verbindung mit einem Data Workbench-Server herstellen (standardmäßig 250e6-Byte), festlegt, können Sie mit dem Parameter "Maximale Stichprobengröße"die Datencache-Größe für einen bestimmten Computer weiter einschränken. Dies ist nützlich, wenn der Client auf einem Computer mit eingeschränkter Datenspeicherung oder Rechenleistung installiert ist. </p> <p> <p>Hinweis: Dieser Parameter begrenzt die Größe eines lokalen Datenmusters, das lokal vom Client-Programm abgefragt wird. Im Gegensatz dazu enthält die Datei <span class="filepath"> cache.db</span> Daten zu jedem Profil, mit dem der Client eine Verbindung herstellt, sowie Elementnamen und -dimensionen. Diese Elementnamen und -dimensionen in den <span class="filepath"> cache.db</span>-Dateien sind erforderlich, um lokale Abfragen auszuführen. Folglich gibt es keine Möglichkeit, seine Größe zu beschränken, außer die Anzahl der Elemente im Datensatz zu reduzieren. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2">Optional. Der Name, den <span class="keyword"> der Client</span> verwendet, um den <span class="keyword">-Server</span> zu identifizieren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkspeicherort </p> </td> 
   <td colname="col2"> <p>Optional. Der Netzwerkspeicherort, der von <span class="keyword"> client</span> verwendet wird, um den Stammnamen des Data Workbench-Servers in eine IP-Adresse aufzulösen. Die verfügbaren Netzwerkspeicherorte werden in der Adressdatei auf dem Server definiert. Weitere Informationen finden Sie im <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> <p>Wenn Sie keinen Netzwerkspeicherort angeben, löst <span class="keyword"> client</span> allgemeine Namen mithilfe des Standardnetzwerkspeicherorts "Insight"auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anschluss </p> </td> 
   <td colname="col2"> <p>Der Anschluss, an den <span class="keyword"> der Client</span> Anforderungen sendet. Diese Anschlussnummer muss mit dem Anschluss übereinstimmen, an dem der Data Workbench-Server auf Anforderungen überwacht. Dies ist normalerweise 443 für sichere Verbindungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Adresse </p> </td> 
   <td colname="col2"> <p>Wenn ein Proxyserver zum Herstellen einer Verbindung mit Ihren Data Workbench-Servercomputern erforderlich ist, müssen Sie mindestens diesen Parameter und den Proxy-Port-Parameter angeben. Sie können optional die Parameter Proxy-Benutzername und Proxy-Benutzerkennwort ausfüllen. </p> <p>Die Adresse des Proxyservers, die <span class="keyword"> vom Client</span> für den Zugriff auf den Data Workbenchs-Server verwendet werden muss. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Kennwort </p> </td> 
   <td colname="col2"> <p>Optional. Das Kennwort für den Proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyanschluss </p> </td> 
   <td colname="col2"> <p>Der Anschluss des Proxyservers. Der Standardwert lautet 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Benutzername </p> </td> 
   <td colname="col2"> <p>Optional. Der Benutzername für den Proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durchsuchen </p> </td> 
   <td colname="col2"> <p>In der Datei <span class="filepath"> Insight.cfg</span> (oder in einer <span class="filepath"> .cfg</span>-Datei) können Sie nach Schlüsselname, Schlüsseltyp oder Wert suchen, um einen Eintrag schnell zu finden, sodass kein Bildlauf durch erweiterte, große Dateien für verschachtelte Informationen erforderlich ist. Sie können Dimensionsnamen, Servernamen usw. suchen. </p> <p>Geben Sie einen Suchbegriff in dieses Feld ein, um die Daten zu suchen. Je nach Erfolg einer Übereinstimmung ändert sich die Feldfarbe. Übereinstimmungen werden hervorgehoben und Nichtübereinstimmungen abgeblendet angezeigt. Wenn keine Übereinstimmung vorliegt, wird der Hintergrund des Suchfelds rot. Wenn Sie die Eingabetaste drücken, erweitert der Konfigurationsbaum jeden Ort, an dem eine Übereinstimmung vorliegt, und reduziert den Punkt, an dem keine Übereinstimmung vorliegt. </p> <p>Sie können auch reguläre Ausdruck im Feld <span class="wintitle"> Suche</span> verwenden. Sie können beispielsweise Folgendes verwenden: <span class="filepath"> *zip.*</span> für alle Einträge mit dem Wort "zip". </p> <p>Um eine Suche zu löschen, drücken Sie <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p>Vektorüberschrift für <span class="keyword">-Verbindungen </span> bis <span class="keyword"> Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-Client-Zertifikat </p> </td> 
   <td colname="col2"> <p>Optional, es sei denn, Sie verfügen über mehr als ein Zertifikat. Der Name der Datei, die das digitale Zertifikat für diese Kopie der Data Workbench enthält. Diese Datei haben Sie unter Herunterladen und Installieren des digitalen Zertifikats heruntergeladen. </p> <p>Beispiel: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Wenn Sie diesen Parameter leer lassen, verwendet <span class="keyword"> der Client</span> das vorhandene Zertifikat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-Server - Allgemeiner Name </p> </td> 
   <td colname="col2"> <p>Der allgemeine Name des Data Workbench-Servers (wie auf dem digitalen Zertifikat zugewiesen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Symbolleistensymbole </p> </td> 
   <td colname="col2"> <p>False deaktiviert die Symbole in der Workstation-Benutzeroberfläche und zeigt Text in der Symbolleiste an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adressdatei verwenden </p> </td> 
   <td colname="col2"> <p>Gibt an, ob Einstellungen in der Adressdatei die Parametereinstellung "Adresse"außer Kraft setzen. Die Optionen sind "true"oder "false". Wenn "true"festgelegt ist, setzen die Einstellungen in der Adressdatei, falls vorhanden, die Parametereinstellung "Address"außer Kraft. Der Standardwert ist true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL verwenden </p> </td> 
   <td colname="col2">Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und dem Client <span class="keyword"> verwendet wird. </span> Die Optionen sind "true"oder "false". Der Standardwert ist true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alle ausblenden </p> </td> 
   <td colname="col2"> <p>Optional. Ermöglicht Ihnen, alle Metriken, Dimensionen und Filter, die mithilfe einer der folgenden Funktionen ausgeblendet wurden, vorübergehend wieder einzublenden: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[Ausschließliche] Einstellung in <span class="filepath"> order.txt</span>-Dateien </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Option in den Dateien <span class="filepath"> order.txt</span> ausblenden </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Parameter in den Dateien <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> und <span class="filepath"> .filter</span> anzeigen. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Ausgeblendeter Parameter in der Datei <span class="filepath"> Transformation.cfg</span>. </li> 
     </ul> </p> <p>Weitere Informationen zu diesen Methoden finden Sie unter <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Menüelement</a> ausblenden. </p> <p>Die Optionen sind "true"oder "false". Die Standardeinstellung ist "false". Ändern Sie diesen Parameter in true, um ausgeblendete Metriken, Dimensionen und Filter vorübergehend wieder einzublenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entsperren </p> </td> 
   <td colname="col2"> <p>Optional. Gibt an, ob Sie gesperrte Arbeitsbereiche entsperren dürfen. Die Optionen sind "true"und "false". Mit "True"können Sie gesperrte Arbeitsflächen entsperren, nicht jedoch mit "false". Der Standardwert ist „false“. Weitere Informationen zu gesperrten Arbeitsbereichen finden Sie unter <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Entsperren eines Arbeitsbereichs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Software aktualisieren </p> </td> 
   <td colname="col2"> <p>Optional. Gibt an, ob diese <span class="keyword">-Clientsoftware vom Data Workbench-Server aktualisiert werden soll. </span> Die Optionen sind "true"oder "false". Der Standardwert ist true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzerordner </p> </td> 
   <td colname="col2"> <p>Optional. Gibt den Namen und den Speicherort des Ordners an, der die lokalen Kopien aller Arbeitsbereiche, Metriken, Dimensionen oder Konfigurationsdateien für jedes Profil enthält. Die Standardeinstellung ist User\\, der den Ordner User im Installationsordner der Data Workbench angibt. </p> <p>Eine Änderung dieser Einstellung ist nützlich, wenn zwei Benutzer denselben Computer gemeinsam verwenden. Um beide Benutzer aufzunehmen, können Sie einen freigegebenen Ordner angeben, auf den beide Benutzer Zugriff haben. </p> </td> 
  </tr> 
 </tbody> 
</table>
