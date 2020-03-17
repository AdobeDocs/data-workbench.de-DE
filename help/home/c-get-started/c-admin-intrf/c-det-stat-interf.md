---
description: Die Detaillierte Statusschnittstelle ist hilfreich, um Fehler oder andere Probleme mit Data Workbench-Servercomputern zu beheben.
solution: Analytics
title: Detaillierte Statusoberfläche
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: fd3afa80250d5ae20b7758ba840fd4d436545cf2

---


# Detaillierte Statusoberfläche{#detailed-status-interface}

Die Detaillierte Statusschnittstelle ist hilfreich, um Fehler oder andere Probleme mit Data Workbench-Servercomputern zu beheben.

Dies umfasst alle [!DNL Transform] Profil, die auf diesen Computern ausgeführt werden, oder [!DNL Report] Computer, die Clients des Data Workbench-Servers sind. Sie können über das Menü auf [!DNL Master Server] und [!DNL Query Server Detailed Status] Schnittstellen [!DNL Admin] zugreifen. Klicken Sie zum Zugriff auf die [!DNL Detailed Status] Benutzeroberfläche für andere Computer mit der [!DNL Servers Manager]rechten Maustaste auf den Serverknoten, für den Sie den Status der Ansicht festlegen möchten, und klicken Sie auf **[!UICONTROL Detailed Status]**. Siehe [Server-Manager](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Weitere Informationen zum Data Workbench-Server finden Sie im Handbuch zur Installation und Verwaltung von *Serverprodukten*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Um die Informationen in einer [!DNL Detailed Status] Oberfläche zu aktualisieren, klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Detailed Status]** Überschrift und dann auf **[!UICONTROL Refresh]**.

