---
description: Nachdem das Feld "x-experiment"verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld "x-experiment"in Ihr Dataset einzuschließen, sodass Sie Ihre Ergebnisse in Insight Ansicht haben.
solution: Analytics,Analytics
title: Bearbeiten der Datei „Transformation.cfg“
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Bearbeiten der Datei „Transformation.cfg“{#modifying-transformation-cfg}

Nachdem das Feld &quot;x-experiment&quot;verfügbar ist, müssen Sie eine erweiterte Dimension erstellen, um das Feld &quot;x-experiment&quot;in Ihr Dataset einzuschließen, sodass Sie Ihre Ergebnisse in Insight Ansicht haben.

Dazu müssen Sie der Datei [!DNL Transformation.cfg] eine neue Dimension hinzufügen.

Wenn Sie mehrere Experimente durchführen möchten, müssen Sie der Datei [!DNL Transformation.cfg] auch eine neue Teilung hinzufügen. Diese Transformation trennt die verschiedenen Experiment- und Gruppennamen, sodass die Informationen einfacher zu interpretieren sind. Um eine erneute Verarbeitung Ihrer Daten zu vermeiden, wenn Sie zu einem späteren Zeitpunkt zusätzliche Experimente hinzufügen müssen, empfiehlt Adobe, die Teilung-Transformation hinzuzufügen, auch wenn Sie derzeit nicht planen, mehrere Experimente auszuführen.

Das folgende Verfahren umfasst die Erstellung der neuen Split-Transformation und der erweiterten Dimension. Wenn Sie die Teilung nicht hinzufügen möchten, überspringen Sie einfach die Schritte 5-7.

**So ändern Sie Transformation.cfg**

1. Öffnen Sie in [!DNL Insight] das [!DNL Profile Manager], indem Sie mit der rechten Maustaste auf einen Arbeitsbereich klicken und auf **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** klicken, oder indem Sie den Arbeitsbereich &quot;Profil-Verwaltung&quot;auf der Registerkarte [!DNL Admin] öffnen.
1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Dataset]**, um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transformation.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL Transformation.cfg] wird angezeigt.
1. Klicken Sie auf **[!UICONTROL Transformation]**, um den Inhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Transformations]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Schließen Sie die neue Aufteilung bei der Kommaumwandlung ab, wie im folgenden Beispiel gezeigt:

   ![Schritt-Info](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Sie können einen beliebigen Wert in das Feld Name eingeben.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Extended Dimensions]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Schließen Sie die neue Dimension wie im folgenden Beispiel ab:

   ![Schritt-Info](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Sie können einen beliebigen Wert in das Feld Name eingeben.
   >* Wenn Sie die Teilung nicht einbezogen haben, müssen Sie &quot;x-experiment&quot;in das Feld [!DNL Input] eingeben.


1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Transformation.cfg] in der Spalte [!DNL User] und dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, um die lokal vorgenommenen Änderungen am funktionierenden Profil zu speichern.

   >[!NOTE]
   >
   >Der Datensatz beginnt sofort mit der Umformung.

   Weitere Informationen zu den Dimensionen [!DNL Transformation.cfg] und Erweitert finden Sie im Handbuch *Konfiguration von Datensätzen*.
