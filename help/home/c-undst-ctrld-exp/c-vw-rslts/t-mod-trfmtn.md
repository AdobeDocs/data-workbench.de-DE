---
description: Nachdem das Feld "x-experiment"verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld "x-experiment"in Ihren Datensatz aufzunehmen, damit Sie Ihre Ergebnisse in Insight anzeigen können.
solution: Analytics
title: Bearbeiten der Datei „Transformation.cfg“
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Bearbeiten der Datei „Transformation.cfg“{#modifying-transformation-cfg}

{{eol}}

Nachdem das Feld &quot;x-experiment&quot;verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld &quot;x-experiment&quot;in Ihren Datensatz aufzunehmen, damit Sie Ihre Ergebnisse in Insight anzeigen können.

Dazu müssen Sie dem [!DNL Transformation.cfg] -Datei.

Wenn Sie mehrere Experimente durchführen möchten, müssen Sie außerdem eine neue Aufspaltungsumwandlung zum [!DNL Transformation.cfg] -Datei. Diese Aufspaltung trennt die verschiedenen Experiment- und Gruppennamen, sodass die Informationen leichter zu interpretieren sind. Um zu vermeiden, dass Ihre Daten erneut verarbeitet werden, wenn Sie zu einem späteren Zeitpunkt zusätzliche Experimente hinzufügen müssen, empfiehlt Adobe, die Split-Transformation hinzuzufügen, selbst wenn Sie derzeit nicht planen, mehrere Experimente durchzuführen.

Das folgende Verfahren umfasst die Erstellung der neuen Aufspaltungsumwandlung und der erweiterten Dimension. Wenn Sie die Split-Transformation nicht hinzufügen möchten, überspringen Sie einfach die Schritte 5 bis 7.

**Ändern von &quot;Transformation.cfg&quot;**

1. In [!DNL Insight], öffnen Sie die [!DNL Profile Manager] durch Rechtsklicken in einem Arbeitsbereich und Klicken auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oder durch Öffnen des Arbeitsbereichs Profilverwaltung im [!DNL Admin] Registerkarte.
1. Im [!DNL Profile Manager]klicken **[!UICONTROL Dataset]** um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transformation.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Die [!DNL Transformation.cfg] angezeigt.
1. Klicken **[!UICONTROL Transformation]** um den Inhalt anzuzeigen.
1. Rechtsklick **[!UICONTROL Transformations]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Schließen Sie die neue Aufspaltung bei der Kommatransformation ab, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Sie können einen beliebigen Wert in das Feld &quot;Name&quot;eingeben.

1. Rechtsklick **[!UICONTROL Extended Dimensions]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Füllen Sie die neue Dimension wie im folgenden Beispiel gezeigt aus:

   ![Schritt-Info](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Sie können einen beliebigen Wert in das Feld &quot;Name&quot;eingeben.
   >* Wenn Sie die Split-Transformation nicht einbezogen haben, müssen Sie &quot;x-experiment&quot;in die [!DNL Input] -Feld.


1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Transformation.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]** , um die lokal vorgenommenen Änderungen am Arbeitsprofil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Umformung.

   Weitere Informationen finden Sie unter [!DNL Transformation.cfg] und erweiterte Dimensionen, siehe *Anleitung zur Datensatzkonfiguration*.
