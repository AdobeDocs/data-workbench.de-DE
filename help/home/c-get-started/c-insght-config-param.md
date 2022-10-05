---
description: Legen Sie die Parameter in der Datei Insight.cfg fest, um die Konfigurationseinstellungen für die Netzwerkverbindung und Data Workbench festzulegen.
title: Konfigurationsparameter
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Konfigurationsparameter{#configuration-parameters}

{{eol}}

Legen Sie die Parameter in der Datei Insight.cfg fest, um die Konfigurationseinstellungen für die Netzwerkverbindung und Data Workbench festzulegen.

Das folgende Beispiel enthält nur die Parameter, die im [!DNL Insight.cfg] -Datei.

**Neue Layoutansicht**

![](assets/config_tree_new_layout.png)

**Ansicht &quot;Original Layout&quot;**

![](assets/cfg_Workstation_AddServer.png)

Einige der in der neuen [!DNL Insight.cfg] in Ihrer Version der [!DNL Insight.cfg] -Datei. Wenn einer dieser Parameter benötigt wird, müssen Sie ihn zum [!DNL Insight.cfg] Datei verwenden [!DNL Add Custom Key], indem Sie mit der rechten Maustaste auf einen Parameter klicken und dann den Namen und den Typ angeben. Sie können auch Parameter hinzufügen, indem Sie die [!DNL .cfg] -Datei (die sich im Installationsverzeichnis der Data Workbench befindet) mithilfe eines Texteditors.

Im Folgenden finden Sie ein Beispiel aller Parameter, die für die [!DNL Insight.cfg] -Datei, die Sie als Modell zum Hinzufügen von Parametereinträgen verwenden können:

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

Die folgende Tabelle enthält Beschreibungen der verfügbaren [!DNL Insight.cfg] -Dateiparameter in alphabetischer Reihenfolge.

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
   <td colname="col2"> <p>Der Hostname oder die numerische IP-Adresse Ihres Data Workbench-Servercomputers. </p> <p>Beispiel: <span class="filepath"> vsServer.mycompany.com oder 192.168.1.90</span> </p> <p>Wenn <span class="wintitle"> Adresse</span> nicht angegeben ist, <span class="keyword"> Client</span> verwendet den allgemeinen Namen, der im Parameter "SSL Server Common Name"angegeben ist, wenn "Use Address File"auf "false"gesetzt ist. </p> <p> <p>Hinweis: Wenn der Parameter "Use Address File"auf "true"gesetzt ist, kann der im Parameter "Address"eingegebene Text entfernt werden, nachdem das erste Profil am <span class="keyword"> Client</span>. Anschließend bestimmt die Einstellung für den Netzwerkstandortparameter, welche Adressen aus der Adressdatei des Clusters zum Herstellen einer Verbindung zum Übergeordneten Server verwendet werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Farbset </p> </td> 
   <td colname="col2"> <p>Gibt die Hintergrundfarbe Ihrer <span class="keyword"> Clientanwendung</span>. Die Optionen lauten wie folgt: </p> <p>0 = schwarz </p> <p>1 = weiß </p> <p>2 = monochrome </p> <p>Der Standardwert ist 0, schwarz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardebene Online-Ebene </p> </td> 
   <td colname="col2"> <p>Optional. Ermöglicht es Ihnen, Ihre Data Workbench-Instanz standardmäßig bei jeder Öffnung als Streaming, offline oder online zu verwenden. Die Optionen sind Streaming, Online oder Offline. Die Standardkonfiguration für die Data Workbench besteht darin, offline zu arbeiten. </p> <p> <p>Hinweis: Bevor Sie sich dafür entscheiden, standardmäßig online zu arbeiten, achten Sie darauf, die in <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Offline und online arbeiten</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schriftarten </p> </td> 
   <td colname="col2"> <p>Optional. Vektor, der die Schriften auflistet, die <span class="keyword"> Client</span> sollte zum Rendern von UTF8-basierten Unicode-Sonderzeichen verwendet werden. Die Anzahl der Schriftarten in der Liste ist unbegrenzt. </p> <p>Die erste Schriftart sollte immer Lucida Sans Console sein. Wenn dieser Parameter nicht im <span class="filepath"> Insight.cfg</span> -Datei, verwendet Data Workbench nur die Lucida Sans-Konsole, um Text anzuzeigen. </p> <p> Data Workbench verwendet die erste Schriftart in der Liste, um alle Zeichen zu rendern, bis ein Zeichen gefunden wird, das nicht gerendert werden kann. Es verwendet die zweite Schriftart in der Liste, um dieses Zeichen zu rendern. Wenn diese Schrift das Zeichen nicht rendert, verwendet Data Workbench die dritte Schrift in der Liste, um dieses Zeichen usw. zu rendern, bis es das Ende der Schriftartenliste erreicht. Wenn die richtige Schriftart nicht im Vektor aufgeführt ist, zeigt Data Workbench den Hexadezimalwert für das Zeichen an. </p> <p> <p>Hinweis: Ändern Sie diesen Parameter nicht, während die Data Workbench ausgeführt wird. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Gamma-Einstellung für die Anzeige der Data Workbench. Der Standardwert ist 1.6. Es wird von Adobe nicht empfohlen, diesen Wert zu ändern. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lizenzierung </p> </td> 
   <td colname="col2"> <p>Optional. Sie müssen die Parameter im Lizenzvektor nur ändern, wenn Sie den Lizenzserver von Adobe über einen Proxyserver kontaktieren. </p> <p>Bereichs-ID für Parameter, die Ihre <span class="keyword"> client</span> , um den Adobe License Server über einen Proxyserver zu kontaktieren. Erweitern Sie den Knoten Lizenzierung und füllen Sie die folgenden Parameter aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Adresse </p> </td> 
   <td colname="col2"> <p>Optional. Die Adresse des Proxyservers, <span class="keyword"> client</span> muss für den Zugriff auf den Adobe License Server verwendet werden. </p> </td> 
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
   <td colname="col2"> <p>Gibt die maximal zulässige Größe im Daten-Cache an, der von <span class="keyword"> Client</span> auf einem einzelnen Computer ausgeführt werden. </p> <p>Während der Parameter "Sample Bytes"im <span class="filepath"> Server.cfg</span> -Datei gibt die Größe des Daten-Cache für alle an <span class="keyword"> Clients</span> Wenn Sie eine Verbindung zu einem Data Workbench-Server herstellen (standardmäßig 250e6 Byte), können Sie mit dem Parameter Maximale Stichprobengröße die Datencache-Größe für einen bestimmten  weiter einschränken. Dies ist nützlich, wenn der Client auf einem Computer mit begrenzter Speicher- oder Rechenleistung installiert ist. </p> <p> <p>Hinweis: Dieser Parameter begrenzt die Größe eines lokalen Datenbeispiels, das vom Clientprogramm lokal abgefragt wird. Im Gegensatz dazu wird die Variable <span class="filepath"> cache.db</span> -Datei enthält Daten zu jedem Profil, mit dem der Client eine Verbindung herstellt, sowie die Elementnamen und ihre Dimensionen. Diese Elementnamen und -dimensionen in <span class="filepath"> cache.db</span> -Dateien erforderlich sind, um lokale Abfragen auszuführen. Daher gibt es keine andere Möglichkeit, die Größe zu begrenzen, als die Anzahl der Elemente im Datensatz zu reduzieren. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2">Optional. Der Name, der <span class="keyword"> Client</span> verwendet, um die <span class="keyword"> server</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Netzwerkstandort </p> </td> 
   <td colname="col2"> <p>Optional. Der Netzwerkspeicherort, unter dem <span class="keyword"> client</span> verwendet , um den gemeinsamen Namen des Data Workbench-Servers in eine IP-Adresse aufzulösen. Die verfügbaren Netzwerkspeicherorte werden in der Adressdatei auf dem Server definiert. Weitere Informationen finden Sie unter <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> <p>Wenn Sie keinen Netzwerkspeicherort angeben, <span class="keyword"> client</span> löst allgemeine Namen mithilfe des standardmäßigen Netzwerkspeicherorts "Insight"auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port </p> </td> 
   <td colname="col2"> <p>Der Anschluss, an den <span class="keyword"> Client</span> sendet Anfragen. Diese Anschlussnummer muss mit dem Anschluss übereinstimmen, an dem der Data Workbench-Server auf Anfragen wartet. Dies ist normalerweise 443 für sichere Verbindungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy-Adresse </p> </td> 
   <td colname="col2"> <p>Wenn ein Proxy-Server für die Verbindung mit Ihren Data Workbench-Servercomputern erforderlich ist, müssen Sie mindestens diesen Parameter und den Proxy-Port-Parameter angeben. Sie können optional die Parameter Proxy-Benutzername und Proxy-Benutzerkennwort eingeben. </p> <p>Die Adresse des Proxyservers, <span class="keyword"> Client</span> muss für den Zugriff auf den Data Workbench-Server verwendet werden. </p> </td> 
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
   <td colname="col2"> <p>Im <span class="filepath"> Insight.cfg</span> (oder <span class="filepath"> .cfg</span> -Datei) können Sie nach Schlüsselname, Schlüsseltyp oder Wert suchen, um einen Eintrag schnell zu finden, sodass Sie nicht durch erweiterte, große Dateien für verschachtelte Informationen blättern müssen. Sie können Dimensionsnamen, Servernamen usw. suchen. </p> <p>Geben Sie einen Suchbegriff in dieses Feld ein, um die Daten zu suchen. Je nach Erfolg einer Übereinstimmung ändert sich die Farbe des Felds. Übereinstimmungen werden hervorgehoben und Nicht-Übereinstimmungen werden abgeblendet angezeigt. Wenn keine Treffer vorliegen, wird der Hintergrund des Suchfelds rot. Wenn Sie die Eingabetaste drücken, erweitert der Konfigurationsbaum jeden Ort, an dem eine Übereinstimmung vorliegt, und reduziert, wo keine Übereinstimmung vorliegt. </p> <p>Sie können auch reguläre Ausdrücke im <span class="wintitle"> Suche</span> -Feld. Sie können beispielsweise Folgendes verwenden: <span class="filepath"> *zip.*</span> für jeden Eintrag, der das Wort "zip"enthält. </p> <p>Um eine Suche zu löschen, drücken Sie die <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p>Vektorüberschrift für <span class="keyword"> client</span> nach <span class="keyword"> server</span> Verbindungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-Client-Zertifikat </p> </td> 
   <td colname="col2"> <p>Optional, es sei denn, Sie verfügen über mehr als ein Zertifikat. Der Name der Datei, die das digitale Zertifikat für diese Kopie der Data Workbench enthält. Dies ist die Datei, die Sie unter Herunterladen und Installieren des digitalen Zertifikats heruntergeladen haben. </p> <p>Beispiel: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Wenn Sie diesen Parameter leer lassen, <span class="keyword"> Client</span> verwendet das vorhandene Zertifikat. </p> </td> 
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
   <td colname="col2">Gibt an, ob SSL für die sichere Kommunikation zwischen dem Data Workbench-Server und <span class="keyword"> Client</span>. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alle einblenden </p> </td> 
   <td colname="col2"> <p>Optional. Ermöglicht es Ihnen, alle Metriken, Dimensionen und Filter, die mit einer der folgenden Funktionen ausgeblendet wurden, vorübergehend wieder einzublenden: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">Einstellung [exklusiv] in <span class="filepath"> order.txt</span> files </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Option "Ausblenden"in <span class="filepath"> order.txt</span> files </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Parameter anzeigen in <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>und <span class="filepath"> .filter</span> Dateien. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Ausgeblendeter Parameter in <span class="filepath"> Transformation.cfg</span> -Datei. </li> 
     </ul> </p> <p>Weitere Informationen zu diesen Methoden finden Sie unter <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Ausblenden von Menüelementen</a>. </p> <p>Die Optionen sind "true"oder "false". Die Standardeinstellung ist "false". Ändern Sie diesen Parameter in true , um die Ausblendung von verborgenen Metriken, Dimensionen und Filtern vorübergehend aufzuheben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entsperren </p> </td> 
   <td colname="col2"> <p>Optional. Gibt an, ob Sie gesperrte Arbeitsbereiche entsperren dürfen. Die Optionen sind "true"und "false". Mit "True"können Sie gesperrte Arbeitsbereiche entsperren, während "false"dies nicht tut. Der Standardwert ist „false“. Weitere Informationen zu gesperrten Arbeitsbereichen finden Sie unter <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Entsperren eines Arbeitsbereichs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Software aktualisieren </p> </td> 
   <td colname="col2"> <p>Optional. Gibt an, ob dies zulässig ist <span class="keyword"> die </span>Client-Software, die vom Data Workbench-Server aktualisiert werden soll. Die Optionen sind "true"oder "false". Der Standardwert ist "true". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzerordner </p> </td> 
   <td colname="col2"> <p>Optional. Gibt den Namen und Speicherort des Ordners an, der die lokalen Kopien aller Arbeitsbereiche, Metriken, Dimensionen oder Konfigurationsdateien für jedes Profil enthält. Die Standardeinstellung ist "Benutzer\\", die den Ordner "Benutzer"im Installationsordner der Data Workbench angibt. </p> <p>Eine Änderung dieser Einstellung ist nützlich, wenn zwei Benutzer denselben Computer gemeinsam nutzen. Um beide Benutzer aufzunehmen, können Sie einen freigegebenen Ordner angeben, auf den beide Benutzer Zugriff haben. </p> </td> 
  </tr> 
 </tbody> 
</table>
