---
description: Sie müssen das Feld x-experiment zur Datei Log Processing.cfg hinzufügen, die zum Erstellen einer erweiterten Dimension verwendet wird.
solution: Analytics,Analytics
title: Bearbeiten der Datei „Log Processing.cfg“
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Bearbeiten der Datei „Log Processing.cfg“{#modifying-log-processing-cfg}

Sie müssen das Feld x-experiment zur Datei Log Processing.cfg hinzufügen, die zum Erstellen einer erweiterten Dimension verwendet wird.

Siehe [Ändern von Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Ändern der Protokollverarbeitung.cfg**

1. Öffnen Sie in [!DNL Insight] den Ordner [!DNL Profile Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** klicken oder indem Sie den Arbeitsbereich &quot;Profilverwaltung&quot;auf der Registerkarte [!DNL Admin] öffnen.
1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Dataset]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL Log Processing.cfg] wird angezeigt.
1. Klicken Sie auf **[!UICONTROL Fields]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das letzte Feld in der aktuellen Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Geben Sie im neu erstellten Feld x-experiment ein, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/logprocessing.png)

1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Log Processing.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, um die lokal vorgenommenen Änderungen am Arbeitsprofil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Wiederaufbereitung.

   Weitere Informationen zur Protokollverarbeitung und zu Feldern finden Sie im *Handbuch zur Datensatzkonfiguration*.
