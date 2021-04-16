---
description: Schritte zum Bearbeiten des vorhandenen Datensatzes umfassen Dateien.
title: Bearbeiten vorhandener Datensatzaufnahme-Dateien
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Bearbeiten vorhandener Datensatzaufnahme-Dateien{#editing-existing-dataset-include-files}

Schritte zum Bearbeiten des vorhandenen Datensatzes umfassen Dateien.

Sie öffnen eine vorhandene Dateneinschlussdatei mit dem [!DNL Profile Manager] in der Datenbasis.

Informationen zum Öffnen und Arbeiten mit [!DNL Profile Manager] finden Sie im *Data Workbench Benutzerhandbuch*.

1. Öffnen Sie beim Arbeiten im DataSet-Profil das [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]**, um den Ordnerinhalt anzuzeigen.

   * Um eine [!DNL Log Processing Dataset Include]-Datei zu öffnen, klicken Sie auf **[!UICONTROL Log Processing]**, um den Inhalt des Ordners anzuzeigen.

   * Um eine [!DNL Transformation Dataset Include]-Datei zu öffnen, klicken Sie auf **[!UICONTROL Transformation]**, um den Inhalt des Ordners anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben der gewünschten Datensatzeinschluss-Datei und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.

   Sie können auch eine Datensatzeinschlussdatei aus einem [!DNL Transformation Dependency Maps] öffnen. Weitere Informationen zu [!DNL Transformation Dependency Maps] finden Sie unter [Wiederaufbereitung und Umgestaltung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei entsprechend. Beschreibungen der Parameter finden Sie unter [Datensatz zur Protokollverarbeitung: Dateien](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) oder [Transformationsdatensatz Dateien einschließen](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

   Beim Bearbeiten einer DataSet-Include-Datei in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x), Kopieren (Strg+c), Einfügen (Strg+v), Rückgängigmachen (Strg+Z), Wiederholen (Strg+Umschalt+Z), Abschnitt auswählen (Klicken+Ziehen) und alle auswählen (Strg+a). Darüber hinaus können Sie mithilfe der Tastaturbefehle Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere kopieren und einfügen.

1. Klicken Sie zum Speichern der Änderungen mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzdatei gehört. Die Verarbeitung oder Umgestaltung der Daten beginnt nach der Synchronisierung des DataSet-Profils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.
