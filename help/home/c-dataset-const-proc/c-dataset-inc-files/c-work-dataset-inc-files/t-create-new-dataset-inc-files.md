---
description: Schritte zum Erstellen eines neuen Datensatzes umfassen die Datei.
solution: Analytics
title: Erstellen von neuen Datasets einschließlich Dateien
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Erstellen von neuen Datasets einschließlich Dateien{#creating-new-dataset-include-files}

Schritte zum Erstellen eines neuen Datensatzes umfassen die Datei.

Sie sollten eine neue Datensatzeinzuschließende Datei erstellen, um die folgenden Aufgaben zur Datensatzkonfiguration auszuführen:

* Angabe neuer Datenfelder, die von der Protokollverarbeitung zur Konvertierung übergeben werden sollen.
* Definieren von Transformationen, die eine der folgenden Aktionen ausführen:

   * Aktualisieren Sie vorhandene Protokollfelder.
   * Erstellen Sie neue Felder, die von der Protokollverarbeitung zur Konvertierung weitergeleitet werden oder die zum Definieren erweiterter Dimensionen verwendet werden.

      Informationen zu den verfügbaren Konvertierungstypen finden Sie unter [Datentransformationen](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Wenn Sie Konvertierungen in einem neuen Datensatz einschließlich Datei definieren, achten Sie darauf, die Reihenfolge der Ein- und Ausgänge zu berücksichtigen. Informationen zur Reihenfolge der Transformationen finden Sie unter [Übereinkommen zum Erstellen von Transformationen](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Erstellen erweiterter Dimensionen. Informationen zu den verfügbaren Dimensionstypen finden Sie unter [Erweiterte Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Öffnen Sie bei der Arbeit mit Ihrem Datenaset-Profil die Datei [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um die vorhandenen Dateneinschlussdateien anzuzeigen.

   * Um die [!DNL Log Processing Dataset Include] Dateien anzuzeigen, klicken Sie auf **[!UICONTROL Log Processing]**.

   * Um die [!DNL Transformation Dataset Include] Dateien anzuzeigen, klicken Sie auf **[!UICONTROL Transformation]**.

1. Erstellen Sie eine neue [!DNL Log Processing] oder [!DNL Transformation Dataset Include] Dateien, indem Sie einen der folgenden Schritte ausführen:

   * Klicken Sie in der [!DNL User] Spalte für den Protokollverarbeitungsordner auf **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Eine Datei mit dem Namen [!DNL New Log Processing.cfg] wird im Verzeichnis angezeigt.

   * Klicken Sie in der [!DNL User] Spalte für das Transformationsverzeichnis auf **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Eine Datei mit dem Namen [!DNL New Transformation.cfg] wird im Verzeichnis angezeigt.

1. Benennen Sie die neue Datei um, indem Sie mit der rechten Maustaste auf das Häkchen in der [!DNL User] Spalte klicken und den neuen Namen im Dateiparameter eingeben.

   ![Schritt-Info](assets/vis_ProfileManager_RenameFile.png)

1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die umbenannte Datei und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei entsprechend. Beschreibungen der verfügbaren Parameter finden Sie unter [Log Processing DataSet Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) oder [Transformation DataSet Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) .
1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört. Die Verarbeitung oder Umgestaltung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

Informationen zum Bearbeiten einer von Ihnen erstellten Datensatzeinschlussdatei finden Sie unter [Bearbeiten vorhandener Datenasets einschließlich Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
