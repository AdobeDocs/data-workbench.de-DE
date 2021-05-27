---
description: Der Parameter Entsperren in der Datei Insight.cfg eines Benutzers gibt an, ob dieser Benutzer über die Berechtigung zum temporären Entsperren von Arbeitsbereichen zur Bearbeitung verfügt.
title: Einrichten des Entsperrungsparameters
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Einrichten des Entsperrungsparameters{#set-the-unlock-parameter}

Der Parameter Entsperren in der Datei Insight.cfg eines Benutzers gibt an, ob dieser Benutzer über die Berechtigung zum temporären Entsperren von Arbeitsbereichen zur Bearbeitung verfügt.

Wenn der Parameter Entsperren bereits in der Datei [!DNL Insight.cfg] des Benutzers vorhanden ist, können Sie den Parameter mit Data Workbench bearbeiten. Wenn sie nicht bereits in der [!DNL Insight.cfg]-Datei des Benutzers vorhanden ist, müssen Sie sie mithilfe eines Texteditors wie Notepad zur Datei hinzufügen.

**So legen Sie einen vorhandenen  [!DNL Unlock] Parameter in der Datei Insight.cfg fest**

1. Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste auf **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Die Datei [!DNL Insight.cfg] wird geöffnet.
1. Geben Sie für den Parameter Entsperren entweder true oder false ein. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsbereiche vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Klicken Sie zum Speichern Ihrer Konfigurationsänderungen mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

**Hinzufügen des Entsperrungsparameters zur Datei Insight.cfg**

1. Navigieren Sie zum Installationsordner Ihrer Data Workbench und öffnen Sie die Datei [!DNL Insight.cfg] mithilfe eines Texteditors wie Notepad.
1. Fügen Sie den Parameter Entsperren am Ende der Datei hinzu, wie im folgenden Beispiel gezeigt:

[!DNL Unlock = bool: false]

1. Setzen Sie den Wert auf &quot;true&quot;oder &quot;false&quot;. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsbereiche vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Speichern und schließen Sie die Datei.
