---
description: Nachdem Sie die Arbeitsbereiche im Berichtssatzordner erstellt und gespeichert haben, müssen Sie eine neue Datei "Report.cfg"erstellen.
title: Konfigurieren des Berichtssatzes
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Konfigurieren des Berichtssatzes{#configure-the-report-set}

Nachdem Sie die Arbeitsbereiche im Berichtssatzordner erstellt und gespeichert haben, müssen Sie eine neue Datei &quot;Report.cfg&quot;erstellen.

Sie müssen in der Datei [!DNL Report.cfg] für den Berichtssatz angeben, wann und wie die Berichte generiert und verteilt werden sollen.

**So erstellen Sie eine neue Report.cfg**

1. Öffnen Sie in Data Workbench das [!DNL Profile Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** klicken.
1. Klicken Sie auf **[!UICONTROL Reports]**, um den Ordner [!DNL Reports] zu öffnen.
1. Klicken Sie auf den Ordner für Ihren Berichtsatz.
1. Klicken Sie in der Spalte [!DNL User] für Ihren Berichtsatzordner mit der rechten Maustaste und wählen Sie **[!UICONTROL Create]** > **[!UICONTROL Report]**. Eine neue Datei [!DNL Report.cfg] wird in der Spalte [!DNL File]angezeigt.
1. Klicken Sie in der Spalte [!DNL User] für die neue Datei [!DNL Report.cfg] mit der rechten Maustaste auf das Häkchen für die Datei [!DNL Report.cfg] und klicken Sie dann auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Schritt-Info](assets/cfg_reportcfg.png)

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Weitere Informationen zu diesen Parametern finden Sie unter [Report.cfg Parameter](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >Das Beispiel [!DNL Report.cfg] in diesem Beispiel enthält standardmäßig nur die Parameter, die in der Datei [!DNL Report.cfg] enthalten sind. Wenn Sie einer [!DNL Report.cfg]-Datei zusätzliche Parameter hinzufügen müssen, müssen Sie dies mit einem Texteditor tun. Anweisungen dazu finden Sie unter [Bearbeiten vorhandener Report.cfg-Dateien](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL Report.cfg (modified)]** oben in der Datei klicken und **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]*****[!UICONTROL \Report.cfg]**klicken.
1. Schließen Sie die Datei.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] für die neue Datei [!DNL Report.cfg] und wählen Sie **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]***.
