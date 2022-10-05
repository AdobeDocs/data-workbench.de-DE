---
description: Das primäre Tool, das von Systemadministratoren verwendet wird, ist der Server-Manager.
title: Server-Manager
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Server-Manager{#servers-manager}

{{eol}}

Das primäre Tool, das von Systemadministratoren verwendet wird, ist der Server-Manager.

Dies ist die wichtigste Schnittstelle zur Bestimmung des Gesamtsystemstatus und zur Durchführung von Systemkonfigurationen, Dateiverwaltung und Fehlerüberwachungsfunktionen.

Der Server-Manager zeigt für jeden Data Workbench-Server einen farbigen Punkt (Knoten) an und [!DNL Sensor] -Installation in Ihrem System und bietet einen Überblick über den Systemstatus für jede Installation. Es wird auch ein Knoten für Ihre Data Workbench-Installation angezeigt.

Grüne Knoten stellen aktive Verbindungen dar, rote Knoten stellen Verbindungen dar, die deaktiviert oder anderweitig nicht zugänglich sind, und graue Knoten stellen Verbindungen dar, deren Status unbestimmt ist.

![](assets/vis_SysStat_RedGreenDots.png)

Wenn Sie mit der rechten Maustaste auf einen Knoten klicken, werden Informationen zur Verbindungs-Komponente angezeigt und Sie erhalten Zugriff auf alle zugehörigen Menüs.

Die folgenden Tabellen beschreiben die Informationen, die bereitgestellt werden, wenn Sie mit der rechten Maustaste auf einen Knoten für die Data Workbench oder den Data Workbench-Server (einschließlich eines Übergeordneten Data Workbench-Servers in einem Cluster) klicken, oder [!DNL Sensor].

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
   <td colname="col2"> <p>IP-Adresse des Data Workbench-Computers. </p> <p>Beispiel: 100,0,0,1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurieren </p> </td> 
   <td colname="col2"> <p>Ein Link zu Ihrer <span class="keyword"> Data Workbench </span> Konfigurationsdatei. Klicken <span class="uicontrol"> Konfigurieren </span> &gt; <span class="uicontrol"> Insight.cfg </span> , um das Konfigurationsfenster der Data Workbench anzuzeigen. Alle Änderungen, die Sie in diesem Fenster vornehmen und speichern, werden im <span class="filepath"> Insight.cfg </span> in Ihrem Installationsverzeichnis der Data Workbench. </p> </td> 
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
   <td colname="col2"> <p>IP-Adresse oder vollständig qualifizierter Domänenname des Servers, wie in der Datei "Adressen"auf dem Computer konfiguriert, und im Parameter "Netzwerkstandort"im <span class="filepath"> Insight.cfg </span> -Datei. </p> <p>Beispiel: 100,0,0,1 </p> <p>Weitere Informationen zur Datei "Adressen"finden Sie unter <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Aktueller Status des Data Workbench-Servers. Dieses Feld zeigt OK an, wenn der Data Workbench-Server normal ausgeführt wird. Wenn ein Fehler aufgetreten ist und der Data Workbench-Serverknoten rot ist, zeigt das Feld den Fehler an (z. B. "403 Verboten"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detaillierter Status </p> </td> 
   <td colname="col2"> <p>Ein Link zum <span class="keyword"> Data Workbench-Server </span> <span class="wintitle"> Detaillierter Status </span> -Schnittstelle, die zur Fehlerbehebung bei Fehlern oder anderen Problemen mit dem Data Workbench-Server nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Die detaillierte Statusschnittstelle</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remote Desktop </p> </td> 
   <td colname="col2"> <p>Öffnet eine <span class="wintitle"> Remote Desktop </span> -Sitzung auf den Data Workbench-Server-Computer. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Die Remote Desktop-Option </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverdateien </p> </td> 
   <td colname="col2"> <p>Ein Link zum <span class="wintitle"> Server Files Manager </span>, der die Ordner und Dateien im Installationsordner des Data Workbench-Servers anzeigt. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Der Server Files Manager </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Monitor </p> </td> 
   <td colname="col2"> <p>Ein Link zum <span class="wintitle"> Server Monitor </span> -Schnittstelle, die für die Fehlerbehebung oder das Tracking von Leistungsparametern nützlich ist. </p> <p>Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Die Server-Monitor-Oberfläche </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verwandte Server </p> </td> 
   <td colname="col2"> <p>Nur für Data Workbench-Servercluster. </p> <p>Ein Menü, in dem die gebräuchlichen Computer aufgelistet werden, die im Übergeordneten <span class="filepath"> *.address des Data Workbench-Servers </span> -Datei. Diese Liste enthält normalerweise die gesamte Verarbeitung <span class="keyword"> Data Workbench-Server </span> im Cluster. Dieses Menü wird nur angezeigt, wenn die Data Workbench über eine Kopie des Übergeordneten verfügt <span class="filepath"> *.address des Data Workbench-Servers </span> -Datei. </p> <p>Wenn Sie auf <span class="uicontrol"> Verwandte Server </span>können Sie auf Folgendes klicken: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor List </span>, der die <span class="wintitle"> Server Monitor </span> Benutzeroberfläche mit Details für alle zugehörigen Server </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Der allgemeine Name eines jeden Data Workbench-Servers, der ein Kontextmenü anzeigt, über das Sie Folgendes für diesen bestimmten Server öffnen können: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detaillierter Status </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Die detaillierte Statusschnittstelle </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Remote Desktop </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Die Remote Desktop-Option </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server-Datei-Manager </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Der Server Files Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor </span>. Siehe <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Die Server-Monitor-Oberfläche </a>. </li> 
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
   <td colname="col2"> Die <span class="wintitle"> Sensor </span> Die in der Variablen <span class="wintitle"> Sensor </span> Konfigurationsdatei für diese Installation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP-Adresse des Web- oder Anwendungsservers, auf dem <span class="wintitle"> Sensor </span> installiert ist. </p> <p>Beispiel: 100,0,0,1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>Vom Betriebssystem zugewiesene Prozess-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Ob <span class="wintitle"> Sensor </span> und der Data Workbench-Server kommunizieren mithilfe von SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zeit </p> </td> 
   <td colname="col2"> <p>Zeit (HH:MM:SS) die <span class="wintitle"> Sensor </span> zuletzt eine Verbindung zum Data Workbench-Server hergestellt. </p> </td> 
  </tr> 
 </tbody> 
</table>
