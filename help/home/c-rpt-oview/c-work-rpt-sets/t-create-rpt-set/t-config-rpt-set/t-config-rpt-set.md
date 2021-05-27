---
description: Nachdem Sie die Arbeitsbereiche in Ihrem Berichtssatzordner erstellt und gespeichert haben, müssen Sie eine neue Datei "Report.cfg"erstellen.
title: Konfigurieren des Berichtssatzes
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Konfigurieren des Berichtssatzes{#configure-the-report-set}

Nachdem Sie die Arbeitsbereiche in Ihrem Berichtssatzordner erstellt und gespeichert haben, müssen Sie eine neue Datei &quot;Report.cfg&quot;erstellen.

Sie müssen in der [!DNL Report.cfg]-Datei für den Berichtssatz angeben, wann und wie die Berichte erstellt und verteilt werden sollen.

**So erstellen Sie eine neue Report.cfg-Datei**

1. Öffnen Sie in Data Workbench das [!DNL Profile Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** auswählen.
1. Klicken Sie auf **[!UICONTROL Reports]** , um den Ordner [!DNL Reports] zu öffnen.
1. Klicken Sie auf den Ordner für Ihren Berichtssatz.
1. Klicken Sie in der Spalte [!DNL User] für Ihren Berichtsset-Ordner mit der rechten Maustaste und wählen Sie **[!UICONTROL Create]** > **[!UICONTROL Report]** aus. Eine neue [!DNL Report.cfg]-Datei wird in der Spalte [!DNL File]angezeigt.
1. Klicken Sie in der Spalte [!DNL User] für die neue Datei [!DNL Report.cfg] mit der rechten Maustaste auf das Häkchen für die Datei [!DNL Report.cfg] und klicken Sie dann auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Schritt-Info](assets/cfg_reportcfg.png)

1. Bearbeiten Sie die Konfigurationsparameter wie gewünscht. Weitere Informationen zu diesen Parametern finden Sie unter [Report.cfg-Parameter](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >Das in diesem Beispiel gezeigte Muster [!DNL Report.cfg] enthält standardmäßig nur die Parameter in der Datei [!DNL Report.cfg] . Wenn Sie zusätzliche Parameter zu einer [!DNL Report.cfg]-Datei hinzufügen müssen, müssen Sie dies mit einem Texteditor tun. Anweisungen dazu finden Sie unter [Bearbeiten vorhandener Report.cfg-Dateien](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL Report.cfg (modified)]** oben in der Datei klicken und **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]*****[!UICONTROL \Report.cfg]**klicken.
1. Schließen Sie die Datei.
1. Klicken Sie in [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] für die neue Datei [!DNL Report.cfg] und wählen Sie **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]***.
