---
description: Im Ordner "Workspaces"des Installationsordners von Data Workbench gibt eine Datei "folder.lock"an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während eine Datei "workspace name.lock"angibt, ob eine bestimmte Arbeitsfläche gesperrt ist.
solution: Analytics
title: Folder.lock- und workspace.lock-Dateien
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Folder.lock- und workspace.lock-Dateien{#folder-lock-and-workspace-lock-files}

Im Ordner &quot;Workspaces&quot;des Installationsordners von Data Workbench gibt eine Datei &quot;folder.lock&quot;an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während eine Datei &quot;workspace name.lock&quot;angibt, ob eine bestimmte Arbeitsfläche gesperrt ist.

Beim Sperren ganzer Ordner können Sie diese auf der Ebene des Workspaces-Ordners oder auf der Ebene des Unterordners (Registerkarte) sperren. Sie können auch alle Ordner sperren oder entsperren (auf der Ebene des Workspaces-Ordners) und dann die Ausnahmen für bestimmte Unterordner (mithilfe von [!DNL folder.lock] Dateien) oder bestimmte Arbeitsbereiche (mithilfe der Dateien &quot; *Workspace name*.lock&quot;) angeben.

Im folgenden Beispiel werden drei Elemente [!DNL Profile Manager] hervorgehoben:

* Eine [!DNL folder.lock] Datei für den Hauptordner &quot;Workspaces&quot;
* Eine [!DNL Monthly Numbers.lock] Datei für die [!DNL Monthly Numbers.vw] Workspace-Datei

* Eine [!DNL folder.lock] Datei für den Unterordner &quot;Workspaces\Custom&quot;

![](assets/wsp_Locking_lockFiles.png)

In diesem Beispiel ist die [!DNL Workspaces folder.lock] Datei auf &quot;gesperrt&quot;eingestellt, wodurch alle Arbeitsbereiche in dieser Instanz von Data Workbench gesperrt werden. Die [!DNL folder.lock] Datei &quot;Arbeitsbereiche\Benutzerdefinierter Unterordner&quot;ist auf entsperrt eingestellt, wodurch alle Arbeitsbereiche auf der [!DNL Custom] Registerkarte entsperrt werden. Schließlich ist die [!DNL Monthly Numbers.lock] Datei auf &quot;gesperrt&quot;eingestellt, wodurch der Arbeitsbereich &quot;Monatliche Zahlen&quot;gesperrt wird.

## Erstellen von .lock-Dateien {#section-c4f78b4b43c347368a376904effb41d2}

Sie können eine [!DNL new folder.lock] Datei mit der [!DNL Create menu] Option im [!DNL Profile Manager] oder im [!DNL Workspaces Manager]. Sie können auch eine Datei mit dem Namen [!DNL folder.lock] .lock *oder* Workspace erstellen, indem Sie eine vorhandene [!DNL .lock] Datei kopieren und in den entsprechenden Ordner einfügen, den Namen der Datei ändern (nur für Dateien mit dem Namen *.lock-* Arbeitsfläche) und die Einstellung in der Datei gegebenenfalls ändern.

**So erstellen Sie eine neue Datei &quot;folder.lock&quot;**

1. Öffnen Sie in Data Workbench das [!DNL Workspaces Manager] durch Rechtsklicken in einem Arbeitsbereich auf **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Klicken Sie auf den Ordner, für den Sie eine [!DNL folder.lock] Datei erstellen möchten.
1. Klicken Sie in der [!DNL User] Spalte für diesen Ordner mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Eine [!DNL new folder.lock] Datei wird angezeigt. [!DNL New folder.lock] Dateien sind standardmäßig auf [entsperrt] eingestellt.
1. (Optional) Wenn Sie die Einstellung in der Datei ändern müssen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL folder.lock] Datei wird geöffnet.

   1. Ändern Sie die Einstellung auf [gesperrt].
   1. Speichern und schließen Sie die Datei.

1. Um diese Einstellung für alle Benutzer mit demselben Arbeitsprofil festzulegen, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Die Arbeitsbereiche in diesem Ordner sind nun gemäß der Einstellung in der neuen Datei gesperrt oder entsperrt.

**So erstellen Sie eine .lock-Datei aus einer vorhandenen Datei**

1. Klicken Sie im [!DNL Profile Manager] oder [!DNL Workspaces Manager]mit der rechten Maustaste auf das Häkchen für eine vorhandene [!DNL .lock] Datei und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie in der [!DNL User] Spalte für den Ordner, in den Sie die [!DNL .lock] Datei einfügen möchten, mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Paste]**.
1. Wenn diese Datei zum Sperren einer einzelnen Arbeitsfläche verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .lock] Datei in der [!DNL User] Spalte und ändern Sie den Namen der Datei im [!DNL File] Feld entsprechend dem Namen der Arbeitsfläche, die Sie sperren möchten.

   Um beispielsweise den [!DNL Monthly Numbers.vw] Arbeitsbereich zu sperren, würden Sie der Datei den Namen &quot; [!DNL Monthly Numbers.lock]&quot;geben.Wenn diese Datei zum Sperren einer einzelnen Arbeitsfläche verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .lock] Datei in der [!DNL User] Spalte und ändern Sie den Namen der Datei im [!DNL File] Feld entsprechend dem Namen der Arbeitsfläche, die Sie sperren möchten. Um beispielsweise den [!DNL Monthly Numbers.vw] Arbeitsbereich zu sperren, würden Sie der Datei den Namen &quot; [!DNL Monthly Numbers.lock]&quot;geben.

1. So ändern Sie die Einstellung in der Datei:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL .lock] Datei wird geöffnet.

   1. Ändern Sie die Einstellung auf [gesperrt] oder [entsperrt].
   1. Speichern und schließen Sie die Datei.

1. Um diese Einstellung für alle Benutzer mit demselben Arbeitsprofil festzulegen, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Die ausgewählten Arbeitsbereiche sind nun gemäß der Einstellung in der neuen Datei gesperrt oder entsperrt.
