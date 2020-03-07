---
description: Wenn Sie nicht berechtigt sind, Dateien aus einem Profil zu löschen oder eine Datei nicht dauerhaft zu löschen, können Sie zum Ausblenden von Dateien leere Dateien (Nullbyte-Dateien) verwenden.
solution: Analytics
title: Ausblenden einer Datei durch Leeren (Null-Byte)
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ausblenden einer Datei durch Leeren (Null-Byte){#hide-a-file-by-emptying-it-zero-byte}

Wenn Sie nicht berechtigt sind, Dateien aus einem Profil zu löschen oder eine Datei nicht dauerhaft zu löschen, können Sie zum Ausblenden von Dateien leere Dateien (Nullbyte-Dateien) verwenden.

In der Spalte [!DNL Profile Manager]wird durch einen Bindestrich (-) anstelle eines Häkchens eine 0-Byte-Datei identifiziert.

![](assets/vis_ProfMgr_Zero-byte.png)

Im Gegensatz zu den anderen Methoden zum Ausblenden von Dateien (z. B. [!DNL order.txt]dem Parameter &quot;Anzeigen&quot;und dem Parameter &quot;Ausgeblendet&quot;) behandelt Data Workbench Nullbyte-Dateien als nicht vorhanden. Wenn Sie z. B. ein Nullbyte-Attribut einer Dimension verwenden, die in einer Visualisierung oder Metrikdefinition verwendet wurde, erzeugt Data Workbench einen Fehler für diese Visualisierung bzw. Metrik.

Diese Funktion ist aus verschiedenen Gründen nützlich, z. B. wenn Sie Folgendes tun möchten:

* **Machen Sie eine Datei in Data Workbench unbrauchbar** , ohne dass die zum Löschen der Datei erforderlichen Profilberechtigungen erforderlich sind.
* **Verschieben Sie eine Metrik, Dimension oder einen Filter** an einen anderen Speicherort, ohne dass die zum Löschen der Datei am ursprünglichen Speicherort erforderlichen Profilberechtigungen erforderlich sind.
* **Menüelemente ausblenden** Das [!DNL Base] Profil hat beispielsweise eine [!DNL Metric Legend] Definition in der [!DNL Metric.vw] Datei. Angenommen, Ihr Unternehmen hat drei Metriklegenden erstellt, die in einem Untermenü &quot;Legende hinzufügen&quot;> &quot;Metrik&quot;angezeigt werden sollen. Sie können die [!DNL Base] Profil- [!DNL Metric.vw] Datei mit Null-Byte versehen, sodass nur Ihr neues Untermenü und drei neue Metriklegenden angezeigt werden.

**So blenden Sie eine Datei aus**

1. Öffnen Sie im [!DNL Profile Manager]Ordner die erforderlichen Ordner und Unterordner, um die Datei zu suchen, die Sie als 0-Byte-Datei verwenden möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Namen der Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Öffnen Sie die lokale Datei und löschen Sie deren Inhalt.
1. Speichern und schließen Sie die Datei.

