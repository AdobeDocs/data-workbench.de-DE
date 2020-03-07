---
description: Schritte zum Bearbeiten des vorhandenen Datensatzes umfassen Dateien.
solution: Analytics
title: Bearbeiten vorhandener Datenbestände einschließlich Dateien
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Bearbeiten vorhandener Datenbestände einschließlich Dateien{#editing-existing-dataset-include-files}

Schritte zum Bearbeiten des vorhandenen Datensatzes umfassen Dateien.

Sie öffnen eine vorhandene Dateneinschlussdatei mit dem [!DNL Profile Manager] in der Datenbasis.

Weitere Informationen zum Öffnen und Arbeiten mit [!DNL Profile Manager]Data Workbench finden Sie im *Data Workbench-Benutzerhandbuch*.

1. Öffnen Sie bei der Arbeit mit Ihrem DataSet-Profil die Datei [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um den Inhalt des Ordners anzuzeigen.

   * Um eine [!DNL Log Processing Dataset Include] Datei zu öffnen, klicken Sie auf **[!UICONTROL Log Processing]** , um den Inhalt des Ordners anzuzeigen.

   * Um eine [!DNL Transformation Dataset Include] Datei zu öffnen, klicken Sie auf **[!UICONTROL Transformation]** , um den Inhalt des Ordners anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben der gewünschten Datensatzdatei einschließen und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Konfigurationsfenster wird angezeigt.

   Sie können auch eine Datensatzeinschlussdatei aus einem [!DNL Transformation Dependency Maps]öffnen. Weitere Informationen [!DNL Transformation Dependency Maps]finden Sie unter [Neuverarbeitung und Konvertierung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Bearbeiten Sie die Parameter in der Konfigurationsdatei entsprechend. Beschreibungen der Parameter finden Sie unter [Log Processing DataSet Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) oder [Transformation DataSet Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) .

   Beim Bearbeiten einer DataSet-Include-Datei in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x), Kopieren (Strg+c), Einfügen (Strg+v), Rückgängigmachen (Strg+Z), Wiederholen (Strg+Umschalt+Z), Abschnitt auswählen (Klicken+Ziehen) und alle auswählen (Strg+a). Darüber hinaus können Sie mithilfe der Tastaturbefehle Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere kopieren und einfügen.

1. Um Ihre Änderungen zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört. Die Verarbeitung oder Umgestaltung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

