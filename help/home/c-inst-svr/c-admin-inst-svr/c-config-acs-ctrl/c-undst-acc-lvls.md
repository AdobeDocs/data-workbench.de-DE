---
description: Zugriffsebenen beschreiben, welche URIs auf dem Computer eine Benutzergruppe lesen oder ändern darf.
solution: Analytics
title: Grundlagen zu Zugriffsebenen
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---


# Grundlagen zu Zugriffsebenen{#understanding-access-levels}

Zugriffsebenen beschreiben, welche URIs auf dem Computer eine Benutzergruppe lesen oder ändern darf.

Beachten Sie die folgenden Richtlinien, um die Zugriffsebenen für die Benutzer Ihrer Organisation zu definieren:

* Bestimmte URIs ohne nachfolgende Schrägstriche beschränken den Zugriff auf diese URI. Beispielsweise [!DNL /Components/Communications.cfg] können Sie nur auf die [!DNL Communications.cfg]Datei zugreifen.

* Ein nachfolgender Schrägstrich (/), der ein Verzeichnis angibt, gibt den Gruppenmitgliedern Zugriff auf jeden URI, der mit dieser Zeichenfolge beginnt. /Profils/ bietet beispielsweise Zugriff auf den gesamten Ordner &quot;Profils&quot;.
* Ein Dollarzeichen ($) schränkt den Zugriff auf den exakten URI nur ein, auch wenn es sich um einen Ordner handelt. /Profils/$ bietet beispielsweise Zugriff zum Lesen des Hauptordners, nicht jedoch zum Lesen von Profilen in diesem Verzeichnis.

   Für den Zugriff auf bestimmte Dateien müssen Sie kein $ nach dem Komma verwenden.

   Geben Sie beispielsweise denselben Zugriff ein [!DNL /Components/Communications.cfg] und [!DNL /Components/Communications.cfg$] gewähren Sie ihn.

* Ein Prozentsymbol (%) kann mit CN (Common Name) verwendet werden, um den Zugriff zu ermöglichen. Beispiel: /Users/%CN%/ erlaubt den Zugriff auf den Benutzerordner, der dem gemeinsamen Namen des [!DNL Insight] Benutzers mit dem SSL-Zertifikat entspricht. Beachten Sie, dass diese Syntax nur einmal in einem URI verwendet werden kann.

Die URIs in den vordefinierten Zugriffskontrollen wurden wie folgt konfiguriert:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gruppenname </th> 
   <th colname="col2" class="entry"> Schreibgeschützter Zugriff </th> 
   <th colname="col3" class="entry"> Schreibzugriff </th> 
   <th colname="col4" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administratoren </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Lese- und Schreibzugriff auf alle <span class="keyword"> Insight Server</span> -Ordner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensoren </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Lesen und schreiben Sie den Zugriff auf die beiden Dateien, die die <span class="wintitle"> Sensoren</span> zur Kommunikation mit dem <span class="keyword"> Insight-Server</span>verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer </p> </td> 
   <td colname="col2"> <p>/Profile/ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Lesen und schreiben Sie den Zugriff auf den Benutzerordner, der dem gemeinsamen Namen des SSL-Zertifikats des <span class="keyword"> Insight</span> -Benutzers entspricht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power-Benutzer </p> </td> 
   <td colname="col2"> <p>/Profile/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> <p>/Profile/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Power Users haben denselben Zugriff wie Users, mit der zusätzlichen Möglichkeit, in den Profils-Ordner zu schreiben. Diese Benutzer können Profile bearbeiten und die automatische Aktualisierung von Änderungen für andere <span class="keyword"> Insight</span> -Benutzer aktivieren, z. B. bei der Verteilung neu definierter Arbeitsbereiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clusterserver </p> </td> 
   <td colname="col2"> <p>/Components for processing servers/ </p> <p>/Addresses/ </p> <p>/Profile/ </p> <p>/Suchen/ </p> <p>/Zugangssteuerung/ </p> <p>/bin/ </p> <p>/Protokolle/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Lese- und Schreibzugriff auf den Cluster-Ordner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Berichtsserver </p> </td> 
   <td colname="col2"> <p>/Profile/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> <p>/Profile/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Berichtscomputer haben denselben Zugriff wie Power Users, mit der zusätzlichen Möglichkeit, in die Datei ReportStatus.vsp zu schreiben <span class="filepath"></span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

**So konfigurieren Sie die Zugriffskontrolle**

Beim Definieren von Zugriffskontrollen müssen Sie alle Systemadministratoren, Benutzer, Cluster- und Berichtsserver-Benutzer einbeziehen, die Zugriff auf diesen [!DNL Insight Server] Computer benötigen. Sie können den Zugriff über IP-Adresse oder SSL-Zertifikatsinformationen, wie z. B. den gemeinsamen Namen oder die allgemeine Organisation, gewähren.

>[!NOTE]
>
>Wenn die [!DNL Access Control.cfg] Datei geändert wird [!DNL Insight Server], werden alle vorhandenen Verbindungen beendet und müssen erneut eine Verbindung hergestellt werden. Verbindungen werden mit den Berechtigungen in der aktualisierten [!DNL Access Control.cfg] Datei verglichen. In der Benutzeroberfläche des Servers Manager wird das [!DNL Insight Server] Symbol vorübergehend rot und dann grün, da die Verbindung beendet wird und eine erneute Verbindung mit allen anderen hergestellt werden muss.

1. Klicken Sie auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Files]**.

1. Klicken Sie im [!DNL Server Files Manager]Fenster auf , **[!UICONTROL Access Control]** um den Inhalt der Datei Ansicht. Die [!DNL Access Control.cfg] Datei befindet sich in diesem Ordner.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Access Control.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Access Control.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Klicken Sie im [!DNL Access Control.cfg] Fenster auf **[!UICONTROL Access Control Groups]** , um den Inhalt des Fensters Ansicht.

   ![](assets/access_ctrl_cfg.png)

1. So fügen Sie eine neue Zugriffskontrolle hinzu:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Access Control Groups]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Members]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Die Mitglieder für die Standardgruppen sind nicht vordefiniert. Standardmäßig wird dem Administrator der Zugriff auf 127.0.0.1 (lokaler Host) gewährt und IP wird [!DNL Sensor] Zugriff gewährt:*. Alle anderen Gruppenmitglieder der Zugriffskontrolle müssen definiert sein.

   1. Füllen Sie die Parameter aus.

1. So fügen Sie einer bestehenden Zugriffskontrolle neue Mitglieder hinzu:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Members]** unter der entsprechenden Zugriffskontrolle auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters klicken und dann auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen am [!DNL Insight Server] Computer zu speichern, klicken Sie mit der [!DNL Server Files Manager]rechten Maustaste auf das Häkchen [!DNL Access Control.cfg] in der [!DNL Temp] Spalte und dann auf **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

