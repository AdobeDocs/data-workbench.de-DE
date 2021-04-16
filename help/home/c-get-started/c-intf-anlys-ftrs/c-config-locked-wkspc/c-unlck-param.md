---
description: Der Parameter "Entsperren"in der Datei "Insight.cfg"eines Benutzers gibt an, ob dieser Benutzer berechtigt ist, gesperrte Arbeitsbereiche zur Bearbeitung vorübergehend zu entsperren.
title: Einrichten des Entsperrungsparameters
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Einrichten des Entsperrungsparameters{#set-the-unlock-parameter}

Der Parameter &quot;Entsperren&quot;in der Datei &quot;Insight.cfg&quot;eines Benutzers gibt an, ob dieser Benutzer berechtigt ist, gesperrte Arbeitsbereiche zur Bearbeitung vorübergehend zu entsperren.

Wenn der Parameter Entsperren bereits in der Datei [!DNL Insight.cfg] des Benutzers vorhanden ist, können Sie den Parameter mit der Data Workbench bearbeiten. Wenn sie nicht bereits in der Datei [!DNL Insight.cfg] des Benutzers vorhanden ist, müssen Sie sie der Datei mithilfe eines Texteditors wie Notepad hinzufügen.

**So legen Sie einen vorhandenen  [!DNL Unlock] Parameter in der Datei Insight.cfg fest**

1. Klicken Sie in einem Arbeitsbereich mit der rechten Maustaste auf **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Die Datei [!DNL Insight.cfg] wird geöffnet.
1. Geben Sie für den Parameter Entsperren entweder true oder false ein. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsflächen vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Klicken Sie zum Speichern der Konfigurationsänderungen mit der rechten Maustaste auf **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

**So fügen Sie der Datei Insight.cfg den Parameter Unlock hinzu**

1. Navigieren Sie zum Installationsordner Ihrer Data Workbench und öffnen Sie die Datei [!DNL Insight.cfg] mithilfe eines Texteditors wie Notepad.
1. hinzufügen Sie den Parameter Entsperren wie im folgenden Beispiel an das Dateiende:

[!DNL Unlock = bool: false]

1. Legen Sie den Wert entweder auf true oder false fest. &quot;True&quot;ermöglicht dem Benutzer, gesperrte Arbeitsflächen vorübergehend zu entsperren, während &quot;false&quot;dies nicht tut.
1. Speichern und schließen Sie die Datei.
