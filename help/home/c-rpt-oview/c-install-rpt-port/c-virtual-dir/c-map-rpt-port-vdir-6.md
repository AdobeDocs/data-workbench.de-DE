---
description: Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 6.0).
title: Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 6.0 oder höher)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 6.0 oder höher){#mapping-report-portal-to-a-virtual-directory-iis}

Schritte zum Zuordnen des Report Portals zu einem virtuellen Verzeichnis (IIS 6.0).

Die Zuordnung von [!DNL Report Portal] zu einem virtuellen Verzeichnis auf IIS 6.0 umfasst drei separate Aufgaben:

1. [Konfigurationsdatei bearbeiten](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Konfigurationsdatei in IIS importieren](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Aktivieren von aktiven Serverseiten (ASPs) in IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Du musst alle drei Aufgaben abschließen.

## So bearbeiten Sie die Konfigurationsdatei {#section-eaf1c58935074cfa840dac33e1286520}

1. Öffnen Sie auf dem Computer, auf dem [!DNL Report Portal] installiert ist, \*PortalName*\ReportPortalSetup.xml in einem Texteditor wie Notepad.

1. Verwenden Sie die Such- und Ersetzungsfunktion des Editors, um die Zeichenfolge &quot;VSVirtualPortalName&quot;global durch den Namen Ihres Portals zu ersetzen (Alle ersetzen). Wenn Sie z. B. &quot;VisualReportPortal&quot;als Namen von [!DNL Report Portal] verwenden möchten, suchen Sie nach &quot;VSVirtualPortalName&quot;und ersetzen Sie es durch &quot;VisualReportPortal&quot;.
1. Suchen Sie das folgende Element in dieser Datei:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Stellen Sie das [!DNL Path]-Attribut dieses Elements auf den physischen Speicherort des Ordners ein, in dem [!DNL Report Server] die Ausgabe für Ihre Berichtsätze speichert.

   Der Ausgabeordner kann sich an einer beliebigen Stelle befinden, beliebig benannt werden und einen Unterordner für jeden Berichtssatz enthalten.

   >[!NOTE]
   >
   >Hierbei muss es sich um denselben Ordner handeln, den Sie in der Datei [!DNL Report.cfg] des Ausgabestammparameters für einen Berichtssatz angeben. Weitere Informationen finden Sie unter [Konfigurieren von Report.cfg-Dateien](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   Das folgende Codebeispiel zeigt, wie Sie das [!DNL Path]-Attribut festlegen würden, wenn Ihre Berichte auf [!DNL E:\VSReport\ReportOutput] gespeichert würden:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >Es ist wichtig, dass das [!DNL Path]-Attribut richtig eingestellt ist.

1. Wenn Sie die Standarddatei [!DNL Path] des Elements [!DNL Output] geändert haben, verschieben Sie die Datei [!DNL profiles.xml] aus der Datei *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. Im obigen Beispiel würden Sie [!DNL profiles.xml] nach [!DNL E:\VSReport\ReportOutput] verschieben.

1. Stellen Sie sicher, dass die [!DNL Path]-Attribute für alle anderen [!DNL IIsWebVirtualDir]-Elemente dem richtigen Speicherort zugeordnet werden, indem Sie nach allen Instanzen von [!DNL C:\Inetpub\wwwroot] suchen und sie durch den richtigen Pfad ersetzen.

1. Speichern Sie die Datei. Wenn Sie die Originaldatei beibehalten möchten, können Sie die Konfigurationsdatei unter einem neuen Namen speichern.

## So importieren Sie die Konfigurationsdatei in IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. Beginn Sie auf dem Computer, auf dem [!DNL Report Portal] installiert ist, den IIS Manager mit **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Auswählen **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Default Web Site]** und wählen Sie **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (aus Datei).

1. Wählen Sie die Datei **[!UICONTROL ReportPortalSetup.xml]** und klicken Sie auf **[!UICONTROL Read File]**.

1. Vergewissern Sie sich, dass für Ihr [!DNL Report Portal] sechs virtuelle Ordner aufgeführt sind, wie im folgenden Beispiel gezeigt.

   ![](assets/rptPort_dia_VirDirs.png)

   Wenn Sie keine sechs virtuellen Verzeichnisse sehen oder eine Fehlermeldung erhalten, klicken Sie auf **[!UICONTROL Cancel]** und prüfen Sie die Konfigurationsdatei auf Fehler.

1. Wählen Sie das erste virtuelle Verzeichnis in der Liste aus (das dem übergeordneten Verzeichnis der anderen fünf) und klicken Sie auf **[!UICONTROL OK]**. IIS importiert die Zuordnungen und fügt die virtuellen Ordner zur Standard-Website hinzu.

   Vergewissern Sie sich, dass die resultierende Ordnerstruktur einen übergeordneten Ordner (mit demselben Namen wie Ihr Portal) und fünf Unterordner hat, wie im folgenden Beispiel gezeigt.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Klicken Sie auf jeden virtuellen Ordner, um sicherzustellen, dass IIS den physischen Ordner finden kann, den es darstellt. Wenn IIS einen Fehler anzeigt, klicken Sie mit der rechten Maustaste auf den Namen des virtuellen Ordners und vergewissern Sie sich, dass das [!DNL Local Path]-Feld auf den richtigen physischen Ordner verweist.

## So aktivieren Sie Active Server Pages (ASPs) auf IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Um [!DNL Report Portal] verwenden zu können, müssen ASPs in IIS aktiviert sein. (Standardmäßig sind ASPs deaktiviert, wenn IIS 6.0 installiert ist.) Verwenden Sie das folgende Verfahren, um zu überprüfen, ob ASPs auf Ihrem IIS aktiviert sind.

1. Wählen Sie im Fenster IIS Manager **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Vergewissern Sie sich, dass die Erweiterung [!DNL Active Server Pages] auf [!DNL Allowed] eingestellt ist.

   ![](assets/report_aspenable.png)

1. Wenn ihr Status verboten ist, wählen Sie **[!UICONTROL Active Server Pages]** und klicken Sie auf **[!UICONTROL Allow]**.
1. Schließen Sie IIS Manager.
