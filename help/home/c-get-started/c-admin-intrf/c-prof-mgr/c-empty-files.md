---
description: Wenn Sie nicht berechtigt sind, Dateien aus einem Profil zu löschen oder eine Datei nicht dauerhaft zu löschen, können Sie leere (Null-Byte-)Dateien verwenden, um Dateien auszublenden.
title: Ausblenden von Dateien durch Leeren ihres Inhalts (Null-Byte)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Ausblenden von Dateien durch Leeren ihres Inhalts (Null-Byte){#hide-a-file-by-emptying-it-zero-byte}

Wenn Sie nicht berechtigt sind, Dateien aus einem Profil zu löschen oder eine Datei nicht dauerhaft zu löschen, können Sie leere (Null-Byte-)Dateien verwenden, um Dateien auszublenden.

In der Spalte [!DNL Profile Manager] gibt ein Bindestrich (-) anstelle eines Häkchens eine Null-Byte-Datei an.

![](assets/vis_ProfMgr_Zero-byte.png)

Im Gegensatz zu den anderen Methoden zum Ausblenden von Dateien (z. B. [!DNL order.txt], dem Parameter &quot;Anzeigen&quot;und dem Parameter &quot;Ausgeblendet&quot;) behandelt Data Workbench Nullbyte-Dateien als nicht vorhanden. Wenn Sie z. B. ein Nullbyte-Attribut einer Dimension verwenden, die in einer Visualisierung oder Metrikdefinition verwendet wurde, erzeugt die Data Workbench einen Fehler für diese Visualisierung bzw. Metrik.

Diese Funktion ist aus verschiedenen Gründen nützlich, z. B. wenn Sie Folgendes tun möchten:

* **Machen Sie eine Datei in der Data Workbench** unbrauchbar, ohne dass die zum Löschen der Profil erforderlichen Berechtigungen erforderlich sind.
* **Verschieben Sie eine Metrik, Dimension oder einen** Filter an einen anderen Speicherort, ohne dass dafür die erforderlichen Profil-Berechtigungen erforderlich sind.
* **Menüelemente ausblenden** Das  [!DNL Base] Profil hat beispielsweise eine  [!DNL Metric Legend] Definition in der  [!DNL Metric.vw] Datei. Angenommen, Ihre Firma hat drei Metriklegenden erstellt, die in einem Untermenü Hinzufügen Legende > Metrik angezeigt werden sollen. Sie können die Datei [!DNL Base] Profil [!DNL Metric.vw] mit Null-Byte versehen, sodass nur Ihr neues Untermenü und drei neue Metriklegenden angezeigt werden.

**So blenden Sie eine Datei aus**

1. Öffnen Sie unter [!DNL Profile Manager] die erforderlichen Ordner und Unterordner, um die Datei zu suchen, die Sie als 0-Byte-Datei verwenden möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Öffnen Sie die lokale Datei und löschen Sie deren Inhalt.
1. Speichern und schließen Sie die Datei.
