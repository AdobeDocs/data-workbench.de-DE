---
description: Mit dem Server Files Manager können Sie Data Workbench-Servercomputer remote von jeder autorisierten Data Workbench aus verwalten, indem Sie Zugriff auf alle Ordner und Dateien im Installationsordner des Produkts, einschließlich Konfigurations- und Nachschlagedateien, gewähren.
solution: Analytics
title: Server Files Manager
topic: Data workbench
uuid: 62625b9d-587f-4a78-8328-2270869909f8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server Files Manager{#server-files-manager}

Mit dem Server Files Manager können Sie Data Workbench-Servercomputer remote von jeder autorisierten Data Workbench aus verwalten, indem Sie Zugriff auf alle Ordner und Dateien im Installationsordner des Produkts, einschließlich Konfigurations- und Nachschlagedateien, gewähren.

Sie können auf die [!DNL Server Files Manager] Seite über das [!DNL Admin] Menü zugreifen, indem Sie mit der rechten Maustaste auf den Knoten des Data Workbench-Servercomputers im klicken [!DNL Servers Manager] und auf **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Sie können neue Serverdateimanager erstellen, die ausgewählte Ordner anzeigen. Siehe [Erstellen neuer Server-Dateimanager](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

Die linke Spalte [!DNL Server Files Manager] listet Datei- und Ordnernamen auf. Die Häkchen in der mittleren und rechten Spalte geben an, wo sich diese Ordner und Dateien in der Dateistruktur befinden.

Wenn sich eine Datei im Installationsordner des Produkts befindet, enthält die Spalte *Servername* (z. B. Data Workbench-Server) ein Häkchen. Wenn sich eine Datei auf dem Computer des Data Workbench-Benutzers im Ordner &quot; *Data Workbench installation directory*\Temp&quot;befindet, enthält die [!DNL Temp] Spalte ein Häkchen. Die Farbe der Häkchen gibt an, ob die Dateien, die sich an unterschiedlichen Speicherorten befinden, gleichzeitig geändert wurden.

* Ein rotes Häkchen in der Spalte mit dem Servernamen zeigt an, dass sich der Ordner oder die Datei auf dem Data Workbench-Servercomputer befindet.
* Ein rotes Häkchen in der [!DNL Temp] Spalte zeigt an, dass die lokale Kopie der Datei oder des Ordners dasselbe Datum und dieselbe Uhrzeit hat wie die Datei oder der Ordner auf dem Data Workbench-Server-Computer.
* Ein weißes Häkchen in der [!DNL Temp] Spalte zeigt an, dass die Datei oder der Ordner im *Installationsordner* von Data Workbench\Temp ein anderes Datum und eine andere Uhrzeit hat als die Datei oder der Ordner auf dem Computer des Data Workbench-Servers.

Die folgende Grafik zeigt die [!DNL Server Files Manager] mit den beiden Markierungen Rot und Weiß:

![](assets/vis_FileManager_RedWhiteChecks.png)

**So verwalten Sie Ordner und Dateien mit dem[!DNL Server Files Manager]**

Sie können die verwenden, [!DNL Server Files Manager] um Ordner und Dateien auf einem Data Workbench-Servercomputer zu bearbeiten.

In der folgenden Tabelle sind die Aufgaben aufgeführt, die mit dem [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
   <th colname="col2" class="entry"> gehen Sie wie folgt vor: </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie die Dateien in einem beliebigen Verzeichnis an </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf den Ordnernamen, um dessen Inhalt anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So blenden Sie den Inhalt eines Ordners aus </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf den Ordnernamen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie Details zu einem Verzeichnis an </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf die Zelle neben dem Ordner in der Spalte Servername oder <span class="wintitle"> Temp</span> . Folgende Informationen werden angezeigt: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Pfad. Der Pfad des Ordners. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir Der Name des Ordners. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">Von. Der Speicherort des Ordners Remote oder Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Datum (nur Spalte Temp). Erstellungsdatum oder das Datum der letzten Überarbeitung der lokalen Kopie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie Details zu einer Datei an </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen neben der Datei in der Spalte Servername oder <span class="wintitle"> Temp</span> . Folgende Informationen werden angezeigt: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Pfad. Der Pfad der Datei. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Datei. Der Name der Datei. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">Von. Der Speicherort des Ordners Remote oder Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Datum. Datum der letzten Überarbeitung der Datei. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Größe. Die Größe der Datei. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So laden Sie ein Verzeichnis auf Ihren lokalen Computer herunter </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte <i>Servername</i> für diesen Ordner und klicken Sie auf <span class="uicontrol"> Verzeichnis lokal</span>machen. Ein Häkchen für den Ordner wird in der Spalte <span class="wintitle"> Temp</span> angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So laden Sie eine Datei auf Ihren lokalen Computer herunter </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte <i>Servername</i> für diese Datei und klicken Sie auf <span class="uicontrol"> Als lokal</span>definieren. Ein Häkchen für die Datei wird in der Spalte " <span class="wintitle"> Temp</span> "angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So laden Sie den letzten Teil einer Protokolldatei auf Ihren lokalen Computer herunter </p> </td> 
   <td colname="col2"> <p>Um zu vermeiden, dass eine gesamte Protokolldatei heruntergeladen werden muss (insbesondere, wenn Sie wissen, dass die Fehlermeldung nahe am Dateiende liegt), klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für die Datei, klicken Sie auf <span class="uicontrol"> Tail</span>und wählen Sie die Größe des herunterzuladenden Abschnitts aus. Ein Häkchen für die Datei wird in der Spalte " <span class="wintitle"> Temp</span> "angezeigt. Die lokale Datei enthält nur die von Ihnen angegebene Datenmenge, beginnend mit dem Dateiende. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So öffnen Sie ein Verzeichnis </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für den Ordner in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Öffnen</span> &gt; <span class="uicontrol"> Ordner</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So öffnen Sie eine Datei </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte <span class="wintitle"> Temp</span> , klicken Sie auf <span class="uicontrol"> Öffnen</span>und dann auf <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> in Notepad</span>oder im <span class="uicontrol"> Ordner</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lokale Kopie eines Ordners auf dem Data Workbench-Server speichern </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für den Ordner in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Verzeichnis speichern unter</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lokale Kopie einer Datei auf dem Data Workbench-Server speichern </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Speichern unter</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entfernen einer lokalen Kopie eines Ordners oder einer Datei </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für das Verzeichnis oder die Datei in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Entfernen</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kopieren und Einfügen einer Datei als E-Mail-Anhang in Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Kopieren</span>. Drücken Sie im Text Ihrer E-Mail Strg+V, um die Datei anzuhängen. </p> </td> 
  </tr> 
 </tbody> 
</table>

