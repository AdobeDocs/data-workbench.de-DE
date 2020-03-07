---
description: Die Benutzeroberfläche "Server Monitor"eignet sich zur Fehlerbehebung oder einfachen Verfolgung der Leistungsparameter von Data Workbench-Servercomputern und Berichtscomputern, die Clients von Data Workbench-Servercomputern sind.
solution: Analytics
title: Server Monitor-Benutzeroberfläche
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server Monitor-Benutzeroberfläche{#server-monitor-interface}

Die Benutzeroberfläche &quot;Server Monitor&quot;eignet sich zur Fehlerbehebung oder einfachen Verfolgung der Leistungsparameter von Data Workbench-Servercomputern und Berichtscomputern, die Clients von Data Workbench-Servercomputern sind.

In der Benutzeroberfläche des Serverbildschirms wird oben links neben dem Computernamen entweder ein grüner Punkt oder ein roter Punkt angezeigt. Ein grüner Punkt zeigt an, dass der Computer fehlerfrei funktioniert. Ein roter Punkt zeigt an, dass auf dem Computer ein oder mehrere Fehler aufgetreten sind.

Im unteren Bereich der Benutzeroberfläche des Server-Monitors werden der Verarbeitungsstatus der einzelnen verfügbaren Profile sowie Leistungsdetails zum Computer aufgeführt.

Weitere Informationen finden Sie [!DNL Data Workbench servers]im *Serverprodukt-Installations- und Administrationshandbuch*. Weitere Informationen finden Sie [!DNL Report]im *Data Workbench Report Guide*.

**So öffnen Sie die Oberfläche des Server-Monitors**

* Klicken Sie im Server Manager mit der rechten Maustaste auf den Knoten des Data Workbench-Servers oder - [!DNL Report] Computers. t

Klicken Sie auf **[!UICONTROL Server Monitor]** , um Details zu einem Server anzuzeigen, oder klicken Sie auf **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** , um Details zu einem Cluster verwandter Server anzuzeigen.

![](assets/vis_ServerMonitor.png)

Die [!DNL Server Monitor]Oberfläche wird alle 10 Sekunden automatisch aktualisiert.

In der folgenden Tabelle sind die Aufgaben aufgeführt, die über die [!DNL Server Monitor] Oberfläche ausgeführt werden können.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
   <th colname="col2" class="entry"> gehen Sie wie folgt vor: </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So prüfen Sie den Protokollverarbeitungsstatus eines Profils </p> </td> 
   <td colname="col2"> <p>Zeigen Sie den <i>Profilnamen</i> -Vektor an. Im obigen Beispiel würden Sie den ProfilbeispielProfile-Vektor anzeigen, um zu sehen, dass das ExampleProfile-Profil auf einem Server verarbeitet wird und die Protokollverarbeitung zu 100 % abgeschlossen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie, wie lange der Computer braucht, um auf Anforderungen zu reagieren </p> </td> 
   <td colname="col2"> <p>Zeigen Sie das Feld für die Umfragelatenz an. Wenn dieser Wert größer als 1000 ms ist, wenden Sie sich an den Adobe Support Services. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie eine Schätzung an, wie lange es dauern kann, die Transformation oder Abfrage abzuschließen </p> </td> 
   <td colname="col2"> <p>Zeigen Sie das Feld "Sweep Time"(hh:mm:ss) an, das nur während der Transformation oder Abfrage vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So ermitteln Sie die aktuelle Anzahl der Netzwerkverbindungen zum Computer </p> </td> 
   <td colname="col2"> <p>Zeigen Sie die letzte Zeile der Serverüberwachungsinformationen des Computers <span class="wintitle"> an</span> . Im obigen Beispiel sehen Sie, dass derzeit zwei Netzwerkverbindungen von einem Computer stammen. </p> </td> 
  </tr> 
 </tbody> 
</table>

