---
description: Legen Sie die Parameter in der Datei Insight.cfg fest, um die Konfigurationseinstellungen für die Netzwerkverbindung und Data Workbench festzulegen.
title: Konfigurationsparameter
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Konfigurationsparameter{#configuration-parameters}

Legen Sie die Parameter in der Datei Insight.cfg fest, um die Konfigurationseinstellungen für die Netzwerkverbindung und Data Workbench festzulegen.

Das folgende Beispiel enthält standardmäßig nur die in der Datei [!DNL Insight.cfg] enthaltenen Parameter.

**Neue Layoutansicht**

![](assets/config_tree_new_layout.png)

**Ansicht &quot;Original Layout&quot;**

![](assets/cfg_Workstation_AddServer.png)

Einige der in der neuen Datei [!DNL Insight.cfg] verfügbaren Parameter stehen in Ihrer Version der Datei [!DNL Insight.cfg] möglicherweise nicht zur Verfügung. Wenn einer dieser Parameter benötigt wird, müssen Sie ihn der Datei [!DNL Insight.cfg] mithilfe von [!DNL Add Custom Key] hinzufügen, indem Sie mit der rechten Maustaste auf einen Parameter klicken und dann den Namen und den Typ angeben. Sie können auch Parameter hinzufügen, indem Sie die Datei [!DNL .cfg] (im Installationsverzeichnis der Data Workbench) mithilfe eines Texteditors öffnen.

Im Folgenden finden Sie ein Beispiel aller Parameter, die für die Datei [!DNL Insight.cfg] verfügbar sind und die Sie als Modell zum Hinzufügen von Parametereinträgen verwenden können:

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
   <td colname="col2"> <p>Der Hostname oder die numerische IP-Adresse Ihres Data Workbench-Servercomputers. </p> <p>Beispiel: <span class="filepath"> vsServer.mycompany.com oder 192.168.1.90</span> </p> <p>Wenn <span class="wintitle"> Adresse</span> nicht angegeben ist, verwendet <span class="keyword"> der Client</span> den im Parameter "SSL Server Common Name"angegebenen gemeinsamen Namen, wenn "Use Address File"auf "false"gesetzt ist. </p> <p> <p>Hinweis: Wenn der Parameter Adressdatei verwenden auf "true"gesetzt ist, kann der im Parameter Adresse eingegebene Text entfernt werden, nachdem das erste Profil auf <span class="keyword"> dem Client</span> geöffnet wurde. Anschließend bestimmt die Einstellung für den Netzwerkstandortparameter, welche Adressen aus der Adressdatei des Clusters zum Herstellen einer Verbindung zum Übergeordneten Server verwendet werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Farbset </p> </td> 
   <td colname="col2"> <p>Gibt die Hintergrundfarbe Ihrer <span class="keyword"> Clientanwendung</span> an. Die Optionen lauten wie folgt: </p> <p>0 = schwarz </p> <p>1 = weiß </p> <p>2 = monochrome </p> <p>Der Standardwert ist 0, schwarz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardebene Online-Ebene </p> </td> 
   <td colname="col2"> <p>Optional. Ermöglicht es Ihnen, Ihre Data Workbench-Instanz standardmäßig bei jeder Öffnung als Streaming, offline oder online zu verwenden. Die Optionen sind Streaming, Online oder Offline. Die Standardkonfiguration für die Data Workbench besteht darin, offline zu arbeiten. </p> <p> <p>Hinweis: Bevor Sie sich dafür entscheiden, standardmäßig online zu arbeiten, stellen Sie sicher, dass Sie die unter <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Offline arbeiten und Online</a> beschriebenen Vorteile und Konsequenzen abwägen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schriftarten </p> </td> 
   <td colname="col2"> <p>Optional. Vektor, der die Schriftarten auflistet, die <span class="keyword"> der Client</span> zum Rendern von UTF8-basierten Unicode-Sonderzeichen verwenden sollte. Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schriftart sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht in der Datei <span class="filepath"> Insight.cfg</span> enthalten ist, verwendet Data Workbench nur die Konsole "Lucida Sans", um Text anzuzeigen. </p> <p> Data Workbench verwendet die erste Schriftart in der Liste, um alle Zeichen zu rendern, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Es verwendet die zweite Schriftart in der Liste, um dieses Zeichen zu rendern. Wenn diese Schrift das Zeichen nicht rendert, verwendet Data Workbench die dritte Schrift in der Liste, um dieses Zeichen usw. zu rendern, bis es das Ende der Schriftartenliste erreicht. Wenn die richtige Schriftart nicht im Vektor aufgeführt ist, zeigt Data Workbench den Hexadezimalwert für das Zeichen an. </p> <p> <p>Hinweis:  Ändern Sie diesen Parameter nicht, während die Data Workbench ausgeführt wird. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Gamma-Einstellung für die Anzeige der Data Workbench. Der Standardwert ist 1.6. Es wird von Adobe nicht empfohlen, diesen Wert zu ändern. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lizenzierung </p> </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter im Lizenzvektor nur ändern, wenn Sie den Lizenzserver von Adobe über einen Proxyserver kontaktieren. </p> <p>Bereichs-ID für Parameter, die es Ihrem <span class="keyword">-Client</span> ermöglichen, den Adobe License Server über einen Proxy-Server zu kontaktieren. Erweitern Sie den Knoten Lizenzierung und füllen Sie die folgenden Parameter aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Adresse </p> </td> 
   <td colname="col2"> <p>Optional. Die Adresse des Proxyservers, die <span class="keyword"> client</span> für den Zugriff auf den Adobe License Server verwenden muss. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Port </p> </td> 
   <td colname="col2"> <p>Optional. Der Port des Proxyservers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Benutzername </p> </td> 
   <td colname="col2"> <p>Optional. Der Benutzername für den Proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Kennwort </p> </td> 
   <td colname="col2"> <p>Optional. Das Kennwort für den Proxy-Benutzernamen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximale Stichprobengröße (MB) </p> </td> 
   <td colname="col2"> <p>Gibt die maximal zulässige Größe im Daten-Cache an, der von <span class="keyword"> dem Client</span> verwendet wird, der auf einem einzelnen Computer ausgeführt wird. </p> <p>Während der Parameter "Bytes-Beispiele"in der Datei <span class="filepath"> Server.cfg</span> die Größe des Daten-Caches für alle <span class="keyword"> Clients</span> angibt, die eine Verbindung zu einem Data Workbench-Server herstellen (standardmäßig 250e6 Bytes), können Sie mit dem Parameter Maximale Stichprobengröße die Größe des Daten-Caches für einen bestimmten Computer weiter einschränken. Dies ist nützlich, wenn der Client auf einem Computer mit begrenzter Speicher- oder Rechenleistung installiert ist. </p> <p> <p>Hinweis: Dieser Parameter begrenzt die Größe eines lokalen Datenbeispiels, das vom Clientprogramm lokal abgefragt wird. Im Gegensatz dazu enthält die Datei <span class="filepath"> cache.db</span> Daten für jedes Profil, mit dem der Client eine Verbindung herstellt, sowie Elementnamen und deren Dimensionen. Diese Elementnamen und -dimensionen in den <span class="filepath"> cache.db</span> -Dateien sind zum Ausführen lokaler Abfragen erforderlich. Daher gibt es keine andere Möglichkeit, die Größe zu begrenzen, als die Anzahl der Elemente im Datensatz zu reduzieren. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2">Optional. Der Name, den <span class="keyword"> der Client</span> verwendet, um den <span class="keyword">-Server</span> zu identifizieren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkstandort </p> </td> 
   <td colname="col2"> <p>Optional. Der Netzwerkspeicherort, den <span class="keyword"> client</span> verwendet, um den gemeinsamen Data Workbench-Server-Namen in eine IP-Adresse aufzulösen. Die verfügbaren Netzwerkspeicherorte werden in der Adressdatei auf dem Server definiert. Weitere Informationen finden Sie im <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> <p>Wenn Sie keinen Netzwerkspeicherort angeben, löst <span class="keyword"> client</span> allgemeine Namen mithilfe des standardmäßigen Netzwerkspeicherorts "Insight"auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anschluss </p> </td> 
   <td colname="col2"> <p>Der Port, an den <span class="keyword"> der Client</span> Anforderungen sendet. Diese Anschlussnummer muss mit dem Anschluss übereinstimmen, an dem der Data Workbench-Server auf Anfragen wartet. Dies ist normalerweise 443 für sichere Verbindungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Adresse </p> </td> 
   <td colname="col2"> <p>Wenn ein Proxy-Server für die Verbindung mit Ihren Data Workbench-Servercomputern erforderlich ist, müssen Sie mindestens diesen Parameter und den Proxy-Port-Parameter angeben. Sie können optional die Parameter Proxy-Benutzername und Proxy-Benutzerkennwort eingeben. </p> <p>Die Adresse des Proxyservers, die <span class="keyword"> vom Client</span> für den Zugriff auf den Data Workbench-Server verwendet werden muss. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Kennwort </p> </td> 
   <td colname="col2"> <p>Optional. Das Kennwort für den Proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Port </p> </td> 
   <td colname="col2"> <p>Der Port des Proxyservers. Der Standardwert lautet 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Benutzername </p> </td> 
   <td colname="col2"> <p>Optional. Der Benutzername für den Proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durchsuchen </p> </td> 
   <td colname="col2"> <p>In der Datei <span class="filepath"> Insight.cfg</span> (oder einer beliebigen <span class="filepath"> .cfg</span>-Datei) können Sie nach Schlüsselname, Schlüsseltyp oder Wert suchen, um einen Eintrag schnell zu finden. So müssen Sie nicht für verschachtelte Informationen durch erweiterte, große Dateien blättern. Sie können Dimensionsnamen, Servernamen usw. suchen. </p> <p>Geben Sie einen Suchbegriff in dieses Feld ein, um die Daten zu suchen. Je nach Erfolg einer Übereinstimmung ändert sich die Farbe des Felds. Übereinstimmungen werden hervorgehoben und Nicht-Übereinstimmungen werden abgeblendet angezeigt. Wenn keine Treffer vorliegen, wird der Hintergrund des Suchfelds rot. Wenn Sie die Eingabetaste drücken, erweitert der Konfigurationsbaum jeden Ort, an dem eine Übereinstimmung vorliegt, und reduziert, wo keine Übereinstimmung vorliegt. </p> <p>Sie können auch reguläre Ausdrücke im Feld <span class="wintitle"> Suche</span> verwenden. Sie können beispielsweise Folgendes verwenden: <span class="filepath"> *zip.*</span> für jeden Eintrag, der das Wort "zip"enthält. </p> <p>Um eine Suche zu löschen, drücken Sie <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p>Vektorüberschrift für <span class="keyword"> Client</span> bis <span class="keyword"> Server</span>-Verbindungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-Client-Zertifikat </p> </td> 
   <td colname="col2"> <p>Optional, es sei denn, Sie verfügen über mehr als ein Zertifikat. Der Name der Datei, die das digitale Zertifikat für diese Kopie der Data Workbench enthält. Dies ist die Datei, die Sie unter Herunterladen und Installieren des digitalen Zertifikats heruntergeladen haben. </p> <p>Beispiel: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Wenn Sie diesen Parameter leer lassen, verwendet <span class="keyword"> der Client</span> das vorhandene Zertifikat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allgemeiner SSL-Server-Name </p> </td> 
   <td colname="col2"> <p>Der allgemeine Name des Data Workbench-Servers (wie auf seinem digitalen Zertifikat zugewiesen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Symbolleistensymbole </p> </td> 
   <td colname="col2"> <p>"False"deaktiviert die Symbole in der Benutzeroberfläche der Workstation und zeigt Text in der Symbolleiste an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adressendatei verwenden </p> </td> 
   <td colname="col2"> <p>Gibt an, ob Einstellungen in der Adressdatei die Einstellung des Adressparameters außer Kraft setzen. Die Optionen sind "true"oder "false". Wenn der Wert auf "true"gesetzt ist, überschreiben die Einstellungen in der Adressdatei (sofern vorhanden) die Einstellung für den Adressparameter . Der Standardwert ist "true". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL verwenden </p> </td> 
   <td colname="col2">Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und <span class="keyword"> dem Client</span> verwendet wird. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alle einblenden </p> </td> 
   <td colname="col2"> <p>Optional. Ermöglicht es Ihnen, alle Metriken, Dimensionen und Filter, die mit einer der folgenden Funktionen ausgeblendet wurden, vorübergehend wieder einzublenden: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[Ausschließliche] Einstellung in <span class="filepath"> order.txt</span> -Dateien </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Option ausblenden in <span class="filepath"> order.txt</span> -Dateien </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Parameter in den Dateien <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> und <span class="filepath"> .filter</span> anzeigen. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Ausgeblendeter Parameter in der Datei <span class="filepath"> Transformation.cfg</span> . </li> 
     </ul> </p> <p>Weitere Informationen zu diesen Methoden finden Sie unter <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Menüelement</a> ausblenden. </p> <p>Die Optionen sind "true"oder "false". Die Standardeinstellung ist "false". Ändern Sie diesen Parameter in true , um die Ausblendung von verborgenen Metriken, Dimensionen und Filtern vorübergehend aufzuheben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entsperren </p> </td> 
   <td colname="col2"> <p>Optional. Gibt an, ob Sie gesperrte Arbeitsbereiche entsperren dürfen. Die Optionen sind "true"und "false". Mit "True"können Sie gesperrte Arbeitsbereiche entsperren, während "false"dies nicht tut. Der Standardwert ist „false“. Weitere Informationen zu gesperrten Arbeitsbereichen finden Sie unter <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Entsperren eines Arbeitsbereichs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Software aktualisieren </p> </td> 
   <td colname="col2"> <p>Optional. Gibt an, ob diese <span class="keyword"> Client-Software vom Data Workbench-Server aktualisiert werden soll. </span> Die Optionen sind "true"oder "false". Der Standardwert ist "true". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzerordner </p> </td> 
   <td colname="col2"> <p>Optional. Gibt den Namen und Speicherort des Ordners an, der die lokalen Kopien aller Arbeitsbereiche, Metriken, Dimensionen oder Konfigurationsdateien für jedes Profil enthält. Die Standardeinstellung ist "Benutzer\\", die den Ordner "Benutzer"im Installationsordner der Data Workbench angibt. </p> <p>Eine Änderung dieser Einstellung ist nützlich, wenn zwei Benutzer denselben Computer gemeinsam nutzen. Um beide Benutzer aufzunehmen, können Sie einen freigegebenen Ordner angeben, auf den beide Benutzer Zugriff haben. </p> </td> 
  </tr> 
 </tbody> 
</table>
