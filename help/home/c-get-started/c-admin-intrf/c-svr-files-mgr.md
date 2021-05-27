---
description: Der Server Files Manager ermöglicht die Remote-Verwaltung und Verwaltung von Data Workbench Server-Computern von beliebigen autorisierten Data Workbenchs aus, indem er Zugriff auf alle Ordner und Dateien im Installationsverzeichnis des Produkts bietet, einschließlich Konfigurations- und Suchdateien.
title: Server-Datei-Manager
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 2%

---

# Server-Datei-Manager{#server-files-manager}

Der Server Files Manager ermöglicht die Remote-Verwaltung und Verwaltung von Data Workbench Server-Computern von beliebigen autorisierten Data Workbenchs aus, indem er Zugriff auf alle Ordner und Dateien im Installationsverzeichnis des Produkts bietet, einschließlich Konfigurations- und Suchdateien.

Sie können auf [!DNL Server Files Manager] über das Menü [!DNL Admin] zugreifen, indem Sie mit der rechten Maustaste auf den Data Workbench-Serverknoten im [!DNL Servers Manager] klicken und **[!UICONTROL Server Files]** auswählen.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Sie können neue Server-Dateimanager erstellen, die ausgewählte Verzeichnisse anzeigen. Siehe [Erstellen neuer Server-Dateimanager](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

In der linken Spalte von [!DNL Server Files Manager] werden Datei- und Ordnernamen aufgelistet. Die Häkchen in der Mitte und in der rechten Spalte zeigen an, wo sich diese Ordner und Dateien in der Dateistruktur befinden.

Wenn sich eine Datei im Installationsverzeichnis des Produkts befindet, enthält die Spalte *Servername* (z. B. Data Workbench-Server) ein Häkchen. Wenn sich eine Datei auf dem Computer des Data Workbench-Benutzers im Ordner *Installationsordner der Data Workbench*\Temp befindet, enthält die Spalte [!DNL Temp] ein Häkchen. Die Farbe der Häkchen zeigt an, ob die Dateien, die sich an verschiedenen Speicherorten befinden, gleichzeitig geändert wurden.

* Ein rotes Häkchen in der Spalte &quot;Servername&quot;zeigt an, dass sich der Ordner oder die Datei auf dem Data Workbench-Server-Computer befindet.
* Ein rotes Häkchen in der Spalte [!DNL Temp] zeigt an, dass die lokale Kopie der Datei oder des Ordners dasselbe Änderungsdatum und dieselbe Uhrzeit hat wie die Datei oder der Ordner auf dem Data Workbench-Server-Computer.
* Ein weißes Häkchen in der Spalte [!DNL Temp] zeigt an, dass die Datei bzw. der Ordner im Installationsordner *Data Workbench*\Temp einen anderen Ordner hat als die Datei bzw. der Ordner auf dem Data Workbench-Servercomputer.

Die folgende Grafik zeigt das [!DNL Server Files Manager] mit den Markierungen Rot und Weiß:

![](assets/vis_FileManager_RedWhiteChecks.png)

**So verwalten Sie Ordner und Dateien mit dem[!DNL Server Files Manager]**

Sie können [!DNL Server Files Manager] verwenden, um Ordner und Dateien auf einem Data Workbench-Servercomputer zu bearbeiten.

In der folgenden Tabelle sind die Aufgaben aufgeführt, die mit [!DNL Server Files Manager] ausgeführt werden können:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
   <th colname="col2" class="entry"> Führen Sie folgende Schritte aus... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Anzeigen der Dateien in einem beliebigen Verzeichnis </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf den Verzeichnisnamen, um dessen Inhalt anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So blenden Sie den Inhalt eines Ordners aus </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf den Verzeichnisnamen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie Details zu einem Ordner an </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf die Zelle neben dem Ordner in der Spalte "Servername"oder "<span class="wintitle"> Temp</span>". Sie sehen die folgenden Informationen: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Path. Der Pfad des Ordners. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir! Der Name des Ordners. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">Von. Der Speicherort des Ordners, Remote oder Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Datum (nur temporäre Spalte). Erstellungsdatum oder das Datum der letzten Änderung an der lokalen Kopie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So zeigen Sie Details zu einer Datei an </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen neben der Datei in der Spalte "Servername"oder "<span class="wintitle"> Temp</span>". Sie sehen die folgenden Informationen: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Pfad. Der Pfad der Datei. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Datei. Der Name der Datei. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">Von. Der Speicherort des Ordners, Remote oder Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Datum. Datum der letzten Revision der Datei. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Größe. Die Größe der Datei. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So laden Sie einen Ordner auf Ihren lokalen Computer herunter </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte <i>Servername</i> für diesen Ordner und klicken Sie auf <span class="uicontrol"> Verzeichnis lokalisieren</span>. Ein Häkchen für das Verzeichnis wird in der Spalte <span class="wintitle"> Temp</span> angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So laden Sie eine Datei auf Ihren lokalen Computer herunter </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte <i>Servername</i> für diese Datei und klicken Sie auf <span class="uicontrol"> Make Local</span>. Ein Häkchen für die Datei wird in der Spalte <span class="wintitle"> Temp</span> angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So laden Sie den letzten Teil einer Protokolldatei auf Ihren lokalen Computer herunter </p> </td> 
   <td colname="col2"> <p>Um zu vermeiden, dass eine gesamte Protokolldatei heruntergeladen werden muss (insbesondere wenn Sie wissen, dass die Fehlermeldung nahe am Dateiende liegt), klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte mit dem Servernamen der Datei, klicken Sie auf <span class="uicontrol"> Tail</span> und wählen Sie die Größe des herunterzuladenden Teils aus. Ein Häkchen für die Datei wird in der Spalte <span class="wintitle"> Temp</span> angezeigt. Die lokale Datei enthält nur die von Ihnen angegebene Datenmenge, beginnend mit dem Ende der Datei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Öffnen eines Ordners </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für den Ordner in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Öffnen</span> &gt; <span class="uicontrol"> Ordner</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>So öffnen Sie eine Datei </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte <span class="wintitle"> Temp</span>, klicken Sie auf <span class="uicontrol"> Öffnen</span> und dann auf <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> in Notepad</span> oder <span class="uicontrol"> Ordner</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lokale Kopie eines Ordners auf dem Data Workbench-Server speichern </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für das Verzeichnis in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Verzeichnis speichern unter</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Speichern einer lokalen Dateikopie auf dem Data Workbench-Server </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Speichern unter</span> &gt; <i>&lt;<span class="uicontrol"> Profilname</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entfernen einer lokalen Kopie eines Ordners oder einer Datei </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für das Verzeichnis oder die Datei in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Remove</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kopieren und Einfügen einer Datei als E-Mail-Anhang in Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte <span class="wintitle"> Temp</span> und klicken Sie auf <span class="uicontrol"> Copy</span>. Drücken Sie im Textkörper Ihrer E-Mail Strg+V, um die Datei anzuhängen. </p> </td> 
  </tr> 
 </tbody> 
</table>
