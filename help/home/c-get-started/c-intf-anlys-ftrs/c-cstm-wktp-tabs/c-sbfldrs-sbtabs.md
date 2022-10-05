---
description: Neu erstellte Registerkarten zeigen die Unterordner im zugehörigen Ordner standardmäßig als hierarchische Dropdown-Unterverzeichnisse an, nicht als Unterregisterkarten.
title: Anzeigen von Unterordnern als Unterregisterkarten
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Anzeigen von Unterordnern als Unterregisterkarten{#display-subfolders-as-subtabs}

{{eol}}

Neu erstellte Registerkarten zeigen die Unterordner im zugehörigen Ordner standardmäßig als hierarchische Dropdown-Unterverzeichnisse an, nicht als Unterregisterkarten.

Sie können Unterordner als Unterregisterkarten anzeigen (wie im folgenden Beispiel gezeigt), indem Sie eine [!DNL empty folder.useTabs] in der Datei *Name des Arbeitsprofils*\Workspaces\*tab name folder* im Installationsordner der Data Workbench.

Das folgende Beispiel zeigt die [!DNL Custom] Registerkarte mit Dropdown-Unterverzeichnissen.

![](assets/client-sub.png)

Wenn Sie [!DNL empty folder.useTabs] im Ordner &quot;Workspaces\Custom&quot;werden alle Unterordner im Ordner &quot;Custom&quot;im Ordner [!DNL Worktop] wie im folgenden Beispiel gezeigt:

![](assets/client-sub2.png)

**So zeigen Sie Unterordner als Unterregisterkarten in der[!DNL Worktop]**

>[!NOTE]
>
>Jede Ordnerebene muss über eine [!DNL Tab Name.useTabs] -Datei, damit der Inhalt des Unterordners als Unterregisterkarten und nicht als hierarchische Dropdown-Unterverzeichnisse angezeigt wird.

1. Im [!DNL Profile Manager]klicken **[!UICONTROL Workspaces]** , um den Inhalt anzuzeigen.
1. Im *Name des Arbeitsprofils* klicken Sie mit der rechten Maustaste auf das Häkchen eines der [!DNL folder.useTabs] Dateien und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste auf die [!DNL User] Spalte für den Ordner &quot;Workspaces\*tab name*&quot;und klicken Sie auf **[!UICONTROL Paste]**. Die Unterordner in dieser Registerkarte werden jetzt als Unterregisterkarten angezeigt.
1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für die [!DNL new folder.useTabs] in der Datei [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
