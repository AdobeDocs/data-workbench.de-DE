---
description: Schritte zum Ändern der Standardvisualisierung.
solution: Analytics
title: Konfigurieren der DataSet-Schemaschnittstelle
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Konfigurieren der DataSet-Schemaschnittstelle{#configure-the-dataset-schema-interface}

Schritte zum Ändern der Standardvisualisierung.

Sie können steuern, welcher Visualisierungstyp angezeigt wird, wenn Sie auf einen Dimensionsnamen in einem Dokument klicken, [!DNL Dataset Schema Interface] indem Sie Dateien zum Profilnamen hinzufügen\*\Context\Dimension Legend folder of the Data Workbench server installation folder. Die [!DNL Default.1d] Datei in diesem Ordner steuert den standardmäßigen Visualisierungstyp für alle Dimensionen. Durch Hinzufügen einer *Dimensionsdatei*.1d (z. B. [!DNL Hour.1d]) zu diesem Ordner können Sie die Standardvisualisierung für diese Dimension steuern.

Weitere Informationen [!DNL Dataset Schema Interfaces]finden Sie unter [Die DataSet-Schemaschnittstelle](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**So ändern Sie die Standardvisualisierung**

1. Erstellen Sie in jedem Arbeitsbereich eine Visualisierung mit den Daten, die in der neuen Standardvisualisierung angezeigt werden sollen.

   Wenn die Dimension beispielsweise in einem Balkendiagramm angezeigt werden soll, erstellen Sie eine Balkendiagramm-Visualisierung, die die gewünschte Metrik und Dimension anzeigt.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Aufruffensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie im [!DNL Save] Fenster auf ![](assets/btn_folder_up.png), doppelklicken Sie **[!UICONTROL Context]** und doppelklicken Sie dann auf **[!UICONTROL Dimension Legend]**.
1. Geben Sie in das [!DNL File Name] Feld den Dimensionsnamen ein.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. Beispiel: [!DNL Hour.1d].

1. Ändern Sie die Dateierweiterung in &quot;1d&quot;und klicken Sie auf **[!UICONTROL Save]**.

   Die Datei wird im Arbeitsprofilnamen des Benutzers gespeichert*\Context\Dimension Legend folder.

   Wenn Sie das nächste Mal in einer [!DNL Dataset Schema Interface]Ansicht auf diese Dimension klicken, wird die von Ihnen angegebene Visualisierung angezeigt.

1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen:

   1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Dimension Legend]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des neuen Aufrufs in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

