---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 5.0).
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0 oder höher)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0 oder höher){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 5.0).

1. Auf dem Computer, auf dem [!DNL Report Portal] installiert ist, starten Sie den IIS-Manager mit **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** oder **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Auswählen **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Rechtsklick **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Wenn die [!DNL Virtual Directory Wizard] öffnet, klicken **[!UICONTROL Next]**.

1. Führen Sie die folgenden Schritte aus, um den virtuellen Stammordner für [!DNL Report Portal]:

   1. Geben Sie bei Aufforderung zur Eingabe eines Alias den Namen der [!DNL Report Portal]Klicken Sie auf **[!UICONTROL Next]**. Wenn Sie beispielsweise &quot;Portal&quot;als Namen für [!DNL Report Portal], weisen Sie dem virtuellen Verzeichnis den Alias &quot;Portal&quot;zu. Klicken Sie zum Fertigstellen auf **[!UICONTROL Next]**.

   1. Wenn Sie nach dem physischen Pfad gefragt werden, suchen Sie nach dem *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** Verzeichnis, und klicken Sie auf **[!UICONTROL Next]**.

      Beispiel: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Wenn Sie nach Berechtigungen gefragt werden, stellen Sie sicher, dass die folgenden Optionen aktiviert sind:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Klicken Sie auf **[!UICONTROL Next]** und dann auf **[!UICONTROL Finish]**. Das von Ihnen erstellte virtuelle Verzeichnis wird unter der Standard-Website angezeigt, wie im folgenden Beispiel gezeigt.

   ![](assets/RptPort_scrn_VirDirManual.png)

1. Klicken Sie mit der rechten Maustaste auf das gerade erstellte virtuelle Verzeichnis und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Verwenden Sie die [!DNL Virtual Directory] um einen Alias für jedes der folgenden physischen Verzeichnisse zu erstellen. Dadurch wird für jede dieser physischen Ressourcen ein entsprechend benanntes virtuelles Verzeichnis erstellt.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Erstellen Sie diesen Alias . . . </th> 
   <th colname="col2" class="entry"> Für diese physische Ressource . . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Core </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bilder </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> <p>Physischer Speicherort des Ordners, in dem <span class="keyword"> Berichtsserver</span> speichert die Ausgabe für Ihre Berichtssätze. Der Ausgabeordner kann sich an einer beliebigen Stelle befinden, beliebig benannt werden und einen Unterordner für jeden Berichtssatz enthalten. </p> <p>Dieser Ordner muss mit dem Ordner übereinstimmen, den Sie im Parameter "Output Root"im <span class="filepath"> Report.cfg</span> -Datei für einen Berichtssatz. Weitere Informationen finden Sie unter <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Konfigurieren von "Report.cfg"-Dateien</a>. </p> <p>Der Standardspeicherort lautet \<i>PortalName</i>\PortalFiles\Output. </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>Die <i>PortalName</i>\PortalFiles\Output-Ordner enthält den Ordner <span class="filepath"> profiles.xml</span> -Datei, die in das Ausgabeverzeichnis verschoben werden muss, das Sie für diesen Alias angeben. </p> <p>Es ist entscheidend, dass die <span class="wintitle"> Pfad</span> -Attribut korrekt festgelegt ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Wenn Sie fertig sind, überprüfen Sie, ob IIS sechs neue virtuelle Verzeichnisse anzeigt. Stellen Sie sicher, dass die Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie Ihr Portal) und fünf Unterordner wie unten dargestellt hat.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Wenn Sie fertig sind, gehen Sie zu [Bearbeiten der Sitzungskonfigurationsdatei](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) , um den Installationsprozess fortzusetzen.
