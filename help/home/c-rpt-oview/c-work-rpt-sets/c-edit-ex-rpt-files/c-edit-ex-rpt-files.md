---
description: Schritte zum Bearbeiten vorhandener Report.cfg-Dateien mit Worktop oder einem Texteditor.
solution: Analytics
title: Bearbeiten vorhandener Report.cfg-Dateien
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bearbeiten vorhandener Report.cfg-Dateien{#editing-existing-report-cfg-files}

Schritte zum Bearbeiten vorhandener Report.cfg-Dateien mit Worktop oder einem Texteditor.

>[!NOTE]
>
>* Sie müssen online arbeiten, um [!DNL Report.cfg] Dateien zu bearbeiten. Um online zu arbeiten, klicken Sie mit der rechten Maustaste [!DNL Worktop]auf die Titelleiste und dann auf **[!UICONTROL Work Online]**.
   >
   >
* Wenn der **[!UICONTROL Allow Report Regeneration]** Parameter in der [!DNL Report.cfg] Datei auf [!DNL True][!DNL Report] festgelegt ist, werden die Berichte in diesem Satz automatisch neu generiert, wenn Sie Änderungen an dieser Datei vornehmen und diese Datei wieder auf dem Server speichern. Obwohl die Berichte neu generiert werden, werden sie nicht erneut per E-Mail gesendet. Anweisungen hierzu finden Sie unter [Berichte per E-Mail](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607)zurücksenden.
>



Sie können eine vorhandene Datei [!DNL Report.cfg] über den [!DNL Worktop] Texteditor oder einen Texteditor bearbeiten.

Wenn Sie eine [!DNL Report.cfg] Datei auf der [!DNL Reports] Registerkarte des [!DNL Worktop] Fensters bearbeiten, können Sie nur die Parameter, Vektoren und Vektorelemente bearbeiten, die bereits in der Datei vorhanden sind. Wenn Sie der Datei einen Parameter oder Vektor hinzufügen müssen, müssen Sie ihn mit einem Texteditor wie Notepad bearbeiten.

* [So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mithilfe von &quot;Worktop&quot;](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mit einem Texteditor](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mithilfe von &quot;Worktop&quot; {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Sie müssen online arbeiten, um die [!DNL Report.cfg] von der zu bearbeiten [!DNL Worktop].

1. Wählen Sie in der Data Workbench auf der [!DNL Reports] Registerkarte den Unterordner (Register- oder Dropdown-Unterordner) für den zu konfigurierenden Berichtssatz aus.
1. Klicken Sie auf **[!UICONTROL Report.cfg]**. Die Parameter des [!DNL Report.cfg] Berichts werden angezeigt.

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Informationen zu diesen Parametern finden Sie unter [Report.cfg-Parameter](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL Report.cfg (modified)]** oben auf die Parameter klicken und auf **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*klicken.

## So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mit einem Texteditor {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Öffnen Sie die [!DNL Reports Manager] Datei, indem Sie mit der rechten Maustaste auf einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Klicken Sie auf den Ordner für Ihren Berichtsatz.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem [!DNL Report.cfg] für diesen Berichtssatz und klicken Sie auf **[!UICONTROL Make Local]**.

1. Klicken Sie in der [!DNL User] Spalte mit der rechten Maustaste auf das Häkchen neben [!DNL Report.cfg] für diesen Berichtsatz und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL Report.cfg] Datei wird geöffnet.

   Das Beispiel [!DNL Report.cfg] unter [Berichtssatz](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) konfigurieren enthält standardmäßig nur die in der [!DNL Report.cfg] Datei enthaltenen Parameter. Das folgende Beispiel enthält alle Parameter, die für die [!DNL Report.cfg] Datei verfügbar sind und als Modelle für Parametereinträge verwendet werden können:

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Informationen zu diesen Parametern finden Sie unter [Report.cfg-Parameter](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Speichern und schließen Sie die Datei.
1. Klicken Sie im [!DNL Reports Manager]Kontextmenü mit der rechten Maustaste auf das Häkchen in der [!DNL User] Spalte für die [!DNL Report.cfg] Datei und wählen Sie **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.

