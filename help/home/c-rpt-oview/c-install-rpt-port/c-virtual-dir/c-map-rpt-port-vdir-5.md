---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 5.0).
solution: Analytics
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 5.0).

1. Starten Sie auf dem Computer, auf dem der IIS Manager installiert [!DNL Report Portal] ist, den IIS Manager entweder mit **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** oder **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Auswählen **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Klicken Sie [!DNL Virtual Directory Wizard] beim Öffnen auf **[!UICONTROL Next]**.

1. Führen Sie die folgenden Schritte aus, um den virtuellen Stammordner für [!DNL Report Portal]Folgendes zu definieren:

   1. Geben Sie bei Aufforderung zur Eingabe eines Alias den Namen des Alias ein [!DNL Report Portal]und klicken Sie dann auf **[!UICONTROL Next]**. Wenn Sie z. B. &quot;Portal&quot;als Namen verwenden möchten, weisen Sie dem virtuellen Verzeichnis den Aliasnamen &quot;Portal&quot;zu [!DNL Report Portal]. Klicken Sie zum Fertigstellen auf **[!UICONTROL Next]**.

   1. Wenn Sie nach dem physischen Pfad gefragt werden, suchen Sie den Ordner *&lt;**[!UICONTROL PortalName]**>* und wählen Sie ihn aus. Klicken Sie dann auf **[!UICONTROL \PortalASP]** **[!UICONTROL Next]**.

      Beispiel: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Wenn Sie zur Eingabe von Berechtigungen aufgefordert werden, überprüfen Sie, ob die folgenden Optionen aktiviert sind:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Click **[!UICONTROL Next]**, then click **[!UICONTROL Finish]**. Der virtuelle Ordner, den Sie erstellt haben, wird unter der Standardwebsite angezeigt, wie im folgenden Beispiel gezeigt.
   ![](assets/RptPort_scrn_VirDirManual.png)

1. Klicken Sie mit der rechten Maustaste auf das virtuelle Verzeichnis, das Sie gerade erstellt haben, und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Verwenden Sie den [!DNL Virtual Directory] Assistenten, um einen Alias für jeden der folgenden physischen Ordner zu erstellen. Dadurch wird ein entsprechend benannter virtueller Ordner für jede dieser physischen Ressourcen erstellt.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Erstellen Sie diesen Alias. . . </th> 
   <th colname="col2" class="entry"> Für diese physische Ressource. . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Kern </td> 
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
   <td colname="col2"> <p>Der physische Speicherort des Ordners, in dem der <span class="keyword"> Berichtsserver</span> die Ausgabe für Ihre Berichtsätze speichert. Der Ausgabeordner kann sich an einer beliebigen Stelle befinden, beliebig benannt werden und einen Unterordner für jeden Berichtssatz enthalten. </p> <p>Hierbei muss es sich um denselben Ordner handeln, den Sie in der Datei "Report.cfg <span class="filepath"></span> "im Parameter "Ausgabestamm"für einen Berichtssatz angeben. Weitere Informationen finden Sie unter Report.cfg-Dateien <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> konfigurieren</a>. </p> <p>Der Standardspeicherort lautet \<i>PortalName</i>\PortalFiles\Output. </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>Die <i>Datei "PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profiles.xml</span> ", die in den Ausgabeverzeichnis verschoben werden muss, den Sie für diesen Alias angeben. </p> <p>Es ist äußerst wichtig, dass das <span class="wintitle"> Path</span> -Attribut richtig eingestellt ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Stellen Sie nach Abschluss des Vorgangs sicher, dass IIS sechs neue virtuelle Ordner anzeigt. Vergewissern Sie sich, dass die Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie das Portal) und fünf Unterordner wie unten dargestellt hat.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Wenn Sie fertig sind, fahren Sie mit dem Installationsprozess fort, indem Sie die Sitzungskonfigurationsdatei [bearbeiten](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) .

