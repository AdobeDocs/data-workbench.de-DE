---
description: Die Benutzeroberfläche "Server Monitor"eignet sich zur Fehlerbehebung oder einfachen Nachverfolgung der Leistungsparameter von Data Workbench-Servercomputern und Berichtscomputern, die Clients von Data Workbench-Servercomputern sind.
title: Oberfläche für die Server-Überwachung
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%

---

# Oberfläche für die Server-Überwachung{#server-monitor-interface}

{{eol}}

Die Benutzeroberfläche &quot;Server Monitor&quot;eignet sich zur Fehlerbehebung oder einfachen Nachverfolgung der Leistungsparameter von Data Workbench-Servercomputern und Berichtscomputern, die Clients von Data Workbench-Servercomputern sind.

In der Benutzeroberfläche &quot;Server Monitor&quot;wird links neben dem Computernamen entweder ein grüner Punkt oder ein roter Punkt angezeigt. Ein grüner Punkt zeigt an, dass der Computer problemlos funktioniert. Ein roter Punkt zeigt an, dass auf dem Computer ein oder mehrere Fehler aufgetreten sind.

Im unteren Bereich der Server Monitor-Benutzeroberfläche werden der Verarbeitungsstatus aller Ihrer verfügbaren Profile sowie Leistungsdetails zum Computer aufgeführt.

Weitere Informationen finden Sie unter [!DNL Data Workbench servers], siehe *Handbuch zur Installation und Verwaltung von Serverprodukten*. Weitere Informationen finden Sie unter [!DNL Report], siehe *Data Workbench-Berichtanleitung*.

**So öffnen Sie die Server Monitor-Benutzeroberfläche**

* Klicken Sie im Server-Manager mit der rechten Maustaste auf den Knoten des Data Workbench-Servers oder [!DNL Report] Computer. t

Klicken **[!UICONTROL Server Monitor]** um Details zu einem Server anzuzeigen, oder klicken Sie auf **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** um Details zu einem Cluster verwandter Server anzuzeigen.

![](assets/vis_ServerMonitor.png)

Die [!DNL Server Monitor]Die -Benutzeroberfläche wird alle zehn Sekunden automatisch aktualisiert.

In der folgenden Tabelle sind die Aufgaben aufgeführt, die mit dem [!DNL Server Monitor] -Schnittstelle.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
   <th colname="col2" class="entry"> Führen Sie folgende Schritte aus... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So überprüfen Sie den Protokollverarbeitungsstatus eines Profils </p> </td> 
   <td colname="col2"> <p>Profil anzeigen <i>Profil</i> Name: vektor. Im obigen Beispiel würden Sie den Profilbeispiel ExampleProfile anzeigen, um zu sehen, dass das ExampleProfile-Profil auf einem Server verarbeitet und die Protokollverarbeitung zu 100 % abgeschlossen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie, wie lange der Computer für die Beantwortung von Anfragen benötigt </p> </td> 
   <td colname="col2"> <p>Zeigen Sie das Feld für die Umfragelatenz an. Wenn dieser Wert größer als 1000 ms ist, wenden Sie sich an den Support-Dienst für Adoben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie eine Schätzung der Dauer an, die zum Abschließen der Transformation oder Abfragen erforderlich ist </p> </td> 
   <td colname="col2"> <p>Sweep-Zeit anzeigen (hh:mm:ss) , das nur während der Transformation oder Abfrage vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie die aktuelle Anzahl von Netzwerkverbindungen zum Computer </p> </td> 
   <td colname="col2"> <p>Anzeigen der letzten Zeile des Computers <span class="wintitle"> Server Monitor</span> Informationen. Im obigen Beispiel sehen Sie, dass derzeit zwei Netzwerkverbindungen von einem Computer stammen. </p> </td> 
  </tr> 
 </tbody> 
</table>
