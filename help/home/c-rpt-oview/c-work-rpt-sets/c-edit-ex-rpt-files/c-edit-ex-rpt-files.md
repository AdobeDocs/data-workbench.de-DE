---
description: Schritte zum Bearbeiten vorhandener Report.cfg-Dateien mit Worktop oder einem Texteditor.
title: Bearbeiten vorhandener Report.cfg-Dateien
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Bearbeiten vorhandener Report.cfg-Dateien{#editing-existing-report-cfg-files}

Schritte zum Bearbeiten vorhandener Report.cfg-Dateien mit Worktop oder einem Texteditor.

>[!NOTE]
>
>* Sie müssen online arbeiten, um [!DNL Report.cfg]-Dateien zu bearbeiten. Um online zu arbeiten, klicken Sie mit der rechten Maustaste auf die Titelleiste und dann auf **[!UICONTROL Work Online]**.[!DNL Worktop]
   >
   >
* Wenn der Parameter **[!UICONTROL Allow Report Regeneration]** in der Datei [!DNL Report.cfg] auf [!DNL True] eingestellt ist und Sie Änderungen an dieser Datei vornehmen und diese Datei wieder auf dem Server speichern, generiert [!DNL Report] automatisch die Berichte in diesem Satz. Obwohl die Berichte neu generiert werden, werden sie nicht erneut per E-Mail gesendet. Anweisungen hierzu finden Sie unter [Berichte per E-Mail senden](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).

>



Sie können ein vorhandenes [!DNL Report.cfg] vom [!DNL Worktop] oder mithilfe eines Texteditors bearbeiten.

Durch Bearbeiten einer [!DNL Report.cfg]-Datei mit der Registerkarte [!DNL Reports] von [!DNL Worktop] können Sie nur die Parameter, Vektoren und Vektorelemente bearbeiten, die bereits in der Datei vorhanden sind. Wenn Sie der Datei einen Parameter oder Vektor hinzufügen müssen, müssen Sie ihn mit einem Texteditor wie Notepad bearbeiten.

* [So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mithilfe von &quot;Worktop&quot;](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mit einem Texteditor](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## So bearbeiten Sie eine vorhandene Datei &quot;Report.cfg&quot;mit der Arbeitsfläche {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Sie müssen online arbeiten, um [!DNL Report.cfg] von [!DNL Worktop] zu bearbeiten.

1. Wählen Sie in der Data Workbench auf der Registerkarte [!DNL Reports] den Unterordner (Register- oder Dropdown-Unterordner) für den zu konfigurierenden Berichtssatz aus.
1. Klicken Sie auf **[!UICONTROL Report.cfg]**. Die Parameter von [!DNL Report.cfg] für diesen Berichtssatz werden angezeigt.

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Weitere Informationen zu diesen Parametern finden Sie unter [Report.cfg Parameter](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL Report.cfg (modified)]** oben in den Parametern klicken und auf **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]***klicken.

## So bearbeiten Sie eine vorhandene Report.cfg-Datei mit einem Texteditor {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Öffnen Sie das [!DNL Reports Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]** klicken.

1. Klicken Sie auf den Ordner für Ihren Berichtsatz.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Report.cfg] für diesen Berichtsatz und klicken Sie auf **[!UICONTROL Make Local]**.

1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen neben [!DNL Report.cfg] für diesen Berichtsatz und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Report.cfg] wird geöffnet.

   Das in [Berichtssatz konfigurieren](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) dargestellte Muster [!DNL Report.cfg] enthält standardmäßig nur die Parameter, die in der Datei [!DNL Report.cfg] enthalten sind. Das folgende Beispiel enthält alle Parameter, die für die Datei [!DNL Report.cfg] verfügbar sind und die Sie als Modelle für Parametereinträge verwenden können:

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

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Weitere Informationen zu diesen Parametern finden Sie unter [Report.cfg Parameter](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Speichern und schließen Sie die Datei.
1. Klicken Sie in der Spalte [!DNL Reports Manager] mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] für die Datei [!DNL Report.cfg] und wählen Sie **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]***.
