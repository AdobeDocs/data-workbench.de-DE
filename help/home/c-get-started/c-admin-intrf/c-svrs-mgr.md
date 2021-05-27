---
description: Das primäre Tool, das von Systemadministratoren verwendet wird, ist der Server-Manager.
title: Server-Manager
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---

# Server-Manager{#servers-manager}

Das primäre Tool, das von Systemadministratoren verwendet wird, ist der Server-Manager.

Dies ist die wichtigste Schnittstelle zur Bestimmung des Gesamtsystemstatus und zur Durchführung von Systemkonfigurationen, Dateiverwaltung und Fehlerüberwachungsfunktionen.

Der Server-Manager zeigt für jeden Data Workbench-Server einen farbigen Punkt (Knoten) und eine [!DNL Sensor]-Installation in Ihrem System an und bietet einen Überblick über den Systemstatus für jede Installation. Es wird auch ein Knoten für Ihre Data Workbench-Installation angezeigt.

Grüne Knoten stellen aktive Verbindungen dar, rote Knoten stellen Verbindungen dar, die deaktiviert oder anderweitig nicht zugänglich sind, und graue Knoten stellen Verbindungen dar, deren Status unbestimmt ist.

![](assets/vis_SysStat_RedGreenDots.png)

Wenn Sie mit der rechten Maustaste auf einen Knoten klicken, werden Informationen zur Verbindungs-Komponente angezeigt und Sie erhalten Zugriff auf alle zugehörigen Menüs.

Die folgenden Tabellen beschreiben die Informationen, die bereitgestellt werden, wenn Sie mit der rechten Maustaste auf einen Knoten für Data Workbench, Data Workbench-Server (einschließlich eines Übergeordneten Data Workbench-Servers in einem Cluster) oder [!DNL Sensor] klicken.

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
   <td colname="col2"> <p>Produktname, Version und Build-Nummer. </p> <p>Beispiel: Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Data Workbench-Computers. </p> <p>Beispiel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren </p> </td> 
   <td colname="col2"> <p>Ein Link zur Konfigurationsdatei Ihrer <span class="keyword"> -Data Workbench </span>. Klicken Sie auf <span class="uicontrol"> </span> &gt; <span class="uicontrol"> Insight.cfg </span> konfigurieren , um das Konfigurationsfenster der Data Workbench anzuzeigen. Alle Änderungen, die Sie in diesem Fenster vornehmen und speichern, werden in der Datei <span class="filepath"> Insight.cfg </span> im Installationsverzeichnis Ihrer Data Workbench übernommen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktname, Version und Build-Nummer. </p> <p>Beispiel: Data Workbench-Server 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Der allgemeine Name des Data Workbench-Servercomputers. </p> <p>Beispiel: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>IP-Adresse oder vollständig qualifizierter Domänenname des Servers, wie in der Datei Adressen auf dem Computer konfiguriert, und der Parameter Netzwerkstandort in der Datei <span class="filepath"> Insight.cfg </span> . </p> <p>Beispiel: 100.0.0.1 </p> <p>Weitere Informationen zur Datei "Adressen"finden Sie im <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Aktueller Status des Data Workbench-Servers. Dieses Feld zeigt OK an, wenn der Data Workbench-Server normal ausgeführt wird. Wenn ein Fehler aufgetreten ist und der Data Workbench-Serverknoten rot ist, zeigt das Feld den Fehler an (z. B. "403 Verboten"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detaillierter Status </p> </td> 
   <td colname="col2"> <p>Ein Link zur <span class="keyword"> Data Workbench-Server </span> <span class="wintitle">-Oberfläche mit detailliertem Status </span>, die zur Fehlerbehebung bei Fehlern oder anderen Problemen mit dem Data Workbench-Server nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Die detaillierte Statusschnittstelle</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remote Desktop </p> </td> 
   <td colname="col2"> <p>Öffnet eine <span class="wintitle"> Remote Desktop </span>-Sitzung für den Data Workbench-Servercomputer. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Die Remote Desktop-Option </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverdateien </p> </td> 
   <td colname="col2"> <p>Ein Link zum <span class="wintitle"> Server Files Manager </span>, der die Ordner und Dateien im Installationsordner des Data Workbench-Servers anzeigt. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Der Server Files Manager </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Monitor </p> </td> 
   <td colname="col2"> <p>Ein Link zur Schnittstelle <span class="wintitle"> Server Monitor </span>, die für die Fehlerbehebung oder das Tracking von Leistungsparametern nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Server Monitor Interface </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verwandte Server </p> </td> 
   <td colname="col2"> <p>Nur für Data Workbench-Servercluster. </p> <p>Ein Menü, das die gebräuchlichen Namen der Computer auflistet, die in der Datei *.address </span> des Übergeordneten <span class="filepath">-Data Workbench-Servers aufgeführt sind. Diese Liste enthält in der Regel alle Verarbeitungsserver <span class="keyword"> für Data Workbenchs </span> im Cluster. Dieses Menü wird nur angezeigt, wenn die Data Workbench über eine Kopie der Übergeordneten Datei <span class="filepath"> *.address </span> des Data Workbench-Servers verfügt. </span></p> <p>Wenn Sie auf <span class="uicontrol"> Zugehörige Server </span> klicken, können Sie auf Folgendes klicken: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor List  </span>, in der die  <span class="wintitle"> Server Monitor- </span> Oberfläche mit Details für alle zugehörigen Server angezeigt wird </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Der allgemeine Name eines jeden Data Workbench-Servers, der ein Kontextmenü anzeigt, über das Sie Folgendes für diesen bestimmten Server öffnen können: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detaillierter Status  </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Die detaillierte Statusschnittstelle </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Remote Desktop  </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Remote Desktop Option </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server-Datei-Manager </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Server-Datei-Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor  </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Server Monitor Interface </a>. </li> 
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
   <td colname="col2"> <p>Produktname, Version und Build-Nummer. </p> <p>Beispiel: Sensor 3.76; J 3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> Die ID <span class="wintitle"> Sensor </span>, die in der Konfigurationsdatei <span class="wintitle"> Sensor </span> für diese Installation angegeben ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Web- oder Anwendungsservers, auf dem <span class="wintitle"> Sensor </span> installiert ist. </p> <p>Beispiel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>Vom Betriebssystem zugewiesene Prozess-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Ob <span class="wintitle"> Sensor </span> und der Data Workbench-Server über SSL kommunizieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zeit </p> </td> 
   <td colname="col2"> <p>Zeit (HH:MM:SS) dass der Sensor <span class="wintitle"> </span> zuletzt eine Verbindung zum Data Workbench-Server hergestellt hat. </p> </td> 
  </tr> 
 </tbody> 
</table>
