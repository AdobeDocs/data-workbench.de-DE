---
description: Zugriffsebenen beschreiben, welche URIs auf dem Computer eine Benutzergruppe lesen oder ändern darf.
title: Grundlagen zu Zugriffsebenen
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Grundlagen zu Zugriffsebenen{#understanding-access-levels}

Zugriffsebenen beschreiben, welche URIs auf dem Computer eine Benutzergruppe lesen oder ändern darf.

Beachten Sie die folgenden Richtlinien, um die Zugriffsebenen für die Benutzer Ihrer Organisation zu definieren:

* Bestimmte URIs ohne nachfolgende Schrägstriche beschränken den Zugriff auf diese URI. Beispielsweise bietet [!DNL /Components/Communications.cfg] nur Zugriff auf die Datei [!DNL Communications.cfg].

* Ein nachfolgender Schrägstrich (/), der ein Verzeichnis angibt, gibt den Gruppenmitgliedern Zugriff auf jeden URI, der mit dieser Zeichenfolge beginnt. /Profils/ bietet beispielsweise Zugriff auf den gesamten Ordner &quot;Profils&quot;.
* Ein Dollarzeichen ($) schränkt den Zugriff auf den exakten URI nur ein, auch wenn es sich um einen Ordner handelt. /Profils/$ bietet beispielsweise Zugriff zum Lesen des Hauptordners, nicht jedoch zum Lesen von Profilen in diesem Verzeichnis.

   Für den Zugriff auf bestimmte Dateien müssen Sie kein $ nach dem Komma verwenden.

   Beispielsweise stellen [!DNL /Components/Communications.cfg] und [!DNL /Components/Communications.cfg$] denselben Zugriff bereit.

* Ein Prozentsymbol (%) kann mit CN (Common Name) verwendet werden, um den Zugriff zu ermöglichen. Beispiel: /Users/%CN%/ erlaubt den Zugriff auf den Benutzerordner, der dem gemeinsamen Namen des SSL-Zertifikats des [!DNL Insight]-Benutzers entspricht. Beachten Sie, dass diese Syntax nur einmal in einem URI verwendet werden kann.

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
   <td colname="col4"> <p>Lesen und Schreiben des Zugriffs auf alle Ordner <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensoren </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Lesen und schreiben Sie den Zugriff auf die beiden Dateien, die die Sensoren <span class="wintitle"> verwenden, um mit dem <span class="keyword"> Insight Server</span> zu kommunizieren.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer </p> </td> 
   <td colname="col2"> <p>/Profile/ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Lesen und schreiben Sie den Zugriff auf den Benutzerordner, der dem gemeinsamen Namen des SSL-Zertifikats des <span class="keyword">-Benutzers entspricht.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power-Benutzer </p> </td> 
   <td colname="col2"> <p>/Profile/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Benutzer/$ </p> </td> 
   <td colname="col3"> <p>/Profile/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Power Users haben denselben Zugriff wie Users, mit der zusätzlichen Möglichkeit, in den Profils-Ordner zu schreiben. Diese Benutzer können Profile bearbeiten und die automatische Aktualisierung von Änderungen für andere <span class="keyword"> Insight</span>-Benutzer aktivieren, z. B. bei der Verteilung neu definierter Arbeitsbereiche. </p> </td> 
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
   <td colname="col4"> <p>Berichtscomputer haben denselben Zugriff wie Power Users, mit der zusätzlichen Möglichkeit, in die Datei <span class="filepath"> ReportStatus.vsp</span> zu schreiben. </p> </td> 
  </tr> 
 </tbody> 
</table>

**So konfigurieren Sie die Zugriffskontrolle**

Beim Definieren von Zugriffskontrollen müssen Sie alle Systemadministratoren, Benutzer, Cluster- und Berichtsserver-Benutzer einbeziehen, die Zugriff auf diesen [!DNL Insight Server]-Computer benötigen. Sie können den Zugriff über IP-Adresse oder SSL-Zertifikatsinformationen, wie z. B. den gemeinsamen Namen oder die allgemeine Organisation, gewähren.

>[!NOTE]
>
>Wenn die [!DNL Access Control.cfg]-Datei unter [!DNL Insight Server] geändert wird, werden alle vorhandenen Verbindungen beendet und müssen eine erneute Verbindung hergestellt werden. Verbindungen werden mit den Berechtigungen in der aktualisierten Datei [!DNL Access Control.cfg] verglichen. In der Server Manager-Oberfläche wird das [!DNL Insight Server]-Symbol vorübergehend rot und dann grün wieder, da die Verbindung beendet wird und gezwungen ist, die Verbindung mit allen anderen wieder herzustellen.

1. Klicken Sie auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht von **[!UICONTROL Servers Manager]**, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Files]**.

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Access Control]**, um den Inhalt Ansicht. Die Datei [!DNL Access Control.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Access Control.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Access Control.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Klicken Sie im Fenster [!DNL Access Control.cfg] auf **[!UICONTROL Access Control Groups]**, um den Inhalt Ansicht.

   ![](assets/access_ctrl_cfg.png)

1. So fügen Sie eine neue Zugriffskontrolle hinzu:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Access Control Groups]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Members]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Die Mitglieder für die Standardgruppen sind nicht vordefiniert. Standardmäßig wird der Administratorzugriff auf 127.0.0.1 (lokaler Host) und der Zugriff auf [!DNL Sensor] auf IP:* gewährt. Alle anderen Gruppenmitglieder der Zugriffskontrolle müssen definiert sein.

   1. Füllen Sie die Parameter aus.

1. So fügen Sie einer bestehenden Zugriffskontrolle neue Mitglieder hinzu:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Members]** unter der entsprechenden Zugriffskontrolle und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]** klicken.

1. Um die lokal vorgenommenen Änderungen am [!DNL Insight Server]-Computer zu speichern, klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Access Control.cfg] in der Spalte [!DNL Temp] und dann auf **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
