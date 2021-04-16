---
description: Die Benutzeroberfläche "Server Monitor"eignet sich zur Fehlerbehebung oder einfach zur Verfolgung der Leistungsparameter von Data Workbench-Servercomputern und Berichtscomputern, die Clients von Data Workbench-Servercomputern sind.
title: Oberfläche für die Server-Überwachung
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Oberfläche für die Server-Überwachung{#server-monitor-interface}

Die Benutzeroberfläche &quot;Server Monitor&quot;eignet sich zur Fehlerbehebung oder einfach zur Verfolgung der Leistungsparameter von Data Workbench-Servercomputern und Berichtscomputern, die Clients von Data Workbench-Servercomputern sind.

In der Benutzeroberfläche des Serverbildschirms wird oben links neben dem Computernamen entweder ein grüner Punkt oder ein roter Punkt angezeigt. Ein grüner Punkt zeigt an, dass der Computer fehlerfrei funktioniert. Ein roter Punkt zeigt an, dass auf dem Computer ein oder mehrere Fehler aufgetreten sind.

Der untere Bereich der Server Monitor-Oberfläche Liste den Verarbeitungsstatus der einzelnen verfügbaren Profil sowie Leistungsdetails zum Computer.

Weitere Informationen zu [!DNL Data Workbench servers] finden Sie im *Server Products Installations- und Administrationshandbuch*. Weitere Informationen zu [!DNL Report] finden Sie im *Data Workbench Report Guide*.

**So öffnen Sie die Oberfläche des Server-Monitors**

* Klicken Sie im Servers Manager mit der rechten Maustaste auf den Knoten des Data Workbench-Servers oder [!DNL Report]-Computers. t

Klicken Sie auf **[!UICONTROL Server Monitor]**, um Details zur Ansicht eines Servers anzuzeigen, oder klicken Sie auf **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]**, um Details zur Ansicht eines Clusters verwandter Server anzuzeigen.

![](assets/vis_ServerMonitor.png)

Die [!DNL Server Monitor]Schnittstelle wird alle 10 Sekunden automatisch aktualisiert.

In der folgenden Tabelle werden die Aufgaben Liste, die mit der [!DNL Server Monitor]-Schnittstelle abgeschlossen werden können.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe durchzuführen... </th> 
   <th colname="col2" class="entry"> Führen Sie folgende Schritte aus... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So prüfen Sie den Protokollverarbeitungsstatus eines Profils </p> </td> 
   <td colname="col2"> <p>Ansicht des Profil-Vektors <i>Profil</i> Name. Im obigen Beispiel würden Sie den Profil ExampleProfile-Vektor Ansicht, um zu sehen, dass das ExampleProfile-Profil auf einem Server verarbeitet wird und die Protokollverarbeitung zu 100 % abgeschlossen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie, wie lange der Computer braucht, um auf Anforderungen zu reagieren </p> </td> 
   <td colname="col2"> <p>Ansicht des Umfragelatenzfelds. Wenn dieser Wert größer als 1000 ms ist, wenden Sie sich an den Adobe Support Services. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zur Ansicht einer Schätzung der Dauer bis zum Abschluss der Transformation oder Abfrage </p> </td> 
   <td colname="col2"> <p>Ansicht des Sweep Time-Felds (hh:mm:ss), das nur während der Transformation oder Abfrage vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So ermitteln Sie die aktuelle Anzahl der Netzwerkverbindungen zum Computer </p> </td> 
   <td colname="col2"> <p>Ansicht der letzten Zeile der <span class="wintitle">-Serverüberwachung</span>-Informationen des Computers. Im obigen Beispiel sehen Sie, dass derzeit zwei Netzwerkverbindungen von einem Computer stammen. </p> </td> 
  </tr> 
 </tbody> 
</table>
