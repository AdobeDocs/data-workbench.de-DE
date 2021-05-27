---
description: Neu erstellte Registerkarten zeigen die Unterordner im zugehörigen Ordner standardmäßig als hierarchische Dropdown-Unterverzeichnisse an, nicht als Unterregisterkarten.
title: Anzeigen von Unterordnern als Unterregisterkarten
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Anzeigen von Unterordnern als Unterregisterkarten{#display-subfolders-as-subtabs}

Neu erstellte Registerkarten zeigen die Unterordner im zugehörigen Ordner standardmäßig als hierarchische Dropdown-Unterverzeichnisse an, nicht als Unterregisterkarten.

Sie können Unterordner als Unterregisterkarten anzeigen (wie im folgenden Beispiel gezeigt), indem Sie eine [!DNL empty folder.useTabs]-Datei im Ordner *Arbeitsprofilname*\Workspaces\*tab name* im Installationsverzeichnis der Data Workbench platzieren.

Das folgende Beispiel zeigt die Registerkarte [!DNL Custom] mit Dropdown-Unterverzeichnissen.

![](assets/client-sub.png)

Wenn Sie eine [!DNL empty folder.useTabs]-Datei im Ordner &quot;Workspaces\Custom&quot;platzieren, werden alle Unterordner im Ordner &quot;Benutzerdefiniert&quot;in den Unterregisterkarten [!DNL Worktop] angezeigt, wie im folgenden Beispiel gezeigt:

![](assets/client-sub2.png)

**So zeigen Sie Unterordner als Unterregisterkarten in der[!DNL Worktop]**

>[!NOTE]
>
>Jede Ordnerebene muss über eine [!DNL Tab Name.useTabs]-Datei verfügen, damit der Inhalt des Unterordners als Unterregisterkarten anstatt als hierarchische Dropdown-Unterverzeichnisse angezeigt wird.

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Workspaces]** , um den Inhalt anzuzeigen.
1. Klicken Sie in der Spalte *Arbeitsprofilname* mit der rechten Maustaste auf das Häkchen für eine der [!DNL folder.useTabs] Dateien und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste in die Spalte [!DNL User] für den Ordner &quot;Workspaces\*tab name*&quot;und klicken Sie auf **[!UICONTROL Paste]**. Die Unterordner in dieser Registerkarte werden jetzt als Unterregisterkarten angezeigt.
1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für die Datei [!DNL new folder.useTabs] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
