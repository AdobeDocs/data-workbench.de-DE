---
description: Schritte zum Ändern der Standardvisualisierung.
title: Konfigurieren der Oberfläche für das Datensatzschema
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Konfigurieren der Oberfläche für das Datensatzschema{#configure-the-dataset-schema-interface}

Schritte zum Ändern der Standardvisualisierung.

Sie können steuern, welcher Visualisierungstyp angezeigt wird, wenn Sie in einem [!DNL Dataset Schema Interface] auf einen Dimensionsnamen klicken, indem Sie Dateien zum Profilnamen\*\Context\Dimension Legend folder of the Data Workbench server installation folder hinzufügen. Die [!DNL Default.1d]-Datei in diesem Ordner steuert den standardmäßigen Visualisierungstyp für alle Dimensionen. Durch Hinzufügen der Datei *Dimensionsname*.1d (z. B. [!DNL Hour.1d]) zu diesem Ordner können Sie die Standardvisualisierung für diese Dimension steuern.

Weitere Informationen zu [!DNL Dataset Schema Interfaces] finden Sie unter [Die Oberfläche für Datensatzschemata](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**So ändern Sie die Standardvisualisierung**

1. Erstellen Sie in jedem Arbeitsbereich eine Visualisierung mit den Daten, die Sie in der neuen Standardvisualisierung anzeigen möchten.

   Wenn Sie beispielsweise möchten, dass die Dimension in einem Balkendiagramm angezeigt wird, erstellen Sie eine Balkendiagrammvisualisierung, die die gewünschte Metrik und Dimension anzeigt.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie im Fenster [!DNL Save] auf ![](assets/btn_folder_up.png), doppelklicken Sie auf **[!UICONTROL Context]** und doppelklicken Sie dann auf **[!UICONTROL Dimension Legend]**.
1. Geben Sie im Feld [!DNL File Name] den Dimensionsnamen ein.

   Der Name der Datei [!DNL .1d] muss exakt mit dem Namen der Dimension übereinstimmen. Beispiel: [!DNL Hour.1d].

1. Ändern Sie die Dateierweiterung in &quot;1d&quot;und klicken Sie auf **[!UICONTROL Save]**.

   Die Datei wird unter dem Benutzernamen des Arbeitsprofils &quot;\Context\Dimension Legend folder&quot;gespeichert.

   Wenn Sie das nächste Mal in einem [!DNL Dataset Schema Interface] auf diese Dimension klicken, wird die von Ihnen angegebene Visualisierung angezeigt.

1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen:

   1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Context]** und dann auf **[!UICONTROL Dimension Legend]**.

   1. Klicken Sie in der Spalte [!DNL User] mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des neuen Callout und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
