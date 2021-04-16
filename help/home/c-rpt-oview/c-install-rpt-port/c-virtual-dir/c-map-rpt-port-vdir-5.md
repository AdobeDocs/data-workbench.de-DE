---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 5.0).
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0 oder höher)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0 oder höher){#mapping-report-portal-to-a-virtual-directory-iis}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 5.0).

1. Beginn Sie auf dem Computer, auf dem [!DNL Report Portal] installiert ist, den IIS Manager entweder mit **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** oder **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Auswählen **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Wenn [!DNL Virtual Directory Wizard] geöffnet wird, klicken Sie auf **[!UICONTROL Next]**.

1. Führen Sie die folgenden Schritte aus, um den virtuellen Stammordner für [!DNL Report Portal] zu definieren:

   1. Geben Sie bei Aufforderung zur Eingabe eines Alias den Namen von [!DNL Report Portal] ein und klicken Sie dann auf **[!UICONTROL Next]**. Wenn Sie beispielsweise &quot;Portal&quot;als Namen von [!DNL Report Portal] verwenden möchten, weisen Sie dem virtuellen Verzeichnis den Alias &quot;Portal&quot;zu. Klicken Sie zum Fertigstellen auf **[!UICONTROL Next]**.

   1. Wenn Sie nach dem physischen Pfad gefragt werden, suchen Sie den Ordner *&lt;**[!UICONTROL PortalName]*** **[!UICONTROL \PortalASP]** und klicken Sie dann auf **[!UICONTROL Next]**.

      Beispiel: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Wenn Sie zur Eingabe von Berechtigungen aufgefordert werden, überprüfen Sie, ob die folgenden Optionen aktiviert sind:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Klicken Sie auf **[!UICONTROL Next]** und dann auf **[!UICONTROL Finish]**. Der virtuelle Ordner, den Sie erstellt haben, wird unter der Standardwebsite angezeigt, wie im folgenden Beispiel gezeigt.

   ![](assets/RptPort_scrn_VirDirManual.png)

1. Klicken Sie mit der rechten Maustaste auf das gerade erstellte virtuelle Verzeichnis und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Verwenden Sie den Assistenten [!DNL Virtual Directory], um einen Alias für jeden der folgenden physischen Ordner zu erstellen. Dadurch wird ein entsprechend benannter virtueller Ordner für jede dieser physischen Ressourcen erstellt.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Erstellen Sie diesen Alias. . . </th> 
   <th colname="col2" class="entry"> Für diese physische Ressource. . . </th> 
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
   <td colname="col2"> <p>Der physische Speicherort des Ordners, in dem <span class="keyword"> Report Server</span> die Ausgabe für Ihre Berichtsätze speichert. Der Ausgabeordner kann sich an einer beliebigen Stelle befinden, beliebig benannt werden und einen Unterordner für jeden Berichtssatz enthalten. </p> <p>Hierbei muss es sich um denselben Ordner handeln, den Sie im Ausgabestammparameter in der Datei <span class="filepath"> Report.cfg</span> für einen Berichtssatz angeben. Weitere Informationen finden Sie unter <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Konfigurieren von Report.cfg-Dateien</a>. </p> <p>Der Standardspeicherort ist \<i>PortalName</i>\PortalFiles\Output. </p> <p>Beispiel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>Die Datei <i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> Profils.xml</span>, die in das Ausgabeverzeichnis verschoben werden muss, das Sie für diesen Alias angeben. </p> <p>Es ist wichtig, dass das Attribut <span class="wintitle"> Path</span> richtig eingestellt ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Stellen Sie nach Abschluss des Vorgangs sicher, dass IIS sechs neue virtuelle Ordner anzeigt. Vergewissern Sie sich, dass die Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie das Portal) und fünf Unterordner wie unten dargestellt hat.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Wenn Sie fertig sind, gehen Sie zu [Bearbeiten Sie die Sitzungskonfigurationsdatei](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7), um den Installationsprozess fortzusetzen.
