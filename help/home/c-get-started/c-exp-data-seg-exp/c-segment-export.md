---
description: Erstellen Sie benutzerdefinierte Spalten-Exportkopfzeilen für Ihre Segmentexportdateien, um leicht verständliche Beschreibungen für exportierte Segmente hinzuzufügen. Mit dieser Exportfunktion können Sie auch als TSV- und CSV-Dateien ausgeben.
title: Segmentexport mit benutzerdefinierten Überschriften
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segmentexport mit benutzerdefinierten Überschriften{#segment-export-with-custom-headers}

Erstellen Sie benutzerdefinierte Spalten-Exportkopfzeilen für Ihre Segmentexportdateien, um leicht verständliche Beschreibungen für exportierte Segmente hinzuzufügen. Mit dieser Exportfunktion können Sie auch als TSV- und CSV-Dateien ausgeben.

Der Segmentexport wurde um eine neue Funktion erweitert, einschließlich der Möglichkeit, mit einem Header oder in CSV- und TSV-Formaten zu exportieren.

Sie können Spaltenüberschriften für Ihre Exportdateien erstellen.

## Erstellen eines neuen Segmentexports {#section-cffff55855f8467ea468b71393ab7676}

1. Öffnen Sie eine Arbeitsfläche und klicken Sie mit der rechten Maustaste **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Add Level > Extended]** > Element auswählen.
1. Klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie im Menü eine Dimension **[!UICONTROL Add Attribute.]** auswählen.

1. Klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie eine Metrik aus dem Menü **[!UICONTROL Add Metric.]** auswählen.

1. Klicken Sie mit der rechten Maustaste auf den Titel und wählen Sie **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** füllt den Spaltennamen automatisch mit dem Namen der Metrik. **[!UICONTROL New Segment Export]** müssen Sie einen benutzerdefinierten Namen festlegen. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >Das Feld &quot;Spaltenname&quot;darf nicht leer gelassen werden oder die Kopfzeile ist nicht vorhanden.

1. Klicken Sie mit der rechten Maustaste und geben Sie dem Segment einen Namen und klicken Sie dann auf **[!UICONTROL Save Export File]**.

   Daraufhin wird ein Exportfenster geöffnet.

1. Klicken Sie mit der rechten Maustaste auf den Exportnamen und klicken Sie auf **[!UICONTROL Speichern unter<export filename>]**.

   ![](assets/segment_export_headers_7.png)

1. Klicken Sie mit der rechten Maustaste [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Suchen Sie die soeben erstellte Exportdatei und speichern Sie sie in einem vorhandenen Profil.

   ![](assets/segment_export_headers_8.png)

