---
description: Der Server Files Manager zeigt alle Ordner im Installationsordner des Data Workbench-Servers an, einschließlich Konfigurations- und Suchdateien.
title: Erstellen von Server-Datei-Managern
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Erstellen von Server-Datei-Managern{#create-a-server-files-manager}

Der Server Files Manager zeigt alle Ordner im Installationsordner des Data Workbench-Servers an, einschließlich Konfigurations- und Suchdateien.

Sie können auf einen Teil des [!DNL Server Files Manager] zugreifen, ohne die gesamte Ordnerstruktur durchsuchen zu müssen, oder nur einige der Unterverzeichnisse anzeigen zu müssen, um eine bestimmte Anforderung zu erfüllen. Sie können beispielsweise eine separate [!DNL Server Files Manager] erstellen, die nur die Unterverzeichnisse Zugriffskontrolle und Benutzer anzeigt und Ihnen die Verwaltung Ihrer Benutzer und deren Zugriff ermöglicht.

Jeder von Ihnen erstellte Manager muss über eine [!DNL .vw] -Datei verfügen. Sie können die Datei [!DNL Server Files.vw] als Vorlage verwenden.

Weitere Informationen zu [!DNL Server Files Manager] finden Sie unter [Der Server Files Manager](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**So erstellen Sie einen Server-Datei-Manager**

1. Klicken Sie im Ordner [!DNL Profile Manager] auf das Verzeichnis **[!UICONTROL Menu]** und dann auf das Verzeichnis **[!UICONTROL Admin]** . Die Datei [!DNL Server Files.vw] befindet sich hier.
1. Klicken Sie in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für die Datei [!DNL Server Files.vw] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für die Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL Server Files.vw] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die Datei [!DNL Server Files.vw] wird geöffnet.
1. Um einen Ordner zu entfernen, klicken Sie mit der rechten Maustaste auf den oberen Rand von [!DNL Server Files Manager] und klicken Sie auf **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]***.
1. Um einen Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf den oberen Rand von [!DNL Server Files Manager], klicken Sie auf **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Geben Sie den URI des Ordners in das Feld &quot;URI&quot;ein und klicken Sie auf **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Sie können mehrere Verzeichnisse im URI-Feld angeben. Wenn Sie beispielsweise  [!DNL Profiles\Marketing\] eingeben, enthält der Server-Dateimanager das Unterverzeichnis Marketing, aber kein anderes Unterverzeichnis im Verzeichnis Profile .

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand von [!DNL Server Files Manager] und klicken Sie auf **[!UICONTROL Save]**.
1. Um einen neuen Manager zu erstellen, ändern Sie den Dateinamen im Feld [!DNL File Name] und klicken Sie dann auf **[!UICONTROL Save]**. Um den vorhandenen Manager zu überschreiben, klicken Sie auf **[!UICONTROL Save]**.
1. (Optional) Um die Änderungen für alle Benutzer des Arbeitsprofils verfügbar zu machen, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .vw] in der Spalte [!DNL User].

   Klicken Sie danach auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
