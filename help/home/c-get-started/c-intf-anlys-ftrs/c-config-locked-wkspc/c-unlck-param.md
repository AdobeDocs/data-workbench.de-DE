---
description: Der Parameter "Entsperren"in der Datei "Insight.cfg"eines Benutzers gibt an, ob dieser Benutzer berechtigt ist, gesperrte Arbeitsbereiche zur Bearbeitung vorübergehend zu entsperren.
solution: Analytics
title: Parameter unlock festlegen
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Parameter unlock festlegen{#set-the-unlock-parameter}

Der Parameter &quot;Entsperren&quot;in der Datei &quot;Insight.cfg&quot;eines Benutzers gibt an, ob dieser Benutzer berechtigt ist, gesperrte Arbeitsbereiche zur Bearbeitung vorübergehend zu entsperren.

Wenn der Parameter Entsperren bereits in der [!DNL Insight.cfg] Datei des Benutzers vorhanden ist, können Sie den Parameter mithilfe von Data Workbench bearbeiten. Wenn sie nicht bereits in der [!DNL Insight.cfg] Datei des Benutzers vorhanden ist, müssen Sie sie der Datei mithilfe eines Texteditors wie Notepad hinzufügen.

**So legen Sie einen vorhandenen[!DNL Unlock]Parameter in der Datei Insight.cfg fest**

1. Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Die [!DNL Insight.cfg] Datei wird geöffnet.
1. Geben Sie für den Parameter Entsperren entweder true oder false ein. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsflächen vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Um die Konfigurationsänderungen zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

**So fügen Sie der Datei Insight.cfg den Parameter Unlock hinzu**

1. Navigieren Sie zum Installationsordner von Data Workbench und öffnen Sie die [!DNL Insight.cfg] Datei mit einem Texteditor wie Notepad.
1. Fügen Sie den Parameter Entsperren am Ende der Datei hinzu, wie im folgenden Beispiel:

[!DNL Unlock = bool: false]

1. Legen Sie den Wert entweder auf true oder false fest. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsflächen vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Speichern und schließen Sie die Datei.

