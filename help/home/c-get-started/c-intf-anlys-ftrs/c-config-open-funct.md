---
description: Mit der Funktion "Öffnen"können Sie Elemente wie Dokumente oder URIs in externen Anwendungen wie einem Texteditor oder einem Webbrowser öffnen.
solution: Analytics
title: Konfigurieren der Funktion "Öffnen"
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren der Funktion &quot;Öffnen&quot;{#configure-open-functionality}

Mit der Funktion &quot;Öffnen&quot;können Sie Elemente wie Dokumente oder URIs in externen Anwendungen wie einem Texteditor oder einem Webbrowser öffnen.

Die Funktion &quot;Öffnen&quot;wird derzeit nur in der [!DNL Site] Anwendung und nur zum Öffnen von URIs konfiguriert. Dieser Abschnitt enthält Informationen zum Konfigurieren der Open URI-Funktionalität für [!DNL Site]. Informationen zum Konfigurieren der Open-Funktion für eine andere Anwendung oder zum Öffnen anderer Elemente erhalten Sie bei Adobe Consulting Services.

Sie [!DNL Site]können mit der rechten Maustaste auf einen URI aus einer Seitenüberlagerung oder Tabelle klicken, um den URI in der Anwendung anzuzeigen, für die er formatiert wurde. Beispielsweise können Sie in einer Visualisierung einer URI-Tabelle auf einen URI klicken, um eine Webseite in einem Webbrowser anzuzeigen.

Um einen URI aus einer Visualisierung zu öffnen, müssen Sie zunächst die [!DNL Open URI.cfg] Datei für die URI-Dimension bearbeiten, um den Speicherort und die Benennungsregeln zu identifizieren, die Data Workbench zum Öffnen des URI verwendet. Um einen URI im nativen Format (z. B. HTML) anzuzeigen, muss Data Workbench Zugriff auf den Speicherort haben, auf den verwiesen wird, und auf die Anwendung, die zum Öffnen dieses Elements erforderlich ist. Zum Anzeigen einer Webseite benötigt Data Workbench beispielsweise Zugriff auf das Internet sowie einen installierten Webbrowser.

**So bearbeiten Sie Open URI.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Klicken Sie im Ordner &quot;URI&quot;mit der rechten Maustaste auf das Häkchen neben der [!DNL Open URI.vw]Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]** , wenn es sich bei der Datei um eine [!DNL .cfg] Datei handelt, oder **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** , wenn es sich um eine [!DNL .vw] Datei handelt.
1. Klicken Sie auf **[!UICONTROL Command]** und dann **[!UICONTROL Parameters]** , um den Inhalt der Datei anzuzeigen.
1. Ändern Sie den [!DNL Site] Parameter und den Vorlagenparameter nach Bedarf:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diesen Parameter... </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen ein... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Site </p> </td> 
   <td colname="col2"> <p>Der Speicherort der URIs, die Sie öffnen möchten. </p> <p>Beispiel: mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vorlage </p> </td> 
   <td colname="col2"> <p>Die Parameter, die Data Workbench zum Suchen und Öffnen der URIs verwenden sollte. </p> <p>Beispiel: <span class="filepath"> http://%Site%%URI%</span> </p> <p>Die im Beispiel dargestellte Standardvorlage weist Data Workbench an, einen Webbrowser zu öffnen, nach dem im <span class="wintitle"> Site</span> -Parameter definierten Speicherort zu suchen und dann das URI-Dimensionselement zu suchen, das Sie öffnen möchten. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei.
1. Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

