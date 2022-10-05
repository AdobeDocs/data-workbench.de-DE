---
description: Der Server Files Manager zeigt alle Ordner im Installationsordner des Data Workbench-Servers an, einschließlich Konfigurations- und Suchdateien.
title: Erstellen von Server-Datei-Managern
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Erstellen von Server-Datei-Managern{#create-a-server-files-manager}

{{eol}}

Der Server Files Manager zeigt alle Ordner im Installationsordner des Data Workbench-Servers an, einschließlich Konfigurations- und Suchdateien.

Sie können auf einen Teil der [!DNL Server Files Manager] , ohne die gesamte Ordnerstruktur durchlaufen zu müssen, oder nur einige der Unterverzeichnisse anzuzeigen, um eine bestimmte Anforderung zu erfüllen. Sie können beispielsweise eine separate [!DNL Server Files Manager] , in dem nur die Unterverzeichnisse Zugriffskontrolle und Benutzer angezeigt werden, sodass Sie Ihre Benutzer und deren Zugriff verwalten können.

Jeder von Ihnen erstellte Manager muss über eine [!DNL .vw] -Datei. Sie können die [!DNL Server Files.vw] als Vorlage zu verwenden.

Weitere Informationen zum [!DNL Server Files Manager], siehe [Der Server Files Manager](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**So erstellen Sie einen Server-Datei-Manager**

1. Im [!DNL Profile Manager], klicken Sie auf die **[!UICONTROL Menu]** Verzeichnis, dann die **[!UICONTROL Admin]** Verzeichnis. Die [!DNL Server Files.vw] -Datei finden Sie hier.
1. Im *Profilname* klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL Server Files.vw] Datei und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für die Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL Server Files.vw] in der Datei [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL Server Files.vw] Datei geöffnet.
1. Um einen Ordner zu entfernen, klicken Sie mit der rechten Maustaste auf den oberen Rand des [!DNL Server Files Manager] und klicken Sie auf **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Um ein Verzeichnis hinzuzufügen, klicken Sie mit der rechten Maustaste auf den oberen Rand des [!DNL Server Files Manager]klicken **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Geben Sie den URI des Ordners in das Feld &quot;URI&quot;ein und klicken Sie auf **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Sie können mehrere Verzeichnisse im URI-Feld angeben. Wenn Sie beispielsweise [!DNL Profiles\Marketing\]enthält der Server-Datei-Manager das Unterverzeichnis Marketing , jedoch kein anderes Unterverzeichnis im Verzeichnis Profile .

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des [!DNL Server Files Manager] und klicken Sie auf **[!UICONTROL Save]**.
1. Um einen neuen Manager zu erstellen, ändern Sie den Dateinamen im [!DNL File Name] und klicken Sie auf **[!UICONTROL Save]**. Um den vorhandenen Manager zu überschreiben, klicken Sie auf **[!UICONTROL Save]**.
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .vw] in der Datei [!DNL User] Spalte.

   Klicken Sie danach auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
