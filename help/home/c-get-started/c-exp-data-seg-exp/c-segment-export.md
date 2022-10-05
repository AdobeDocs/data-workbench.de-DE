---
description: Erstellen Sie benutzerdefinierte Spaltenexport-Header für Ihre Segmentexportdateien, um leicht verständliche Beschreibungen für exportierte Segmente hinzuzufügen. Diese Exportfunktion ermöglicht auch die Ausgabe als TSV- und CSV-Dateien.
title: Segmentexport mit benutzerdefinierten Kopfzeilen
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
exl-id: 1d27f926-35e1-4886-b7a6-702d9947dabb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Segmentexport mit benutzerdefinierten Kopfzeilen{#segment-export-with-custom-headers}

{{eol}}

Erstellen Sie benutzerdefinierte Spaltenexport-Header für Ihre Segmentexportdateien, um leicht verständliche Beschreibungen für exportierte Segmente hinzuzufügen. Diese Exportfunktion ermöglicht auch die Ausgabe als TSV- und CSV-Dateien.

Dem Segmentexport wurden neue Funktionen hinzugefügt, einschließlich der Möglichkeit, mit einem Header zu exportieren, oder in CSV- und TSV-Formaten.

Sie können Spaltenüberschriften für Ihre Exportdateien erstellen.

## Erstellen eines neuen Segmentexports {#section-cffff55855f8467ea468b71393ab7676}

1. Öffnen Sie einen Arbeitsbereich und klicken Sie mit der rechten Maustaste **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Add Level > Extended]** > Wählen Sie ein Element aus.
1. Klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie **[!UICONTROL Add Attribute.]** Wählen Sie eine Dimension aus dem Menü aus.

1. Klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie **[!UICONTROL Add Metric.]** Wählen Sie eine Metrik aus dem Menü aus.

1. Klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** füllt automatisch den Spaltennamen mit dem Namen der Metrik. **[!UICONTROL New Segment Export]** erfordert, dass Sie einen benutzerdefinierten Namen festlegen. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >Das Feld Spaltenname kann nicht leer gelassen werden oder die Kopfzeile ist nicht vorhanden.

1. Klicken Sie mit der rechten Maustaste und benennen Sie das Segment und klicken Sie dann auf **[!UICONTROL Save Export File]**.

   Daraufhin wird ein Exportfenster geöffnet.

1. Klicken Sie mit der rechten Maustaste auf den Exportnamen und klicken Sie auf **Speichern unter`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Rechtsklick [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Suchen Sie die soeben erstellte Exportdatei und speichern Sie sie in einem vorhandenen Profil.

   ![](assets/segment_export_headers_8.png)
