---
description: Schritte zum Bearbeiten eines vorhandenen Datensatzes umfassen Dateien.
title: Bearbeiten vorhandener Datensatzaufnahme-Dateien
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Bearbeiten vorhandener Datensatzaufnahme-Dateien{#editing-existing-dataset-include-files}

Schritte zum Bearbeiten eines vorhandenen Datensatzes umfassen Dateien.

Sie öffnen einen vorhandenen Datensatz mit der Include-Datei [!DNL Profile Manager] in Data Workbench.

Informationen zum Öffnen und Verwenden von [!DNL Profile Manager] finden Sie im *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie bei der Arbeit mit Ihrem Datensatzprofil [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um den Inhalt des Ordners anzuzeigen.

   * Um eine [!DNL Log Processing Dataset Include]-Datei zu öffnen, klicken Sie auf **[!UICONTROL Log Processing]**, um den Inhalt des Ordners anzuzeigen.

   * Um eine [!DNL Transformation Dataset Include]-Datei zu öffnen, klicken Sie auf **[!UICONTROL Transformation]**, um den Inhalt des Ordners anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben der gewünschten Datensatzaufnahme-Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.

   Sie können auch eine Datensatzaufnahme-Datei aus einem [!DNL Transformation Dependency Maps] öffnen. Weitere Informationen zu [!DNL Transformation Dependency Maps] finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei entsprechend. Beschreibungen der Parameter finden Sie unter [Datensatzaufnahme-Dateien für die Protokollverarbeitung](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) oder [Datensatzaufnahme-Dateien für Umwandlungen](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) .

   Beim Bearbeiten einer Datensatzaufnahme-Datei in einem Data Workbench-Fenster können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+C), Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswahl des Bereichs (Klicken+Ziehen) und Auswahl aller Elemente (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere einzufügen.

1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört. Die Neuverarbeitung oder Umformatierung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
