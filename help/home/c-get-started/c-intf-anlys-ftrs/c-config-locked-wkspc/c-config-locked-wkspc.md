---
description: Data Workbench kann so konfiguriert werden, dass nur bestimmte Benutzer bestimmte Arbeitsbereiche ändern können.
title: Konfigurieren gesperrter Arbeitsbereiche
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Konfigurieren gesperrter Arbeitsbereiche{#configure-a-locked-workspace}

{{eol}}

Data Workbench kann so konfiguriert werden, dass nur bestimmte Benutzer bestimmte Arbeitsbereiche ändern können.

Während ein Arbeitsbereich gesperrt ist, können Benutzer in den meisten Visualisierungen Auswahlen treffen und die Daten in Tabellen sortieren, den Arbeitsbereich jedoch nicht ändern. Diese Funktion verhindert, dass Benutzer unbeabsichtigte Änderungen an den Arbeitsbereichen vornehmen.

Die folgenden drei Elemente arbeiten zusammen, um das Sperren von Arbeitsbereichen zu steuern:

* **Ordner.lock oder *Arbeitsbereichname*.lock-Datei:** A [!DNL folder.lock] -Datei gibt an, ob die Arbeitsbereiche in einem bestimmten Ordner gesperrt sind, während ein Arbeitsbereich [!DNL name.lock] gibt an, ob ein bestimmter Arbeitsbereich gesperrt ist.

* **Der Parameter Entsperren im [!DNL Insight.cfg] Datei:** Dieser Parameter gibt an, ob dieser Benutzer vorübergehend Sperren von Arbeitsbereichen entsperren kann.
* **Die Menüoption &quot;Vorübergehendes Entsperren&quot;:** Wenn der Parameter Entsperren im [!DNL Insight.cfg] auf &quot;true&quot;gesetzt ist, wird diese Option automatisch im Menü der Titelleiste jedes gesperrten Arbeitsbereichs angezeigt, um dem Benutzer die Möglichkeit zu geben, sie zu entsperren.

Informationen zu [!DNL folder.lock] und Arbeitsbereich [!DNL name.lock] -Dateien, siehe folgenden Abschnitt. Informationen zum Festlegen des Entsperrungsparameters finden Sie unter [Festlegen des Entsperrungsparameters](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Informationen zum [!DNL Temporarily Unlock menu] , siehe [Entsperren eines Arbeitsbereichs](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
