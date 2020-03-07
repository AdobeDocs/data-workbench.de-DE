---
description: Das Hauptwerkzeug, das Systemadministratoren verwenden, ist der Server Manager.
solution: Analytics
title: Server Manager
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Server Manager{#servers-manager}

Das Hauptwerkzeug, das Systemadministratoren verwenden, ist der Server Manager.

Es ist die wichtigste Schnittstelle zur Bestimmung des Gesamtstatus des Systems und zur Durchführung von Systemkonfigurationen, Dateiverwaltung und Fehlerüberwachung.

Der Server Manager zeigt für jeden Data Workbench-Server und jede Installation in Ihrem System einen farbigen Punkt (Knoten) an und bietet einen Überblick über den Systemstatus für jede Installation. [!DNL Sensor] Es wird auch ein Knoten für Ihre Data Workbench-Installation angezeigt.

Grüne Knoten stellen aktive Verbindungen dar, rote Knoten stellen Verbindungen dar, die deaktiviert sind oder anderweitig nicht zugänglich sind, und graue Knoten stellen Verbindungen dar, deren Status unbestimmt ist.

![](assets/vis_SysStat_RedGreenDots.png)

Wenn Sie mit der rechten Maustaste auf eine Node klicken, werden Informationen zur Verbindungskomponente angezeigt und Sie erhalten Zugriff auf alle zugehörigen Menüs.

Die folgenden Tabellen beschreiben die Informationen, die bereitgestellt werden, wenn Sie mit der rechten Maustaste auf einen Knoten für Data Workbench, Data Workbench-Server (einschließlich eines Master-Data Workbench-Servers in einem Cluster) oder [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Buildnummer. </p> <p>Beispiel: Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Data Workbench-Computers. </p> <p>Beispiel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren </p> </td> 
   <td colname="col2"> <p>Ein Link zur <span class="keyword"> Konfigurationsdatei Ihrer </span> Data Workbench. Klicken Sie auf <span class="uicontrol"> Konfigurieren </span> &gt; <span class="uicontrol"> Insight.cfg, </span> um das Konfigurationsfenster von Data Workbench anzuzeigen. Änderungen, die Sie in diesem Fenster vornehmen und speichern, werden in der Datei <span class="filepath"> Insight.cfg </span> im Installationsordner von Data Workbench übernommen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Buildnummer. </p> <p>Beispiel: Data Workbench Server 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Der allgemeine Name des Data Workbench-Servercomputers. </p> <p>Beispiel: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>IP-Adresse oder vollständig qualifizierter Domänenname des Servers, wie in der Datei Adressen auf dem Computer und im Parameter Netzwerkspeicherort in der <span class="filepath"> Datei Insight.cfg </span> konfiguriert. </p> <p>Beispiel: 100.0.0.1 </p> <p>Informationen zur Datei "Adressen"finden Sie im <i>Serverprodukte-Installations- und Administrationshandbuch</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Aktueller Status des Data Workbench-Servers. Dieses Feld zeigt OK an, wenn der Data Workbench-Server normal ausgeführt wird. Wenn ein Fehler aufgetreten ist und der Data Workbench-Server-Knoten rot ist, zeigt das Feld den Fehler an (z. B. "403 Verboten"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detaillierter Status </p> </td> 
   <td colname="col2"> <p>Ein Link zur <span class="keyword"> Data Workbench-Server-Oberfläche </span> mit detailliertem Status, die zur Fehlerbehebung oder zur Behebung anderer Probleme mit dem Data Workbench-Server nützlich <span class="wintitle"> </span> ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Detaillierte Statusschnittstelle</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remote Desktop </p> </td> 
   <td colname="col2"> <p>Öffnet eine <span class="wintitle"> Remote Desktop- </span> Sitzung auf dem Data Workbench-Servercomputer. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Option "Remote-Desktop" </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverdateien </p> </td> 
   <td colname="col2"> <p>Ein Link zum <span class="wintitle"> Server Files Manager </span>, der die Ordner und Dateien im Installationsordner des Data Workbench-Servers anzeigt. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Server Files Manager </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Monitor </p> </td> 
   <td colname="col2"> <p>Ein Link zur <span class="wintitle"> Server Monitor- </span> Oberfläche, der zur Fehlerbehebung oder Verfolgung von Leistungsparametern nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Die Server-Monitorschnittstelle </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verwandte Server </p> </td> 
   <td colname="col2"> <p>Nur für Data Workbench-Servercluster. </p> <p>Ein Menü, das die gebräuchlichen Namen der Computer auflistet, die in der *.address-Datei des Master- <span class="filepath"> Data Workbench-Servers aufgeführt </span> sind. Diese Liste umfasst in der Regel alle verarbeitenden <span class="keyword"> Data Workbench-Server </span> im Cluster. Dieses Menü wird nur angezeigt, wenn Data Workbench über eine Kopie der *.address-Datei des Master- <span class="filepath"> Data Workbench-Servers verfügt </span> . </p> <p>Wenn Sie auf <span class="uicontrol"> Verwandte Server klicken </span>Sie auf: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor List </span>, in der die <span class="wintitle"> Server Monitor- </span> Oberfläche mit Details zu allen zugehörigen Servern angezeigt wird </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Der allgemeine Name eines Data Workbench-Servers, der ein Kontextmenü anzeigt, mit dem Sie einen der folgenden Schritte für diesen bestimmten Server öffnen können: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detaillierter Status </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Detaillierte Statusschnittstelle </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Remote Desktop </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Option "Remote-Desktop" </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server Files Manager </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Server Files Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Server Monitor Interface </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Buildnummer. </p> <p>Beispiel: Sensor 3.76; J 3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> Die <span class="wintitle"> Sensor- </span> ID, die in der <span class="wintitle"> Sensor- </span> Konfigurationsdatei für diese Installation angegeben ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Web- oder Anwendungsservers, auf dem <span class="wintitle"> Sensor installiert </span> ist. </p> <p>Beispiel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>Prozess-ID, die vom Betriebssystem zugewiesen wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Gibt an, ob <span class="wintitle"> Sensor </span> und der Data Workbench-Server mit SSL kommunizieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zeit </p> </td> 
   <td colname="col2"> <p>Zeit (HH:MM:SS), dass der <span class="wintitle"> Sensor </span> zuletzt eine Verbindung mit dem Data Workbench-Server hergestellt hat. </p> </td> 
  </tr> 
 </tbody> 
</table>
