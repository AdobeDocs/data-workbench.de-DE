---
description: Die detaillierte Statusschnittstelle ist zur Fehlerbehebung bei Fehlern oder anderen Problemen mit Data Workbench Server-Computern hilfreich.
title: Oberfläche zu Statusdetails
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Oberfläche zu Statusdetails{#detailed-status-interface}

{{eol}}

Die detaillierte Statusschnittstelle ist zur Fehlerbehebung bei Fehlern oder anderen Problemen mit Data Workbench Server-Computern hilfreich.

Dies umfasst alle [!DNL Transform] Profile, die auf diesen Computern ausgeführt werden, oder [!DNL Report] Computer, die Clients des Data Workbench-Servers sind. Sie können [!DNL Master Server] und [!DNL Query Server Detailed Status] Schnittstellen durch [!DNL Admin] Menü. So greifen Sie auf die [!DNL Detailed Status] Benutzeroberfläche für andere Computer, in [!DNL Servers Manager]klicken Sie mit der rechten Maustaste auf den Knoten des Servers, für den Sie den Status anzeigen möchten, und klicken Sie auf **[!UICONTROL Detailed Status]**. Siehe [Server-Manager](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Weitere Informationen zum Data Workbench-Server finden Sie unter *Handbuch zur Installation und Verwaltung von Serverprodukten*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>So aktualisieren Sie die Informationen in einer [!DNL Detailed Status] -Benutzeroberfläche, klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Detailed Status]** Überschrift und Klicken **[!UICONTROL Refresh]**.

In der folgenden Tabelle sind die Aufgaben aufgeführt, die mit dem [!DNL Detailed Status] -Schnittstelle.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
   <th colname="col2" class="entry"> Führen Sie folgende Schritte aus... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie die einzelnen Computerkomponenten und ihren aktuellen Status an </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Komponentenstatus</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie an, wie viel Speicher auf dem Computer verwendet wird </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Speicherstatus</span> &gt; <span class="uicontrol"> Laden des Adressraums</span>. </p> <p>Weitere Informationen zur Überwachung der Auslastung des Adressraums finden Sie im Abschnitt <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie, ob der Computer für die Verwendung des /3GB-Switches konfiguriert ist </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Speicherstatus</span> &gt; <span class="uicontrol"> Process Address Space</span>. </p> <p>Wenn die Variable <span class="wintitle"> Ingesamt</span> mehr als 3000000 KB anzeigen, ist Ihr Computer für die Verwendung des /3GB-Switches konfiguriert. </p> <p>Weitere Informationen zum /3GB-Switch finden Sie in der <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie die Menge an Speicherplatz und Arbeitsspeicher, die zum Speichern der einzelnen Dimensionen verwendet werden, sowie die Menge, die zum Speichern der Namen der zugehörigen Elemente verwendet wird </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> Dimensionen</span> &gt; <span class="uicontrol"> Festplattenauslastung</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt; </i>oder <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> Dimensionen</span> &gt; <span class="uicontrol"> Speichernutzung</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i>. </p> <p>Die <span class="wintitle"> Festplattenauslastung</span> -Felder geben den Namen und die Menge des Festplattenspeichers an (in MB), der zum Speichern der einzelnen Dimensionen erforderlich ist. Eine große Anzahl von Festplattenverwendungen kann sich nachteilig auf die Abfrageleistungen auswirken, da der Data Workbench-Server alle Daten durchlesen muss, um die entsprechenden Abfragen abzuschließen. Wenn Sie die Festplattenauslastung für eine Dimension verringern, kann die Zeit für die Durchführung verwandter Abfragen verkürzt werden. </p> <p>Die <span class="wintitle"> Speichernutzung</span> -Felder geben die Anzahl der Elemente in jeder Dimension und den Speicherbedarf an, um die Liste der Elementnamen zu speichern. Eine große Anzahl von Elementen kann sich nachteilig auf die Speicherkapazität auswirken, die während einer Abfrage verwendet wird, da der Data Workbench-Server jedes Element durchlesen muss. Eine Verringerung der Anzahl von Elementen in einer Dimension kann die Zeit für die Durchführung verwandter Abfragen verkürzen. </p> <p>Beispiel: <code>+&nbsp;Performance
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
   <td colname="col1"> <p>Überwachen der CPU-Auslastung für die Phasen der Protokollverarbeitung und -umwandlung </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> CPU-Auslastung</span> &gt; <span class="uicontrol"> Protokollverarbeitung</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i> oder <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> CPU-Auslastung</span> &gt; <span class="uicontrol"> Umwandlung</span> &gt; &lt;<span class="uicontrol"> Profilname</span>&gt;. </p> <p>Jeder dieser Feldsätze bietet Ihnen die CPU-Nutzung (in Sekunden) für jede der Phasen der Protokollverarbeitung und -umwandlung. </p> <p>Beispiel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Die Zeit, die zum Abschließen einer Abfrage benötigt wird, ist normalerweise proportional zur Gesamtgröße aller Dimensionen. Nach Überprüfung der Größe jeder Dimension können Sie ermitteln, ob eine bestimmte Dimension nützlich genug ist und oft genug verwendet wird, um die Leistungskosten der Dimension zu rechtfertigen. Ist dies nicht der Fall, können Sie die Dimension im <span class="wintitle"> Profil-Manager</span>.<p>Eine Dimension, deren Elementnamenliste zu groß ist (d. h. mehr als 128 MB), kann zu Fehlern bei "Nicht genügend Arbeitsspeicher"führen, selbst wenn die gesamte Adressenspeicherplatznutzung nicht nahe am Grenzwert liegt. </p> <p>Wenn Sie einen Data Workbench-Servercluster verwenden, jedoch keine zentralisierte Normalisierung verwenden, wirkt sich eine Dimension, deren Elementnamen umfangreich sind, erheblich auf die Speicherbudgets für den Versand aus. Weitere Informationen zur zentralisierten Normalisierung finden Sie im <i>Anleitung zur Datensatzkonfiguration</i>. Wenn der für die Speicherung aller Listen mit Elementnamen benötigte Speicher über alle Server im Cluster mehr als 100 MB beträgt, können Fehler vom Typ "Speicherbudget überschritten senden"auftreten, selbst wenn die Abfrageaktivität leicht ist. Wenn beispielsweise ein Cluster mit vier Servern mit mehr als 25 MB auf jedem Server zum Speichern der Listen mit Elementnamen verwendet wird, können Fehler auftreten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie die mit der Protokollverarbeitung und -umwandlung verbrachte Zeit </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> CPU-Auslastung</span> &gt; <span class="uicontrol"> Protokollverarbeitung</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i> oder <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> CPU-Auslastung</span> &gt; <span class="uicontrol"> Umwandlung</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i>. </p> <p>Wenn Sie die Felder in diesen Abschnitten überprüfen, können Sie Filter und Umwandlungen identifizieren, die sich negativ auf die für die Protokollverarbeitung und -umwandlung benötigte Zeit auswirken können. Anschließend können Sie Designentscheidungen zu individuellen Filtern und Umwandlungen mit langen Verarbeitungszeiten treffen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So überwachen Sie den Festplattenspeicherbedarf und erhöhen die Abfrageschwindigkeit </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Leistung</span> &gt; <span class="uicontrol"> Verarbeitungsfelder für Protokolle</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i>. </p> <p>Jeder Zeileneintrag in diesem Abschnitt entspricht einem Parameter im <span class="filepath"> Log Processing.cfg</span> -Datei. Durch die Überprüfung dieser Felder können Sie sehen, wie viel Speicher die einzelnen Parameter verwenden. Anschließend können Sie Designentscheidungen für einzelne Artikel treffen, die sehr groß sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So bestimmen Sie die verstrichene Zeit der vorherigen Wiederaufbereitung oder Transformation </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Verarbeitungsstatus</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i> &gt; <span class="uicontrol"> Verlauf des Verarbeitungsmodus</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Echtzeit - Zeit, die der Data Workbench-Server für Abfragen zur Verfügung stand. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Schnelle Eingabe - Dieses Mal plus der Schnelle Zusammenführungszeitpunkt ist die Gesamtdauer, die für die Verarbeitung des Datensatzes erforderlich ist. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Schnelle Zusammenführung - die für die Transformation des Datensatzes benötigte Gesamtzeit. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So diagnostizieren Sie Probleme mit dem Ausführungszeitpunkt </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Verarbeitungsstatus</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i> &gt; <span class="uicontrol"> Ausführungszeit</span> &gt; <span class="uicontrol"> Quellen als</span>. </p> <p>Die Überprüfung der Ausführungszeiten für jede Quelle kann Ihnen dabei helfen festzustellen, welche Quelle(n) sich negativ auf das Gesamtergebnis auswirken kann. Anschließend können Sie die Probleme mit diesen speziellen Quellen beheben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So schätzen Sie, wie lange eine laufende Abfrage dauert </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Execution Engine</span>. </p> <p>Überprüfen der <span class="wintitle"> Sweep-Zeit der Daten</span> gibt einen Schätzwert dazu an, wie lange es dauert, bis eine Abfrage abgeschlossen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So listen Sie alle auf diesem Computer verfügbaren Profile sowie deren Status auf </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Profile</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie den Replikationsstatus an </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Komponentenstatus</span>. </p> <p>Überprüfen Sie den Status der Replicate-Komponente. Wenn die Replikation ausgeführt wird, wird OK angezeigt. Wenn die Replikationskomponente fehlgeschlagen ist, wird eine Fehlermeldung angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zur Ansicht <span class="wintitle"> Berichtsserver</span> Status für <span class="keyword"> Bericht</span> Computer, der eine Verbindung zum Data Workbench-Server herstellt </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Report Server-Status</span>. </p> <p>Dieser Abschnitt der <span class="wintitle"> Detaillierter Status</span> -Benutzeroberfläche enthält eine Kopie der <span class="filepath"> Report Server.cfg</span> Datei, Informationen zur Anzahl der ausgeführten Berichte (aktueller Slice) und Informationen zum letzten Fehler (Letzter Fehler). </p> <p>Schritte zum Bearbeiten der <span class="filepath"> Report Server.cfg</span> -Datei, siehe <i>Data Workbench-Berichtanleitung</i>. </p> <p> <p>Hinweis: Wenn die Variable <span class="wintitle"> Report Server-Status</span> wird nicht im <span class="wintitle"> Detaillierter Status</span> -Benutzeroberfläche, müssen Sie möglicherweise den Data Workbench-Server für die Anzeige konfigurieren <span class="wintitle"> Report Server-Status</span>. Anweisungen finden Sie in der <i>Data Workbench-Berichtanleitung</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie Speicherverwendungsinformationen für Transform an </p> </td> 
   <td colname="col2"> <p>Klicken <span class="uicontrol"> Verarbeitungsstatus</span> &gt; <span class="uicontrol"> Transform</span>. </p> <p>Weitere Informationen zu Transform finden Sie unter <i>Handbuch zur Installation und Verwaltung von Serverprodukten</i> und <i>Anleitung zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So speichern Sie die <span class="wintitle"> Detaillierter Status</span> Benutzeroberfläche als <span class="filepath"> *.cfg</span> Datei, die in einem Texteditor wie Notepad geöffnet oder an andere verteilt werden kann </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf die <span class="uicontrol"> Detaillierter Status</span> Überschrift und Klicken <span class="uicontrol"> Kopie speichern unter</span>. </p> <p>Hinweis:  <p>Rechtsklick auf die <span class="uicontrol"> Detaillierter Status</span> Überschrift und Klicken <span class="uicontrol"> Speichern</span> nach <i>Servername</i>/Status/ funktioniert nicht im <span class="wintitle"> Detaillierter Status</span> -Schnittstelle. Die folgende Fehlermeldung wird angezeigt: </p> <p>/Status/ kann nicht gespeichert werden. 403 Verboten </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zur Ansicht <span class="uicontrol"> Zeilen pro Protokollquelle</span> Metrik </p> </td> 
   <td colname="col2"> <p>Wenn die Metrik Zeilen pro Protokollquelle im Detailstatus aufgeführt werden muss, muss der Data Workbench-Administrator die "Protokollquellen-ID"definieren und in der Datei "Log Processing.cfg"des benutzerdefinierten Profils einen eindeutigen Namen angeben. </p> </td> 
  </tr> 
 </tbody> 
</table>
