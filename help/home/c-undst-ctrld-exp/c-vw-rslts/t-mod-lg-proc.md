---
description: Sie müssen das Feld "x-experiment"der Datei "Log Processing.cfg"hinzufügen, mit der eine erweiterte Dimension erstellt wird.
solution: Analytics,Analytics
title: Bearbeiten der Datei „Log Processing.cfg“
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Bearbeiten der Datei „Log Processing.cfg“{#modifying-log-processing-cfg}

Sie müssen das Feld &quot;x-experiment&quot;der Datei &quot;Log Processing.cfg&quot;hinzufügen, mit der eine erweiterte Dimension erstellt wird.

Siehe [Modifying Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**So ändern Sie Log Processing.cfg**

1. Öffnen Sie in [!DNL Insight] das [!DNL Profile Manager], indem Sie mit der rechten Maustaste auf einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** klicken, oder indem Sie den Arbeitsbereich &quot;Profil-Verwaltung&quot;auf der Registerkarte [!DNL Admin] öffnen.
1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Dataset]**, um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Log Processing.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL Log Processing.cfg] wird angezeigt.
1. Klicken Sie auf **[!UICONTROL Fields]**, um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das letzte Feld in der aktuellen Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Geben Sie x-experiment in das neu erstellte Feld ein, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/logprocessing.png)

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Log Processing.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, um die lokal vorgenommenen Änderungen im funktionierenden Profil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Wiederaufbereitung.

   Weitere Informationen zur Protokollverarbeitung und zu Feldern finden Sie im Handbuch *Konfiguration von Datensätzen*.
