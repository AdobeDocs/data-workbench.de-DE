---
description: Schritte zum Erstellen einer neuen Datensatzaufnahme-Datei.
title: Erstellen neuer Datensatzaufnahme-Dateien
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Erstellen neuer Datensatzaufnahme-Dateien{#creating-new-dataset-include-files}

{{eol}}

Schritte zum Erstellen einer neuen Datensatzaufnahme-Datei.

Sie sollten eine neue Datensatzaufnahme-Datei erstellen, um eine der folgenden Datensatzkonfigurationsaufgaben auszuführen:

* Angabe neuer Datenfelder, die von der Protokollverarbeitung zur Transformation übergeben werden sollen.
* Definieren von Umwandlungen mit einer der folgenden Aufgaben:

   * Vorhandene Protokollfelder aktualisieren.
   * Erstellen Sie neue Felder, die von der Protokollverarbeitung an die Transformation übergeben werden sollen oder die zur Definition erweiterter Dimensionen verwendet werden.

      Informationen zu den verfügbaren Transformationstypen finden Sie unter [Datenumwandlungen](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Wenn Sie Umwandlungen in einem neuen Datensatz mit Include-Dateien definieren, achten Sie darauf, die Reihenfolge der Ein- und Ausgabedaten zu berücksichtigen. Informationen zur Reihenfolge der Umwandlungen finden Sie unter [Konventionen zum Erstellen von Umwandlungen](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Erstellen erweiterter Dimensionen Informationen zu den verfügbaren Dimensionstypen finden Sie unter [Erweiterte Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie die [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um die vorhandenen Datensatzaufnahme-Dateien anzuzeigen.

   * So zeigen Sie die [!DNL Log Processing Dataset Include] Dateien, klicken Sie auf **[!UICONTROL Log Processing]**.

   * So zeigen Sie die [!DNL Transformation Dataset Include] Dateien, klicken Sie auf **[!UICONTROL Transformation]**.

1. Erstellen Sie eine neue [!DNL Log Processing] oder [!DNL Transformation Dataset Include] -Dateien, indem Sie einen der folgenden Schritte ausführen:

   * Im [!DNL User] Spalte für den Protokollverarbeitungsordner klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Eine Datei mit dem Namen [!DNL New Log Processing.cfg] im Verzeichnis angezeigt.

   * Im [!DNL User] Spalte für das Verzeichnis &quot;Umwandlungen&quot;auf **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Eine Datei mit dem Namen [!DNL New Transformation.cfg] im Verzeichnis angezeigt.

1. Benennen Sie die neue Datei um, indem Sie mit der rechten Maustaste auf das entsprechende Kontrollkästchen im [!DNL User] und geben Sie den neuen Namen in den Parameter Datei ein.

   ![Schritt-Info](assets/vis_ProfileManager_RenameFile.png)

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die umbenannte Datei und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei entsprechend. Siehe [Datensatzaufnahme-Dateien zur Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) oder [Datensatzaufnahme-Dateien zur Transformation](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) für Beschreibungen der verfügbaren Parameter.
1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme-Datei gehört. Die Neuverarbeitung oder Umformatierung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

Informationen zum Bearbeiten einer von Ihnen erstellten Datensatzaufnahme-Datei finden Sie unter [Bearbeiten vorhandener Datensatzaufnahme-Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
