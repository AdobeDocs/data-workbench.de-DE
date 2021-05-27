---
description: Nachdem das Feld "x-experiment"verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld "x-experiment"in Ihren Datensatz aufzunehmen, damit Sie Ihre Ergebnisse in Insight anzeigen können.
solution: Analytics,Analytics
title: Bearbeiten der Datei „Transformation.cfg“
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Bearbeiten der Datei „Transformation.cfg“{#modifying-transformation-cfg}

Nachdem das Feld &quot;x-experiment&quot;verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld &quot;x-experiment&quot;in Ihren Datensatz aufzunehmen, damit Sie Ihre Ergebnisse in Insight anzeigen können.

Dazu müssen Sie der Datei [!DNL Transformation.cfg] eine neue Dimension hinzufügen.

Wenn Sie mehrere Experimente durchführen möchten, müssen Sie der Datei [!DNL Transformation.cfg] auch eine neue Split-Transformation hinzufügen. Diese Aufspaltung trennt die verschiedenen Experiment- und Gruppennamen, sodass die Informationen leichter zu interpretieren sind. Um zu vermeiden, dass Ihre Daten erneut verarbeitet werden, wenn Sie zu einem späteren Zeitpunkt zusätzliche Experimente hinzufügen müssen, empfiehlt Adobe, die Split-Transformation hinzuzufügen, selbst wenn Sie derzeit nicht planen, mehrere Experimente durchzuführen.

Das folgende Verfahren umfasst die Erstellung der neuen Aufspaltungsumwandlung und der erweiterten Dimension. Wenn Sie die Split-Transformation nicht hinzufügen möchten, überspringen Sie einfach die Schritte 5 bis 7.

**Ändern von &quot;Transformation.cfg&quot;**

1. Öffnen Sie in [!DNL Insight] den Ordner [!DNL Profile Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** klicken oder indem Sie den Arbeitsbereich &quot;Profilverwaltung&quot;auf der Registerkarte [!DNL Admin] öffnen.
1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Dataset]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transformation.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL Transformation.cfg] wird angezeigt.
1. Klicken Sie auf **[!UICONTROL Transformation]** , um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Transformations]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Schließen Sie die neue Aufspaltung bei der Kommatransformation ab, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Sie können einen beliebigen Wert in das Feld &quot;Name&quot;eingeben.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Extended Dimensions]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Füllen Sie die neue Dimension wie im folgenden Beispiel gezeigt aus:

   ![Schritt-Info](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Sie können einen beliebigen Wert in das Feld &quot;Name&quot;eingeben.
   >* Wenn Sie die Split-Transformation nicht angegeben haben, müssen Sie &quot;x-experiment&quot;in das Feld [!DNL Input] eingeben.


1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Transformation.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, um die lokal vorgenommenen Änderungen am Arbeitsprofil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Umformung.

   Weitere Informationen zu [!DNL Transformation.cfg] und erweiterten Dimensionen finden Sie im *Handbuch zur Datensatzkonfiguration*.