In der folgenden Tabelle werden die Aufgaben Liste, die über die [!DNL Detailed Status] Oberfläche abgeschlossen werden können.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe durchzuführen... </th> 
   <th colname="col2" class="entry"> gehen Sie wie folgt vor: </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie jede Computerkomponente und ihren aktuellen Status an </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Komponentenstatus</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie an, wie viel Speicher auf dem Computer verwendet wird </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Speicherstatus</span> &gt; <span class="uicontrol"> Adressraum laden</span>. </p> <p>Weitere Informationen zum Überwachen der Auslastung des Adressenraums finden Sie im <i>Server Products Installations- und Administrationshandbuch</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie, ob der Computer für die Verwendung des /3GB-Switches konfiguriert ist </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Speicherstatus</span> &gt; <span class="uicontrol"> Prozessadressbereich</span>. </p> <p>Wenn das Feld <span class="wintitle"> Gesamtsumme</span> mehr als 3000000 KB anzeigt, ist Ihr Computer für die Verwendung des /3 GB-Switches konfiguriert. </p> <p>Weitere Informationen zum Switch /3 GB finden Sie im <i>Serverprodukt-Installations- und Administrationshandbuch</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie die Menge an Speicherplatz und Arbeitsspeicher, die zum Speichern der einzelnen Dimensionen verwendet werden, sowie die Menge, die zum Speichern der Namen der Elemente verwendet wird </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> Dimensionen</span> &gt; <span class="uicontrol"> Festplattennutzung</span> &gt; <i>&lt;<span class="uicontrol"> Profil-Name</span>&gt; </i><span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>Leistung&gt; &gt; &gt;Speichernutzung&gt; &lt;Name des Profils&gt;. </p> <p>Die <span class="wintitle"> Felder "Festplattennutzung</span> "enthalten den Namen und den Speicherplatz (in MB), der zum Speichern der einzelnen Dimensionen erforderlich ist. Eine hohe Speichernutzung kann sich nachteilig auf die Abfrage auswirken, da der Data Workbench-Server alle Daten durchlesen muss, um die entsprechenden Abfragen abzuschließen. Durch eine Verringerung der Speichernutzung für eine Dimension kann die Zeit zum Abschluss der zugehörigen Abfragen reduziert werden. </p> <p>Die Felder <span class="wintitle"> Speicherverwendung</span> geben die Anzahl der Elemente in den einzelnen Dimensionen und den Speicher an, der zum Speichern der Liste der Elementnamen erforderlich ist. Eine große Anzahl von Elementen kann sich negativ auf die Speichermenge auswirken, die während einer Abfrage verwendet wird, da der Data Workbench-Server jedes Element lesen muss. Eine Verringerung der Anzahl der Elemente in einer Dimension kann die Zeit verringern, die zum Abschluss der zugehörigen Abfragen benötigt wird. </p> <p>Beispiel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie die CPU-Auslastung für die Phasen der Protokollverarbeitung und -verarbeitung </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> CPU-Nutzung</span> &gt; <span class="uicontrol"> Protokollverarbeitung</span> &gt; <i>&lt;<span class="uicontrol"> Profil-Name</span>&gt;</i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span><span class="uicontrol"></span>Leistung&gt; Prozessorauslastung&gt; -Transformation&gt; &lt;Name des Profils&gt;. </p> <p>Jeder dieser Feldsätze bietet Ihnen die CPU-Auslastung (in Sekunden) für jede der Phasen der Protokollverarbeitung und -umwandlung. </p> <p>Beispiel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Die Abfrage dauert in der Regel proportional zur Gesamtgröße aller Dimensionen. Nach der Überprüfung der Größe der einzelnen Dimensionen können Sie bewerten, ob eine bestimmte Dimension nützlich genug ist und oft genug verwendet wird, um die Leistungskosten der Dimension zu rechtfertigen. Ist dies nicht der Fall, können Sie die Dimension im <span class="wintitle"> Profil-Manager</span>löschen.<p>Eine Dimension, deren Liste der Elementnamen zu groß ist (d. h. mehr als 128 MB), kann zu Fehlern im Zusammenhang mit "Nicht genügend Arbeitsspeicher"führen, selbst wenn die gesamte Speichernutzung der Adresse nicht annähernd so groß ist. </p> <p>Wenn Sie ein Data Workbench-Servercluster verwenden, aber keine zentralisierte Normalisierung verwenden, hat eine Dimension, deren Liste der Elementnamen groß ist, erhebliche Auswirkungen auf die Speicherbudgets für das Senden. Weitere Informationen zur zentralisierten Normalisierung finden Sie im Handbuch zur Konfiguration von <i>Datasets</i>. Wenn der für die Speicherung aller Listen von Elementnamen zusammen benötigte Arbeitsspeicher über 100 MB auf allen Servern im Cluster beträgt, erhalten Sie möglicherweise die Fehlermeldung "Speicherbudget überschritten"auch bei geringer Aktivität der Abfrage. Wenn Sie z. B. über einen Cluster mit vier Servern mit mehr als 25 MB auf jedem Server verfügen, auf dem die Listen von Elementnamen gespeichert werden, werden möglicherweise Fehler angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie die in der Protokollverarbeitung und -umwandlung verbrachte Zeit </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> CPU-Auslastung</span> &gt; <span class="uicontrol"> Protokollverarbeitung</span> &gt; <i>&lt;<span class="uicontrol"> Profil-Name</span>&gt;</i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>oder Leistung&gt; Prozessorauslastung&gt; Profil--&gt; -&gt;. </p> <p>Durch die Überprüfung der Felder in diesen Abschnitten können Sie Filter und Transformationen identifizieren, die sich negativ auf die für die Verarbeitung und Transformation von Protokollen benötigte Zeit auswirken können. Mit langen Verarbeitungszeiten können Sie dann Designentscheidungen zu individuellen Filtern und Transformationen treffen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie die Speichernutzung und erhöhen die Abfrage </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> Verarbeitungsfelder</span> für Protokolle &gt; <i>&lt;<span class="uicontrol"> Profil-Name</span>&gt;</i>. </p> <p>Jeder Zeileneintrag in diesem Abschnitt entspricht einem Parameter in der Datei " <span class="filepath"> Log Processing.cfg</span> ". Wenn Sie diese Felder überprüfen, können Sie sehen, wie viel Arbeitsspeicher die einzelnen Parameter verwenden. Sie können dann Designentscheidungen für einzelne Artikel treffen, die ziemlich groß sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie die abgelaufene Zeit der vorherigen Wiederaufbereitung oder Transformation </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Verarbeitungsstatus</span> &gt; <i>&lt;<span class="uicontrol"> Profil-Name</span>&gt;</i> &gt; <span class="uicontrol"> Verarbeitungsmodusverlauf</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Echtzeit - die Bereitstellung des Data Workbench-Servers für die Erstellung von Abfragen. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Schnelle Eingabe - Dieses Mal plus die Zeit der schnellen Zusammenführung ist die Gesamtdauer, die für die Verarbeitung des Datensatzes benötigt wird. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Schnelle Zusammenführung - die gesamte für die Transformation des Datensatzes benötigte Zeit. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So diagnostizieren Sie Probleme mit dem Ausführungszeitpunkt </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Verarbeitungsstatus</span> &gt; <i>&lt;<span class="uicontrol"> Profil-Name</span>&gt;</i> &gt; <span class="uicontrol"> Ausführungszeit</span> &gt; <span class="uicontrol"> Quellen als</span>. </p> <p>Die Überprüfung der Ausführungszeiten für jede Quelle kann Ihnen dabei helfen, festzustellen, welche(n) Quelle(n) sich negativ auf die Gesamt-Ausführungszeit auswirken können. Sie können dann die Probleme mit diesen Quellen lösen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So schätzen Sie, wie lange eine laufende Abfrage dauert </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Execution Engine</span>. </p> <p>Die Überprüfung des Felds <span class="wintitle"> "Zeit</span> für Datenabruf"gibt Ihnen eine Schätzung der Dauer des Abschlusses einer Abfrage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So erstellen Sie eine Liste aller auf diesem Computer verfügbaren Profil und Angaben zum Status </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Profil</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So replizieren Sie die Ansicht </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Komponentenstatus</span>. </p> <p>Überprüfen Sie den Status der Replizierungskomponente. Wenn Replizierung ausgeführt wird, wird OK angezeigt. Wenn die Replizierungskomponente fehlgeschlagen ist, wird eine Fehlermeldung angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ansicht des <span class="wintitle"> Berichtsserverstatus</span> für einen <span class="keyword"> Berichtscomputer</span> , der eine Verbindung zum Data Workbench-Server herstellt </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Berichtsserverstatus</span>. </p> <p>Dieser Abschnitt der <span class="wintitle"> Oberfläche für den Detailstatus</span> enthält eine Kopie der Datei " <span class="filepath"> Report Server.cfg</span> ", Informationen zur Anzahl der ausgeführten Berichte (aktueller Abschnitt) und Informationen zum letzten Fehler (Letzter Fehler). </p> <p>Anweisungen zum Bearbeiten der <span class="filepath"> Datei "Report Server.cfg</span> "finden Sie im <i>Data Workbench Report Guide</i>. </p> <p> <p>Hinweis: Wenn der Abschnitt " <span class="wintitle"> Berichtsserver-Status</span> "nicht in der Oberfläche " <span class="wintitle"> Detaillierter Status</span> "angezeigt wird, müssen Sie den Data Workbench-Server möglicherweise so konfigurieren, dass der <span class="wintitle"> Berichtsserver-Status</span>angezeigt wird. Anweisungen finden Sie im <i>Data Workbench Report Guide</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ansicht der Speichernutzungsinformationen für Transform </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf <span class="uicontrol"> Verarbeitungsstatus</span> &gt; <span class="uicontrol"> Transformieren</span>. </p> <p>Weitere Informationen zu Transform finden Sie im Handbuch zur Installation und Verwaltung von <i>Serverprodukten</i> und im Handbuch zur Konfiguration von <i>Datasets</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So speichern Sie die <span class="wintitle"> Oberfläche für den Detailstatus</span> als <span class="filepath"> *.cfg</span> -Datei, die in einem Texteditor wie Notepad geöffnet oder an andere verteilt werden kann </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf die Überschrift <span class="uicontrol"> Detaillierter Status</span> und klicken Sie auf <span class="uicontrol"> Kopieren</span>speichern unter. </p> <p>Hinweis:  <p>Wenn Sie mit der rechten Maustaste auf die Überschrift <span class="uicontrol"> Detaillierter Status</span> klicken und auf <span class="uicontrol"> Speichern</span> unter dem <i>Servernamen</i>/-status/ klicken, funktioniert das nicht in der Benutzeroberfläche <span class="wintitle"> Detaillierter Status</span> . Die folgende Fehlermeldung wird angezeigt: </p> <p>/Status/ kann nicht gespeichert werden. 403 Verboten </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ansicht <span class="uicontrol"> Zeilen pro Protokollquelle</span> , Metrik </p> </td> 
   <td colname="col2"> <p>Wenn die Metrik Zeilen pro Protokollquelle im Detailstatus gemeldet werden muss, muss der Data Workbench-Administrator die "Protokollquellen-ID"definieren und einen eindeutigen Namen in der Datei "Log Processing.cfg"des benutzerspezifischen Profils angeben. </p> </td> 
  </tr> 
 </tbody> 
</table>

