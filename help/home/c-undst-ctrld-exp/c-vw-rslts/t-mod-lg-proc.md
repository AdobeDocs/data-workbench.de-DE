---
description: Sie müssen das Feld "x-experiment"der Datei "Log Processing.cfg"hinzufügen, mit der eine erweiterte Dimension erstellt wird.
solution: Insight,Analytics
title: Ändern von "Log Processing.cfg"
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändern von &quot;Log Processing.cfg&quot;{#modifying-log-processing-cfg}

Sie müssen das Feld &quot;x-experiment&quot;der Datei &quot;Log Processing.cfg&quot;hinzufügen, mit der eine erweiterte Dimension erstellt wird.

Siehe [Ändern von &quot;Transformation.cfg&quot;](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**So ändern Sie Log Processing.cfg**

1. Öffnen Sie [!DNL Insight]die Datei, [!DNL Profile Manager] indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** klicken oder indem Sie den Arbeitsbereich &quot;Profilverwaltung&quot;auf der [!DNL Admin] Registerkarte öffnen.
1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Dataset]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das [!DNL Log Processing.cfg] Fenster wird angezeigt.
1. Klicken Sie auf **[!UICONTROL Fields]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das letzte Feld in der aktuellen Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Geben Sie x-experiment in das neu erstellte Feld ein, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/logprocessing.png)

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen [!DNL Log Processing.cfg] in der [!DNL User] Spalte und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* , um die lokal vorgenommenen Änderungen am Arbeitsprofil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Wiederaufbereitung.

   Weitere Informationen zu Protokollverarbeitung und Feldern finden Sie im Handbuch zur Konfiguration von *Datasets*.

