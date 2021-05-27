---
description: Im Ordner "Workspaces"des Installationsordners Ihrer Data Workbench gibt die Datei "folder.lock"an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während die Datei "name.lock"im Arbeitsbereich angibt, ob ein bestimmter Arbeitsbereich gesperrt ist.
title: Dateien „folder.lock“ und „workspace.lock“
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Dateien „folder.lock“ und „workspace.lock“{#folder-lock-and-workspace-lock-files}

Im Ordner &quot;Workspaces&quot;des Installationsordners Ihrer Data Workbench gibt die Datei &quot;folder.lock&quot;an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während die Datei &quot;name.lock&quot;im Arbeitsbereich angibt, ob ein bestimmter Arbeitsbereich gesperrt ist.

Beim Sperren ganzer Ordner können Sie diese auf der Ordnerebene &quot;Arbeitsbereiche&quot;oder auf der Ebene des Unterordners (Registerkarte) sperren. Sie können auch alle Ordner sperren oder entsperren (auf der Ordnerebene von Workspaces) und dann die Ausnahmen für bestimmte Unterordner (mithilfe von [!DNL folder.lock]-Dateien) oder bestimmte Arbeitsbereiche (mithilfe von *Workspace name*.lock-Dateien) festlegen.

Im folgenden Beispiel von [!DNL Profile Manager] werden drei Elemente hervorgehoben:

* Datei [!DNL folder.lock] für den Ordner &quot;Workspaces&quot;
* Eine [!DNL Monthly Numbers.lock]-Datei für die Arbeitsbereichsdatei [!DNL Monthly Numbers.vw]

* Datei [!DNL folder.lock] für den Unterordner Workspaces\Benutzerdefiniert

![](assets/wsp_Locking_lockFiles.png)

In diesem Beispiel ist die Datei [!DNL Workspaces folder.lock] auf &quot;locked&quot;gesetzt, wodurch alle Arbeitsbereiche in dieser Instanz der Data Workbench gesperrt werden. Die Datei &quot;Workspaces\Benutzerdefinierter Unterordner [!DNL folder.lock]&quot;ist auf &quot;entsperrt&quot;gesetzt, wodurch alle Arbeitsbereiche auf der Registerkarte [!DNL Custom] entsperrt werden. Schließlich ist die Datei [!DNL Monthly Numbers.lock] gesperrt, wodurch der Arbeitsbereich &quot;Monatliche Zahlen&quot;gesperrt wird.

## Erstellen von .lock-Dateien {#section-c4f78b4b43c347368a376904effb41d2}

Sie können eine [!DNL new folder.lock]-Datei mit der [!DNL Create menu]-Option in [!DNL Profile Manager] oder [!DNL Workspaces Manager] erstellen. Sie können auch eine Datei [!DNL folder.lock] oder *Workspace name*.lock erstellen, indem Sie eine vorhandene [!DNL .lock]-Datei kopieren und in den entsprechenden Ordner einfügen, den Namen der Datei ändern (nur für *Workspace-Namen*.lock-Dateien) und die Einstellung in der Datei ggf. ändern.

**So erstellen Sie eine neue Datei &quot;folder.lock&quot;**

1. Öffnen Sie in Data Workbench das [!DNL Workspaces Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]** auswählen.
1. Klicken Sie auf den Ordner, für den Sie eine [!DNL folder.lock]-Datei erstellen möchten.
1. Klicken Sie in der Spalte [!DNL User] für diesen Ordner mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Eine [!DNL new folder.lock]-Datei wird angezeigt. [!DNL New folder.lock] -Dateien standardmäßig auf  [] entsperrt.
1. (Optional) Wenn Sie die Einstellung in der Datei ändern müssen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL folder.lock] wird geöffnet.

   1. Ändern Sie die Einstellung in [locked].
   1. Speichern und schließen Sie die Datei.

1. Um dies zur Einstellung für alle Benutzer zu machen, die mit demselben Arbeitsprofil arbeiten, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Die Arbeitsbereiche in diesem Ordner sind nun entsprechend der Einstellung in der neuen Datei gesperrt oder entsperrt.

**So erstellen Sie eine .lock-Datei aus einer vorhandenen Datei**

1. Klicken Sie in [!DNL Profile Manager] oder [!DNL Workspaces Manager] mit der rechten Maustaste auf das Häkchen für eine vorhandene [!DNL .lock]-Datei und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie in der Spalte [!DNL User] des Ordners, in den Sie die Datei [!DNL .lock] einfügen möchten, mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Paste]**.
1. Wenn diese Datei zum Sperren eines einzelnen Arbeitsbereichs verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .lock] in der Spalte [!DNL User] und ändern Sie den Namen im Feld [!DNL File], um ihn an den Namen des Arbeitsbereichs anzupassen, den Sie sperren möchten.

   Um beispielsweise den Arbeitsbereich [!DNL Monthly Numbers.vw] zu sperren, würden Sie die Datei &quot;[!DNL Monthly Numbers.lock]&quot;nennen.Wenn diese Datei zum Sperren eines einzelnen Arbeitsbereichs verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .lock] in der Spalte [!DNL User] und ändern Sie den Namen im Feld [!DNL File], um ihn an den Namen des Arbeitsbereichs anzupassen, den Sie sperren möchten. Um beispielsweise den Arbeitsbereich [!DNL Monthly Numbers.vw] zu sperren, würden Sie die Datei &quot;[!DNL Monthly Numbers.lock]&quot;nennen.

1. So ändern Sie die Einstellung in der Datei:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL .lock] wird geöffnet.

   1. Ändern Sie die Einstellung in [locked] oder [unlocked].
   1. Speichern und schließen Sie die Datei.

1. Um dies zur Einstellung für alle Benutzer zu machen, die mit demselben Arbeitsprofil arbeiten, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Die ausgewählten Arbeitsbereiche sind nun entsprechend der Einstellung in der neuen Datei gesperrt oder entsperrt.
