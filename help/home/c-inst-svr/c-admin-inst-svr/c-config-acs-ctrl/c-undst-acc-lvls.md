---
description: Zugriffsebenen beschreiben, welche URIs auf dem Computer, den eine Benutzergruppe lesen oder ändern darf.
title: Grundlagen zu Zugriffsebenen
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Grundlagen zu Zugriffsebenen{#understanding-access-levels}

{{eol}}

Zugriffsebenen beschreiben, welche URIs auf dem Computer, den eine Benutzergruppe lesen oder ändern darf.

Befolgen Sie diese Richtlinien, um die Zugriffsebene für die Benutzer Ihres Unternehmens zu definieren:

* Bestimmte URIs ohne Schrägstrich beschränken den Zugriff auf diesen URI. Beispiel: [!DNL /Components/Communications.cfg] bietet Zugriff auf [!DNL Communications.cfg]nur -Datei.

* Ein nachfolgender Schrägstrich (/), der einen Ordner angibt, bietet den Gruppenmitgliedern Zugriff auf alle URI, die mit dieser Zeichenfolge beginnt. Beispielsweise bietet /Profile/ Zugriff auf den gesamten Profilordner.
* Ein nachstehendes Dollarzeichen ($) beschränkt nur den Zugriff auf den exakten URI, auch wenn es sich um ein Verzeichnis handelt. Beispielsweise ermöglicht /Profiles/$ den Zugriff auf das Verzeichnis der Hauptprofile, nicht aber auf das Lesen von Dateien in diesem Verzeichnis.

   Für den Zugriff auf bestimmte Dateien müssen Sie kein $ verwenden.

   Beispiel: [!DNL /Components/Communications.cfg] und [!DNL /Components/Communications.cfg$] denselben Zugriff gewähren.

* Ein Prozentsymbol (%) kann mit CN (Common Name) verwendet werden, um den Zugriff zu ermöglichen. Beispielsweise ermöglicht /Users/%CN%/ den Zugriff auf den Benutzerordner, der dem gemeinsamen SSL-Zertifikatnamen des [!DNL Insight] Benutzer. Beachten Sie, dass diese Syntax nur einmal in einem URI verwendet werden kann.

Die URIs in den vordefinierten Zugriffssteuerungsgruppen wurden wie folgt konfiguriert:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gruppenname </th> 
   <th colname="col2" class="entry"> Schreibgeschützter Zugriff </th> 
   <th colname="col3" class="entry"> Lese- und Schreibzugriff </th> 
   <th colname="col4" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administratoren </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Lese- und Schreibzugriff auf alle <span class="keyword"> Insight Server</span> Verzeichnissen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensoren </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Lese- und Schreibzugriff auf die beiden Dateien, die die <span class="wintitle"> Sensoren</span> zur Kommunikation mit dem <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer </p> </td> 
   <td colname="col2"> <p>/Profile/ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Lese- und Schreibzugriff auf den Benutzerordner, der dem gemeinsamen SSL-Zertifikatnamen des <span class="keyword"> Insight</span> Benutzer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power Users </p> </td> 
   <td colname="col2"> <p>/Profile/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> <p>/Profile/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Power Users haben denselben Zugriff wie Benutzer, mit der zusätzlichen Möglichkeit, in den Profilordner zu schreiben. Diese Benutzer können Profile bearbeiten und Änderungen für andere automatisch aktualisieren lassen <span class="keyword"> Insight</span> Benutzer, z. B. beim Verteilen neu definierter Arbeitsbereiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cluster-Server </p> </td> 
   <td colname="col2"> <p>/Components for Processing Servers/ </p> <p>/Addresses/ </p> <p>/Profile/ </p> <p>/Lookups/ </p> <p>/Zugriffssteuerung/ </p> <p>/bin/ </p> <p>/Protokolle/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Lese- und Schreibzugriff auf das Cluster-Verzeichnis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Berichtsserver </p> </td> 
   <td colname="col2"> <p>/Profile/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> <p>/Profile/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Berichtsmaschinen haben denselben Zugriff wie Power Users, mit der zusätzlichen Möglichkeit, in die <span class="filepath"> ReportStatus.vsp</span> -Datei. </p> </td> 
  </tr> 
 </tbody> 
</table>

**So konfigurieren Sie die Zugriffssteuerung**

Beim Definieren von Zugriffssteuerungsgruppen müssen Sie alle Systemadministratoren, Benutzer, Cluster-Server und Report Server-Benutzer einbeziehen, die Zugriff auf diese [!DNL Insight Server] Computer. Sie können den Zugriff über IP-Adressen oder SSL-Zertifikatinformationen, wie z. B. den allgemeinen Namen oder die Organisation, gewähren.

>[!NOTE]
>
>Wenn die [!DNL Access Control.cfg] geändert in [!DNL Insight Server], werden alle vorhandenen Verbindungen beendet und müssen erneut eine Verbindung herstellen. Verbindungen werden mit den Berechtigungen in der aktualisierten geprüft [!DNL Access Control.cfg] -Datei. In der Server-Manager-Benutzeroberfläche wird die [!DNL Insight Server] -Symbol wird vorübergehend rot und dann wieder grün, da die Verbindung beendet und gezwungen wird, sich wieder mit allen anderen zu verbinden.

1. Im [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol der [!DNL Insight Server] Sie möchten konfigurieren und klicken Sie auf **[!UICONTROL Files]**.

1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Access Control]** , um den Inhalt anzuzeigen. Die [!DNL Access Control.cfg] -Datei befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte für [!DNL Access Control.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Access Control.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Im [!DNL Access Control.cfg] Fenster, klicken Sie auf **[!UICONTROL Access Control Groups]** , um den Inhalt anzuzeigen.

   ![](assets/access_ctrl_cfg.png)

1. So fügen Sie eine neue Zugriffskontrollgruppe hinzu:

   1. Rechtsklick **[!UICONTROL Access Control Groups]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Rechtsklick **[!UICONTROL Members]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Die Mitglieder für die Standardgruppen sind nicht vordefiniert. Standardmäßig wird der Administratorzugriff auf 127.0.0.1 (lokaler Host) gewährt und [!DNL Sensor] Zugriff wird IP gewährt:&#42;. Alle anderen Zugriffskontrollgruppenmitglieder müssen definiert sein.

   1. Füllen Sie die Parameter aus.

1. So fügen Sie einer vorhandenen Zugriffskontrollgruppe neue Mitglieder hinzu:

   1. Rechtsklick **[!UICONTROL Members]** unter der entsprechenden Zugriffskontrollgruppe und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. So speichern Sie lokal vorgenommene Änderungen am [!DNL Insight Server] in der [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Access Control.cfg] im [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
