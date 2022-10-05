---
description: Sie müssen das Feld x-experiment zur Datei Log Processing.cfg hinzufügen, die zum Erstellen einer erweiterten Dimension verwendet wird.
solution: Analytics
title: Bearbeiten der Datei „Log Processing.cfg“
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Bearbeiten der Datei „Log Processing.cfg“{#modifying-log-processing-cfg}

{{eol}}

Sie müssen das Feld x-experiment zur Datei Log Processing.cfg hinzufügen, die zum Erstellen einer erweiterten Dimension verwendet wird.

Siehe [Ändern von &quot;Transformation.cfg&quot;](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Ändern der Protokollverarbeitung.cfg**

1. In [!DNL Insight], öffnen Sie die [!DNL Profile Manager] durch Rechtsklicken in einem Arbeitsbereich und Klicken auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oder durch Öffnen des Arbeitsbereichs Profilverwaltung im [!DNL Admin] Registerkarte.
1. Im [!DNL Profile Manager]klicken **[!UICONTROL Dataset]** um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Die [!DNL Log Processing.cfg] angezeigt.
1. Klicken **[!UICONTROL Fields]** um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das letzte Feld in der aktuellen Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Geben Sie im neu erstellten Feld x-experiment ein, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/logprocessing.png)

1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Log Processing.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* , um die lokal vorgenommenen Änderungen am Arbeitsprofil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Wiederaufbereitung.

   Weitere Informationen zur Protokollverarbeitung und zu Feldern finden Sie unter *Anleitung zur Datensatzkonfiguration*.
