---
description: Neu erstellte Registerkarten zeigen die Unterordner im zugehörigen Ordner standardmäßig als hierarchische Dropdown-Unterordner an und nicht als Unterregisterkarten.
solution: Analytics
title: Unterordner als Unterregisterkarten anzeigen
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Unterordner als Unterregisterkarten anzeigen{#display-subfolders-as-subtabs}

Neu erstellte Registerkarten zeigen die Unterordner im zugehörigen Ordner standardmäßig als hierarchische Dropdown-Unterordner an und nicht als Unterregisterkarten.

Sie können Unterordner als Unterregisterkarten anzeigen (wie im folgenden Beispiel gezeigt), indem Sie eine [!DNL empty folder.useTabs] Datei im Ordner mit dem *Profilnamen*\Workspaces\*tab name* im Installationsordner von Data Workbench ablegen.

Das folgende Beispiel zeigt die [!DNL Custom] Registerkarte mit Dropdown-Unterordnern.

![](assets/client-sub.png)

Wenn Sie eine [!DNL empty folder.useTabs] Datei im Ordner &quot;Workspaces\Custom&quot;ablegen, werden alle Unterordner im Ordner &quot;Custom&quot;auf den Unterregisterkarten [!DNL Worktop] als Unterregisterkarten angezeigt, wie im folgenden Beispiel gezeigt:

![](assets/client-sub2.png)

**So zeigen Sie Unterordner als Unterregisterkarten im[!DNL Worktop]**

>[!NOTE]
>
>Jede Ordnerebene muss über eine [!DNL Tab Name.useTabs] Datei verfügen, damit der Inhalt des Unterordners als Unterregisterkarten anstatt als hierarchische Dropdown-Unterordner angezeigt wird.

1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Workspaces]** , um den Inhalt anzuzeigen.
1. Klicken Sie in der Spalte *Arbeitsprofilname* mit der rechten Maustaste auf das Häkchen für eine der [!DNL folder.useTabs] Dateien und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste in die [!DNL User] Spalte für den Ordner Workspaces\*tab name* und klicken Sie auf **[!UICONTROL Paste]**. Die Unterordner in dieser Registerkarte werden jetzt als Unterregisterkarten angezeigt.
1. (Optional) Um diese Änderung allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für die [!DNL new folder.useTabs] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

