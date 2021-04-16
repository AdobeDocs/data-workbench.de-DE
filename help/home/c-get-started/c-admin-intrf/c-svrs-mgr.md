---
description: Das Hauptwerkzeug, das Systemadministratoren verwenden, ist der Server Manager.
title: Server-Manager
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---

# Server-Manager{#servers-manager}

Das Hauptwerkzeug, das Systemadministratoren verwenden, ist der Server Manager.

Es ist die wichtigste Schnittstelle zur Bestimmung des Gesamtstatus des Systems und zur Durchführung von Systemkonfigurationen, Dateiverwaltung und Fehlerüberwachung.

Der Server Manager zeigt einen farbigen Punkt (Knoten) für jeden Data Workbench-Server und [!DNL Sensor]-Installationsordner in Ihrem System an und stellt einen Überblick über den Systemstatus für jede Installation bereit. Es wird auch ein Knoten für die Installation der Data Workbench angezeigt.

Grüne Knoten stellen aktive Verbindungen dar, rote Knoten stellen Verbindungen dar, die deaktiviert sind oder anderweitig nicht zugänglich sind, und graue Knoten stellen Verbindungen dar, deren Status unbestimmt ist.

![](assets/vis_SysStat_RedGreenDots.png)

Wenn Sie mit der rechten Maustaste auf eine Node klicken, werden Informationen zur Verbindungskomponente angezeigt und Sie erhalten Zugriff auf alle zugehörigen Menüs.

Die folgenden Tabellen beschreiben die Informationen, die bereitgestellt werden, wenn Sie mit der rechten Maustaste auf einen Knoten für Data Workbench, Data Workbench-Server (einschließlich eines Übergeordnet-Data Workbench-Servers in einem Cluster) oder [!DNL Sensor] klicken.

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Buildnummer. </p> <p>Beispiel: Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Data Workbench-Computers. </p> <p>Beispiel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren </p> </td> 
   <td colname="col2"> <p>Ein Link zur Konfigurationsdatei Ihrer <span class="keyword">-Data Workbench </span>. Klicken Sie auf <span class="uicontrol"> </span> &gt; <span class="uicontrol"> Insight.cfg </span> konfigurieren, um das Konfigurationsfenster der Data Workbench anzuzeigen. Änderungen, die Sie in diesem Fenster vornehmen und speichern, werden in der Datei <span class="filepath"> Insight.cfg </span> im Installationsordner Ihrer Data Workbench übernommen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Buildnummer. </p> <p>Beispiel: Data Workbench Server 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Der allgemeine Name des Data Workbench-Servercomputers. </p> <p>Beispiel: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>IP-Adresse oder vollständig qualifizierter Domänenname des Servers, wie er in der Datei Adressen auf dem Computer und im Parameter Netzwerkspeicherort in der Datei <span class="filepath"> Insight.cfg </span> konfiguriert ist. </p> <p>Beispiel: 100.0.0.1 </p> <p>Weitere Informationen zur Datei "Adressen"finden Sie im <i>Serverprodukte - Installations- und Administrationshandbuch</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Aktueller Status des Data Workbench-Servers. Dieses Feld zeigt OK an, wenn der Data Workbench-Server normal ausgeführt wird. Wenn ein Fehler aufgetreten ist und der Serverknoten der Data Workbench rot ist, zeigt das Feld den Fehler an (z. B. "403 Verboten"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detaillierter Status </p> </td> 
   <td colname="col2"> <p>Ein Link zur <span class="keyword">-Data Workbench-Server </span> <span class="wintitle">-Schnittstelle mit Detailliertem Status </span>, die zur Fehlerbehebung von Fehlern oder anderen Problemen mit dem Data Workbench-Server nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Die detaillierte Statusschnittstelle</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remote Desktop </p> </td> 
   <td colname="col2"> <p>Öffnet eine <span class="wintitle"> Remote Desktop </span>-Sitzung auf dem Data Workbench-Servercomputer. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Die Remote-Desktop-Option </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverdateien </p> </td> 
   <td colname="col2"> <p>Ein Link zum <span class="wintitle">-Server-Dateimanager </span>, der die Ordner und Dateien im Installationsordner des Data Workbench-Servers anzeigt. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Der Server Files Manager </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Monitor </p> </td> 
   <td colname="col2"> <p>Eine Verknüpfung zur Oberfläche <span class="wintitle"> Server Monitor </span>, die zur Fehlerbehebung oder Verfolgung von Leistungsparametern nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Die Server-Monitorschnittstelle </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verwandte Server </p> </td> 
   <td colname="col2"> <p>Nur für Data Workbench-Server-Cluster. </p> <p>Ein Menü, das die gebräuchlichen Computernamen Liste, die in der Übergeordnete <span class="filepath"> des Data Workbench-Servers *.address </span> aufgeführt sind. Diese Liste umfasst in der Regel alle Verarbeitungsserver <span class="keyword"> der Data Workbench </span> im Cluster. Dieses Menü wird nur angezeigt, wenn die Data Workbench eine Kopie der Übergeordnet <span class="filepath">-Data Workbench-Server-Datei *.address </span> enthält. </p> <p>Wenn Sie auf <span class="uicontrol"> Verwandte Server </span> klicken, können Sie auf Folgendes klicken: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor-Liste  </span>, in der die  <span class="wintitle"> Server Monitor- </span> Benutzeroberfläche mit Details zu allen zugehörigen Servern angezeigt wird </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Der gebräuchliche Name eines Serverservers, der ein Kontextmenü anzeigt, mit dem Sie einen der folgenden Data Workbenchs für den jeweiligen Server öffnen können: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detaillierter Status  </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Die detaillierte Statusschnittstelle </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Remote Desktop  </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Die Remote-Desktop-Option </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server-Datei-Manager </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Der Server Files Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor  </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Die Server-Monitorschnittstelle </a>. </li> 
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
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Buildnummer. </p> <p>Beispiel: Sensor 3.76; J 3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> Die <span class="wintitle"> Sensor </span>-ID, die in der Konfigurationsdatei <span class="wintitle"> Sensor </span> für diese Installation angegeben ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Web- oder Anwendungsservers, auf dem <span class="wintitle"> Sensor </span> installiert ist. </p> <p>Beispiel: 100.0.0.1 </p> </td> 
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
