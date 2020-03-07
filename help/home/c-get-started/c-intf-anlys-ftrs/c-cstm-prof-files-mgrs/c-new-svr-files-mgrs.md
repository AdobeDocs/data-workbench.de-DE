---
description: Der Server Files Manager zeigt alle Ordner im Installationsordner des Data Workbench-Servers an, einschließlich Konfigurations- und Nachschlagedateien.
solution: Analytics
title: Server Files Manager erstellen
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server Files Manager erstellen{#create-a-server-files-manager}

Der Server Files Manager zeigt alle Ordner im Installationsordner des Data Workbench-Servers an, einschließlich Konfigurations- und Nachschlagedateien.

Möglicherweise möchten Sie auf einen Teil des Verzeichnisses zugreifen, [!DNL Server Files Manager] ohne die gesamte Ordnerstruktur zu durchlaufen oder nur einige der Unterordner anzuzeigen, um eine bestimmte Anforderung zu erfüllen. Sie können beispielsweise eine separate Datei erstellen, [!DNL Server Files Manager] die nur die Unterordner Zugriffssteuerung und Benutzer anzeigt, sodass Sie Ihre Benutzer und deren Zugriff verwalten können.

Jeder Manager, den Sie erstellen, muss über eine [!DNL .vw] Datei verfügen. Sie können die [!DNL Server Files.vw] Datei als Vorlage verwenden.

Weitere Informationen zum [!DNL Server Files Manager]Server finden Sie unter [Server Files Manager](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**So erstellen Sie einen Server Files Manager**

1. Klicken Sie im [!DNL Profile Manager]Ordner auf das **[!UICONTROL Menu]** Verzeichnis und dann auf das **[!UICONTROL Admin]** Verzeichnis. Die [!DNL Server Files.vw] Datei befindet sich hier.
1. Klicken Sie in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für die [!DNL Server Files.vw] Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für die Datei wird in der [!DNL User] Spalte angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL Server Files.vw] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL Server Files.vw] Datei wird geöffnet.
1. Klicken Sie zum Entfernen eines Ordners mit der rechten Maustaste auf den oberen Rand des Ordners [!DNL Server Files Manager] und klicken Sie auf **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Klicken Sie zum Hinzufügen eines Ordners mit der rechten Maustaste auf den oberen Rand des Ordners [!DNL Server Files Manager]und klicken Sie auf **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Geben Sie den URI des Ordners in das Feld &quot;URI&quot;ein und klicken Sie auf **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Sie können mehrere Ordner im Feld &quot;URI&quot;angeben. Wenn Sie beispielsweise [!DNL Profiles\Marketing\] eingeben, enthält der Server-Dateimanager den Unterordner &quot;Marketing&quot;, jedoch keinen anderen Unterordner im Ordner &quot;Profile&quot;.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Formulars [!DNL Server Files Manager] und klicken Sie auf **[!UICONTROL Save]**.
1. Um einen neuen Manager zu erstellen, ändern Sie den Dateinamen im [!DNL File Name] Feld und klicken Sie dann auf **[!UICONTROL Save]**. Um den vorhandenen Manager zu überschreiben, klicken Sie auf **[!UICONTROL Save]**.
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] Datei in der [!DNL User] Spalte.

   Klicken Sie danach auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

