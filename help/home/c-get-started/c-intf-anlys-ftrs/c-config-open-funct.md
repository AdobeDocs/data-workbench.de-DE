---
description: Mit der Funktion "Öffnen"können Sie Elemente wie Dokumente oder URIs in externen Anwendungen wie einem Texteditor oder einem Webbrowser öffnen.
title: Konfigurieren der Funktion zum Öffnen
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# Konfigurieren der Funktion zum Öffnen{#configure-open-functionality}

{{eol}}

Mit der Funktion &quot;Öffnen&quot;können Sie Elemente wie Dokumente oder URIs in externen Anwendungen wie einem Texteditor oder einem Webbrowser öffnen.

Die Open-Funktion ist derzeit nur in der [!DNL Site] und nur zum Öffnen von URIs. Dieser Abschnitt enthält Informationen zum Konfigurieren der Open URI-Funktionalität für [!DNL Site]. Informationen zum Konfigurieren der Open-Funktionalität für eine andere Anwendung oder zum Öffnen anderer Elemente erhalten Sie von Adobe Consulting Services.

In [!DNL Site]können Sie mit der rechten Maustaste auf einen URI aus einer Seitenüberlagerung oder Tabelle klicken, um den URI in der Anwendung anzuzeigen, für die er formatiert wurde. Beispielsweise können Sie in einer Visualisierung einer URI-Tabelle auf einen URI klicken, um eine Webseite in einem Webbrowser anzuzeigen.

Um einen URI aus einer Visualisierung zu öffnen, müssen Sie zunächst die [!DNL Open URI.cfg] -Datei für die URI-Dimension, um den Speicherort und die Benennungskonventionen zu identifizieren, die Data Workbench zum Öffnen des URI verwendet. Um einen URI im nativen Format anzuzeigen (z. B. HTML), muss die Data Workbench Zugriff auf den referenzierten Speicherort und die Anwendung haben, die zum Öffnen des Elements erforderlich sind. Um beispielsweise eine Webseite anzuzeigen, muss die Data Workbench auf das Internet zugreifen und einen Webbrowser installieren.

**So bearbeiten Sie Open URI.vw**

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Klicken Sie im URI-Ordner mit der rechten Maustaste auf das Häkchen neben dem [!DNL Open URI.vw]Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]** wenn die Datei ein [!DNL .cfg] Datei oder **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** wenn es sich um eine [!DNL .vw] -Datei.
1. Klicken **[!UICONTROL Command]**, dann **[!UICONTROL Parameters]** um den Inhalt der Datei anzuzeigen.
1. Ändern Sie die [!DNL Site] und dem Vorlagenparameter nach Bedarf:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Für diesen Parameter ... </th>
   <th colname="col2" class="entry"> Geben Sie diese Informationen an... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Site </p> </td>
   <td colname="col2"> <p>Der Speicherort der URIs, die Sie öffnen möchten. </p> <p>Beispiel: mysite.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Vorlage </p> </td>
   <td colname="col2"> <p>Die Parameter, die von Data Workbench zum Suchen und Öffnen der URIs verwendet werden sollen. </p> <p>Beispiel: <span class="filepath"> https://%Site%%URI%</span> </p> <p>Die im Beispiel dargestellte Standardvorlage weist die Data Workbench an, einen Webbrowser zu öffnen, nach dem Speicherort zu suchen, der in der Variablen <span class="wintitle"> Site</span> und suchen Sie dann das URI-Dimensionselement, das Sie öffnen möchten. </p> </td>
  </tr>
 </tbody>
</table>

1. Speichern Sie die Datei.
1. Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL .vw] in der Datei [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
