---
description: Schritte zum Ändern der Standardvisualisierung.
title: Konfigurieren der Oberfläche für das Datensatzschema
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Konfigurieren der Oberfläche für das Datensatzschema{#configure-the-dataset-schema-interface}

{{eol}}

Schritte zum Ändern der Standardvisualisierung.

Sie können steuern, welcher Visualisierungstyp angezeigt wird, wenn Sie auf einen Dimensionsnamen in einem [!DNL Dataset Schema Interface] durch Hinzufügen von Dateien zum Ordner Profile\*profile name*\Context\Dimension Legende des Installationsordners des Data Workbench-Servers. Die [!DNL Default.1d] -Datei in diesem Ordner steuert den standardmäßigen Visualisierungstyp für alle Dimensionen. Durch Hinzufügen eines *Dimensionsname*.1d-Datei (z. B. [!DNL Hour.1d]), können Sie die Standardvisualisierung für diese Dimension steuern.

Weitere Informationen finden Sie unter [!DNL Dataset Schema Interfaces], siehe [Die Oberfläche des Datensatzschemas](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**So ändern Sie die Standardvisualisierung**

1. Erstellen Sie in jedem Arbeitsbereich eine Visualisierung mit den Daten, die Sie in der neuen Standardvisualisierung anzeigen möchten.

   Wenn Sie beispielsweise möchten, dass die Dimension in einem Balkendiagramm angezeigt wird, erstellen Sie eine Balkendiagrammvisualisierung, die die gewünschte Metrik und Dimension anzeigt.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Assistenten und klicken Sie auf **[!UICONTROL Save]**.
1. Im [!DNL Save] Fenster, klicken Sie auf ![](assets/btn_folder_up.png), Doppelklick **[!UICONTROL Context]** und anschließend auf **[!UICONTROL Dimension Legend]**.
1. Im [!DNL File Name] -Feld den Dimensionsnamen ein.

   Der Name der [!DNL .1d] -Datei muss exakt mit dem Namen der Dimension übereinstimmen. Zum Beispiel [!DNL Hour.1d].

1. Ändern Sie die Dateierweiterung in &quot;1d&quot;und klicken Sie auf **[!UICONTROL Save]**.

   Die Datei wird im Ordner Benutzer\*Arbeitsprofilname*\Kontext\Dimension-Legende gespeichert.

   Das nächste Mal, wenn Sie in einer [!DNL Dataset Schema Interface], wird die von Ihnen angegebene Visualisierung angezeigt.

1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen:

   1. Im [!DNL Profile Manager]klicken **[!UICONTROL Context]** Klicken Sie auf **[!UICONTROL Dimension Legend]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen des neuen Callout im [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
