---
description: Im Ordner "Workspaces"des Installationsordners Ihrer Data Workbench gibt die Datei "folder.lock"an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während die Datei "name.lock"im Arbeitsbereich angibt, ob ein bestimmter Arbeitsbereich gesperrt ist.
title: Dateien „folder.lock“ und „workspace.lock“
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Dateien „folder.lock“ und „workspace.lock“{#folder-lock-and-workspace-lock-files}

{{eol}}

Im Ordner &quot;Workspaces&quot;des Installationsordners Ihrer Data Workbench gibt die Datei &quot;folder.lock&quot;an, ob die Arbeitsbereiche in diesem Ordner gesperrt sind, während die Datei &quot;name.lock&quot;im Arbeitsbereich angibt, ob ein bestimmter Arbeitsbereich gesperrt ist.

Beim Sperren ganzer Ordner können Sie diese auf der Ordnerebene &quot;Arbeitsbereiche&quot;oder auf der Ebene des Unterordners (Registerkarte) sperren. Sie können auch alle Ordner sperren oder entsperren (auf der Ordnerebene &quot;Arbeitsbereiche&quot;) und dann die Ausnahmen für bestimmte Unterordner angeben (mithilfe von [!DNL folder.lock] Dateien oder bestimmte Arbeitsbereiche (mithilfe von *Arbeitsbereichname*.lock-Dateien).

Das folgende Beispiel zeigt die [!DNL Profile Manager] hebt drei Elemente hervor:

* A [!DNL folder.lock] Datei für den Hauptordner Arbeitsbereiche
* A [!DNL Monthly Numbers.lock] -Datei für [!DNL Monthly Numbers.vw] Arbeitsbereichsdatei

* A [!DNL folder.lock] Datei für den Unterordner Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

In diesem Beispiel wird die [!DNL Workspaces folder.lock] -Datei auf gesperrt gesetzt ist, wodurch alle Arbeitsbereiche in dieser Instanz von Data Workbench gesperrt werden. Der Unterordner Workspaces\Custom [!DNL folder.lock] auf entsperrt gesetzt ist, wodurch alle Arbeitsbereiche auf der [!DNL Custom] Registerkarte. Schließlich wird die [!DNL Monthly Numbers.lock] ist auf &quot;locked&quot;gesetzt, wodurch der Arbeitsbereich &quot;Monatliche Zahlen&quot;gesperrt wird.

## Erstellen von .lock-Dateien {#section-c4f78b4b43c347368a376904effb41d2}

Sie können eine [!DNL new folder.lock] -Datei mithilfe der [!DNL Create menu] in der [!DNL Profile Manager] oder [!DNL Workspaces Manager]. Sie können auch eine [!DNL folder.lock] oder *Arbeitsbereichname*.lock-Datei durch Kopieren und Einfügen einer vorhandenen [!DNL .lock] Datei in den entsprechenden Ordner hinzu und ändern Sie den Namen der Datei (für *Arbeitsbereichname*.lock-Dateien) und ggf. Änderung der Einstellung in der Datei.

**So erstellen Sie eine neue Datei &quot;folder.lock&quot;**

1. Öffnen Sie in Data Workbench die [!DNL Workspaces Manager] durch Rechtsklicken in einem Arbeitsbereich und Klicken auf **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Klicken Sie auf den Ordner, für den Sie eine [!DNL folder.lock] -Datei.
1. Im [!DNL User] für diesen Ordner klicken Sie mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] angezeigt. [!DNL New folder.lock] -Dateien auf [unlocked] Standardmäßig.
1. (Optional) Wenn Sie die Einstellung in der Datei ändern müssen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL folder.lock] Datei geöffnet.

   1. Ändern Sie die Einstellung in [locked].
   1. Speichern und schließen Sie die Datei.

1. Um dies zur Einstellung für alle Benutzer zu machen, die mit demselben Arbeitsprofil arbeiten, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Die Arbeitsbereiche in diesem Ordner sind nun entsprechend der Einstellung in der neuen Datei gesperrt oder entsperrt.

**So erstellen Sie eine .lock-Datei aus einer vorhandenen Datei**

1. Im [!DNL Profile Manager] oder [!DNL Workspaces Manager], klicken Sie mit der rechten Maustaste auf das Häkchen für ein vorhandenes [!DNL .lock] Datei und klicken Sie auf **[!UICONTROL Copy]**.
1. Im [!DNL User] -Spalte für den Ordner, in den Sie die [!DNL .lock] Datei, klicken Sie mit der rechten Maustaste in die Zelle und klicken Sie auf **[!UICONTROL Paste]**.
1. Wenn diese Datei zum Sperren eines einzelnen Arbeitsbereichs verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .lock] in der Datei [!DNL User] und ändern Sie den Namen in [!DNL File] -Feld mit dem Namen des Arbeitsbereichs übereinstimmen, den Sie sperren möchten.

   Um beispielsweise die [!DNL Monthly Numbers.vw] Arbeitsbereich, würden Sie die Datei &quot; [!DNL Monthly Numbers.lock].&quot;Wenn diese Datei zum Sperren eines einzelnen Arbeitsbereichs verwendet wird, klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL .lock] in der Datei [!DNL User] und ändern Sie den Namen in [!DNL File] -Feld mit dem Namen des Arbeitsbereichs übereinstimmen, den Sie sperren möchten. Um beispielsweise die [!DNL Monthly Numbers.vw] Arbeitsbereich, würden Sie die Datei &quot; [!DNL Monthly Numbers.lock].&quot;

1. So ändern Sie die Einstellung in der Datei:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei.
   1. Klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL .lock] Datei geöffnet.

   1. Ändern Sie die Einstellung in [locked] oder [unlocked].
   1. Speichern und schließen Sie die Datei.

1. Um dies zur Einstellung für alle Benutzer zu machen, die mit demselben Arbeitsprofil arbeiten, klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Die ausgewählten Arbeitsbereiche sind nun entsprechend der Einstellung in der neuen Datei gesperrt oder entsperrt.
