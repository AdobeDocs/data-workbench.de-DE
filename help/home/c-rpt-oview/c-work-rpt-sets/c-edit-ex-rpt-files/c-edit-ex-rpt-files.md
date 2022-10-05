---
description: Schritte zum Bearbeiten vorhandener Report.cfg-Dateien mithilfe von Worktop oder einem Texteditor.
title: Bearbeiten vorhandener Report.cfg-Dateien
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Bearbeiten vorhandener Report.cfg-Dateien{#editing-existing-report-cfg-files}

{{eol}}

Schritte zum Bearbeiten vorhandener Report.cfg-Dateien mithilfe von Worktop oder einem Texteditor.

>[!NOTE]
>
>* Sie müssen online arbeiten, um [!DNL Report.cfg] Dateien. Um online zu arbeiten, verwenden Sie die [!DNL Worktop]klicken Sie mit der rechten Maustaste auf die Titelleiste und klicken Sie auf **[!UICONTROL Work Online]**.
>
>* Wenn die Variable **[!UICONTROL Allow Report Regeneration]** -Parameter in der [!DNL Report.cfg] -Datei auf [!DNL True], wenn Sie Änderungen an dieser Datei vornehmen und diese Datei wieder auf dem Server speichern, [!DNL Report] generiert die Berichte in diesem Satz automatisch neu. Obwohl die Berichte neu generiert werden, werden sie nicht erneut per E-Mail gesendet. Anweisungen hierzu finden Sie unter [Erneutes Senden von Berichten per E-Mail](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>


Sie können vorhandene [!DNL Report.cfg] von [!DNL Worktop] oder einen Texteditor verwenden.

Bearbeiten von [!DNL Report.cfg] -Datei mithilfe der [!DNL Reports] des [!DNL Worktop] können Sie nur die Parameter, Vektoren und Vektorelemente bearbeiten, die bereits in der Datei vorhanden sind. Wenn Sie einen Parameter oder Vektor zur Datei hinzufügen müssen, müssen Sie ihn mithilfe eines Texteditors wie Notepad bearbeiten.

* [So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;über die Arbeitsfläche](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mit einem Texteditor](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;über die Arbeitsfläche {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Sie müssen online arbeiten, um die [!DNL Report.cfg] von [!DNL Worktop].

1. In Data Workbench auf der [!DNL Reports] wählen Sie den Unterordner (Registerkarte oder Dropdown-Unterverzeichnis) für den Berichtssatz aus, den Sie konfigurieren möchten.
1. Klicken Sie auf **[!UICONTROL Report.cfg]**. Die Parameter der [!DNL Report.cfg] für diesen Berichtssatz anzeigen.

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Weitere Informationen zu diesen Parametern finden Sie unter [Parameter &quot;Report.cfg&quot;](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL Report.cfg (modified)]** oben in den Parametern und klicken Sie auf **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mit einem Texteditor {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Öffnen Sie die [!DNL Reports Manager] durch Rechtsklicken in einem Arbeitsbereich und Klicken auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Klicken Sie auf den Ordner für Ihren Berichtssatz.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem [!DNL Report.cfg] für diesen Berichtssatz und klicken Sie auf **[!UICONTROL Make Local]**.

1. Im [!DNL User] klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Report.cfg] für diesen Berichtssatz und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL Report.cfg] Datei geöffnet.

   Beispiel [!DNL Report.cfg] angezeigt in [Berichtssatz konfigurieren](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) enthält nur die Parameter, die im [!DNL Report.cfg] -Datei. Im folgenden Beispiel werden alle für die [!DNL Report.cfg] -Datei, die Sie als Modelle für Ihre Parametereinträge verwenden können:

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

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Weitere Informationen zu diesen Parametern finden Sie unter [Parameter &quot;Report.cfg&quot;](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Speichern und schließen Sie die Datei.
1. Im [!DNL Reports Manager]klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL User] Spalte für [!DNL Report.cfg] Datei und wählen Sie **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
