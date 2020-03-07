---
description: Nachdem das Feld "x-experiment"verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld "x-experiment"in Ihr Dataset einzuschließen, sodass Sie Ihre Ergebnisse in Insight anzeigen können.
solution: Insight,Analytics
title: Ändern von "Transformation.cfg"
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Ändern von &quot;Transformation.cfg&quot;{#modifying-transformation-cfg}

Nachdem das Feld &quot;x-experiment&quot;verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld &quot;x-experiment&quot;in Ihr Dataset einzuschließen, sodass Sie Ihre Ergebnisse in Insight anzeigen können.

Dazu müssen Sie der [!DNL Transformation.cfg] Datei eine neue Dimension hinzufügen.

Wenn Sie mehrere Experimente durchführen möchten, müssen Sie der [!DNL Transformation.cfg] Datei auch eine neue Teilung hinzufügen. Diese Transformation trennt die verschiedenen Experiment- und Gruppennamen, sodass die Informationen einfacher zu interpretieren sind. Um eine erneute Verarbeitung Ihrer Daten zu vermeiden, wenn Sie zu einem späteren Zeitpunkt zusätzliche Experimente hinzufügen müssen, empfiehlt Adobe, die Teilung-Transformation hinzuzufügen, auch wenn Sie derzeit nicht planen, mehrere Experimente auszuführen.

Das folgende Verfahren umfasst die Erstellung der neuen Split-Transformation und der erweiterten Dimension. Wenn Sie die Teilung nicht hinzufügen möchten, überspringen Sie einfach die Schritte 5-7.

**So ändern Sie Transformation.cfg**

1. Öffnen Sie [!DNL Insight]die Datei, [!DNL Profile Manager] indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** klicken oder indem Sie den Arbeitsbereich &quot;Profilverwaltung&quot;auf der [!DNL Admin] Registerkarte öffnen.
1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Dataset]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transformation.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das [!DNL Transformation.cfg] Fenster wird angezeigt.
1. Klicken Sie auf **[!UICONTROL Transformation]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Transformations]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Schließen Sie die neue Aufteilung bei der Kommaumwandlung ab, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Sie können einen beliebigen Wert in das Feld Name eingeben.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Extended Dimensions]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Schließen Sie die neue Dimension wie im folgenden Beispiel ab:

   ![Schritt-Info](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Sie können einen beliebigen Wert in das Feld Name eingeben.
   >* Wenn Sie die Teilung nicht einbezogen haben, müssen Sie &quot;x-experiment&quot;in das [!DNL Input] Feld eingeben.


1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der [!DNL Profile Manager]Spalte mit der rechten Maustaste auf das Häkchen [!DNL Transformation.cfg] in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]** , um die lokal vorgenommenen Änderungen am Arbeitsprofil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Umformung.

   Weitere Informationen zu [!DNL Transformation.cfg] und erweiterten Dimensionen finden Sie im Handbuch zur Konfiguration von *Datasets*.
