---
description: Schritte zum Bearbeiten eines vorhandenen Datensatzes umfassen Dateien.
title: Bearbeiten vorhandener Datensatzaufnahme-Dateien
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Bearbeiten vorhandener Datensatzaufnahme-Dateien{#editing-existing-dataset-include-files}

{{eol}}

Schritte zum Bearbeiten eines vorhandenen Datensatzes umfassen Dateien.

Sie öffnen eine vorhandene Datensatzaufnahme-Datei mit der [!DNL Profile Manager] in Data Workbench.

Informationen zum Öffnen und Arbeiten mit der [!DNL Profile Manager], siehe *Data Workbench-Benutzerhandbuch*.

1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie die [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** um den Inhalt des Ordners anzuzeigen.

   * So öffnen Sie eine [!DNL Log Processing Dataset Include] Datei, klicken Sie auf **[!UICONTROL Log Processing]** um den Inhalt des Ordners anzuzeigen.

   * So öffnen Sie eine [!DNL Transformation Dataset Include] Datei, klicken Sie auf **[!UICONTROL Transformation]** um den Inhalt des Ordners anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben der gewünschten Datensatzaufnahme-Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.

   Sie können auch eine Datensatzaufnahme-Datei aus einem [!DNL Transformation Dependency Maps]. Informationen zu [!DNL Transformation Dependency Maps], siehe [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei entsprechend. Siehe [Datensatzaufnahme-Dateien zur Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) oder [Datensatzaufnahme-Dateien zur Transformation](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) für Beschreibungen der Parameter.

   Beim Bearbeiten einer Datensatzaufnahme-Datei in einem Data Workbench-Fenster können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+C), Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswahl des Bereichs (Klicken+Ziehen) und Auswahl aller Elemente (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei zu kopieren und einzufügen ( [!DNL .cfg]) in eine andere.

1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme-Datei gehört. Die Neuverarbeitung oder Umformatierung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
