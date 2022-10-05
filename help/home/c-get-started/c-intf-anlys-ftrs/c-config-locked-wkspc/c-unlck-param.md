---
description: Der Parameter Entsperren in der Datei Insight.cfg eines Benutzers gibt an, ob dieser Benutzer über die Berechtigung zum temporären Entsperren von Arbeitsbereichen zur Bearbeitung verfügt.
title: Einrichten des Entsperrungsparameters
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Einrichten des Entsperrungsparameters{#set-the-unlock-parameter}

{{eol}}

Der Parameter Entsperren in der Datei Insight.cfg eines Benutzers gibt an, ob dieser Benutzer über die Berechtigung zum temporären Entsperren von Arbeitsbereichen zur Bearbeitung verfügt.

Wenn der Parameter Entsperren bereits im [!DNL Insight.cfg] -Datei, können Sie den Parameter mithilfe von Data Workbench bearbeiten. Wenn es nicht bereits im [!DNL Insight.cfg] -Datei, müssen Sie sie mithilfe eines Texteditors, wie z. B. Notepad, zur Datei hinzufügen.

**So legen Sie eine vorhandene [!DNL Unlock] Parameter in der Datei Insight.cfg**

1. Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste auf **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Die [!DNL Insight.cfg] Datei geöffnet.
1. Geben Sie für den Parameter Entsperren entweder true oder false ein. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsbereiche vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Um Ihre Konfigurationsänderungen zu speichern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save as Insight.cfg]**.

**Hinzufügen des Entsperrungsparameters zur Datei Insight.cfg**

1. Navigieren Sie zum Installationsordner der Data Workbench und öffnen Sie die [!DNL Insight.cfg] Datei mit einem Texteditor wie Notepad.
1. Fügen Sie den Parameter Entsperren am Ende der Datei hinzu, wie im folgenden Beispiel gezeigt:

[!DNL Unlock = bool: false]

1. Setzen Sie den Wert auf &quot;true&quot;oder &quot;false&quot;. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsbereiche vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Speichern und schließen Sie die Datei.
