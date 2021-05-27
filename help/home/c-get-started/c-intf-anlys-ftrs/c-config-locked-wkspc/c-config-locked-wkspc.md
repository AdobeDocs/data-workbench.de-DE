---
description: Data Workbench kann so konfiguriert werden, dass nur bestimmte Benutzer bestimmte Arbeitsbereiche ändern können.
title: 'Konfigurieren gesperrter Arbeitsbereiche '
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Konfigurieren gesperrter Arbeitsbereiche{#configure-a-locked-workspace}

Data Workbench kann so konfiguriert werden, dass nur bestimmte Benutzer bestimmte Arbeitsbereiche ändern können.

Während ein Arbeitsbereich gesperrt ist, können Benutzer in den meisten Visualisierungen Auswahlen treffen und die Daten in Tabellen sortieren, den Arbeitsbereich jedoch nicht ändern. Diese Funktion verhindert, dass Benutzer unbeabsichtigte Änderungen an den Arbeitsbereichen vornehmen.

Die folgenden drei Elemente arbeiten zusammen, um das Sperren von Arbeitsbereichen zu steuern:

* **Datei &quot;folder.lock&quot;oder &quot; *workspace name*.lock&quot;:**  Eine  [!DNL folder.lock] Datei, die angibt, ob die Arbeitsbereiche in einem bestimmten Ordner gesperrt sind, während eine Workspace- [!DNL name.lock] Datei angibt, ob ein bestimmter Arbeitsbereich gesperrt ist.

* **Der Parameter Entsperren in der  [!DNL Insight.cfg] Datei eines Benutzers:** Dieser Parameter gibt an, ob dieser Benutzer vorübergehend entsperrte Arbeitsbereiche entsperren kann.
* **Die Menüoption &quot;Vorübergehendes Entsperren&quot;:**  Wenn der Parameter Entsperren im Benutzermenü auf &quot;true&quot;gesetzt  [!DNL Insight.cfg] ist, wird diese Option automatisch im Menü der Titelleiste jedes gesperrten Arbeitsbereichs angezeigt, um dem Benutzer die Möglichkeit zu geben, sie zu entsperren.

Informationen zu [!DNL folder.lock]- und Arbeitsbereich [!DNL name.lock]-Dateien finden Sie im folgenden Abschnitt. Informationen zum Festlegen des Entsperrungsparameters finden Sie unter [Festlegen des Entsperrungsparameters](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Weitere Informationen zur Option [!DNL Temporarily Unlock menu] finden Sie unter [Entsperren eines Workspace](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
