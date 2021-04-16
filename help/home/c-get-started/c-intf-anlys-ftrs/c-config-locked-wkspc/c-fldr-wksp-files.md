---
description: Im Workspaces-Ordner des Installationsordners der Data Workbench gibt eine Datei "folder.lock"an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während eine Datei "workspace name.lock"angibt, ob eine bestimmte Arbeitsfläche gesperrt ist.
title: Dateien „folder.lock“ und „workspace.lock“
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Dateien „folder.lock“ und „workspace.lock“{#folder-lock-and-workspace-lock-files}

Im Workspaces-Ordner des Installationsordners der Data Workbench gibt eine Datei &quot;folder.lock&quot;an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während eine Datei &quot;workspace name.lock&quot;angibt, ob eine bestimmte Arbeitsfläche gesperrt ist.

Beim Sperren ganzer Ordner können Sie diese auf der Ebene des Workspaces-Ordners oder auf der Ebene des Unterordners (Registerkarte) sperren. Sie können auch alle Ordner sperren oder entsperren (auf der Ebene des Workspaces-Ordners) und dann die Ausnahmen für bestimmte Unterordner (mit [!DNL folder.lock]-Dateien) oder bestimmte Arbeitsbereiche (mit *Workspace-Namen*.lock-Dateien) angeben.

Im folgenden Beispiel von [!DNL Profile Manager] werden drei Elemente hervorgehoben:

* Eine [!DNL folder.lock]-Datei für den Hauptordner &quot;Workspaces&quot;
* Eine [!DNL Monthly Numbers.lock]-Datei für die Arbeitsbereichdatei [!DNL Monthly Numbers.vw]

* Eine [!DNL folder.lock]-Datei für den Unterordner &quot;Workspaces\Custom&quot;

![](assets/wsp_Locking_lockFiles.png)

In diesem Beispiel ist die [!DNL Workspaces folder.lock]-Datei auf &quot;locked&quot;gesetzt, wodurch alle Arbeitsbereiche in dieser Instanz der Data Workbench gesperrt werden. Die Datei &quot;Arbeitsbereiche\Benutzerdefinierter Unterordner [!DNL folder.lock]&quot;ist auf entsperrt, wodurch alle Arbeitsbereiche auf der Registerkarte [!DNL Custom] entsperrt werden. Schließlich ist die Datei [!DNL Monthly Numbers.lock] gesperrt, wodurch der Arbeitsbereich &quot;Monatliche Zahlen&quot;gesperrt wird.

## Erstellen von .lock-Dateien {#section-c4f78b4b43c347368a376904effb41d2}

Sie können eine [!DNL new folder.lock]-Datei mit der Option [!DNL Create menu] in [!DNL Profile Manager] oder [!DNL Workspaces Manager] erstellen. Sie können auch eine Datei [!DNL folder.lock] oder *Workspace name*.lock erstellen, indem Sie eine vorhandene [!DNL .lock]-Datei kopieren und in den entsprechenden Ordner einfügen, den Namen der Datei ändern (nur für *Workspace-Namen*.lock-Dateien) und die Einstellung in der Datei ggf. ändern.

**So erstellen Sie eine neue Datei &quot;folder.lock&quot;**

1. Öffnen Sie in der Data Workbench das [!DNL Workspaces Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und auf **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]** klicken.
1. Klicken Sie auf den Ordner, für den Sie eine [!DNL folder.lock]-Datei erstellen möchten.
1. Klicken Sie in der Spalte [!DNL User] für diesen Ordner mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Eine [!DNL new folder.lock]-Datei wird angezeigt. [!DNL New folder.lock] -Dateien standardmäßig  [] entsperrt.
1. (Optional) Wenn Sie die Einstellung in der Datei ändern müssen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL folder.lock] wird geöffnet.

   1. Ändern Sie die Einstellung in [locked].
   1. Speichern und schließen Sie die Datei.

1. Um diese Einstellung für alle Benutzer mit demselben funktionierenden Profil festzulegen, klicken Sie mit der rechten Maustaste auf das Häkchen der Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Die Arbeitsbereiche in diesem Ordner sind nun gemäß der Einstellung in der neuen Datei gesperrt oder entsperrt.

**So erstellen Sie eine .lock-Datei aus einer vorhandenen Datei**

1. Klicken Sie in der [!DNL Profile Manager]- oder [!DNL Workspaces Manager]-Datei mit der rechten Maustaste auf das Häkchen für eine vorhandene [!DNL .lock]-Datei und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie in der Spalte [!DNL User] für den Ordner, in den Sie die Datei [!DNL .lock] einfügen möchten, mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Paste]**.
1. Wenn diese Datei zum Sperren einer einzelnen Arbeitsfläche verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .lock] in der Spalte [!DNL User] und ändern Sie ihren Namen im Feld [!DNL File], damit er mit dem Namen der Arbeitsfläche übereinstimmt, die Sie sperren möchten.

   Um beispielsweise den Arbeitsbereich [!DNL Monthly Numbers.vw] zu sperren, würden Sie der Datei den Namen &quot;[!DNL Monthly Numbers.lock]&quot;geben.Wenn diese Datei zum Sperren einer einzelnen Arbeitsfläche verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL .lock] in der Spalte [!DNL User] und ändern Sie ihren Namen im Feld [!DNL File], damit er mit dem Namen der Arbeitsfläche übereinstimmt, die Sie sperren möchten. Um beispielsweise den Arbeitsbereich [!DNL Monthly Numbers.vw] zu sperren, würden Sie der Datei den Namen &quot;[!DNL Monthly Numbers.lock]&quot;geben.

1. So ändern Sie die Einstellung in der Datei:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL .lock] wird geöffnet.

   1. Ändern Sie die Einstellung in [locked] oder [unlocked].
   1. Speichern und schließen Sie die Datei.

1. Um diese Einstellung für alle Benutzer mit demselben funktionierenden Profil festzulegen, klicken Sie mit der rechten Maustaste auf das Häkchen der Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Die ausgewählten Arbeitsbereiche sind nun gemäß der Einstellung in der neuen Datei gesperrt oder entsperrt.
