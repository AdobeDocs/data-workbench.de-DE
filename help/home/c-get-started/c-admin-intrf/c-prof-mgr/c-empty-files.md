---
description: Wenn Sie keine Berechtigung zum Löschen von Dateien aus einem Profil haben oder eine Datei nicht dauerhaft löschen möchten, können Sie leere (Null-Byte-)Dateien verwenden, um Dateien auszublenden.
title: Ausblenden von Dateien durch Leeren ihres Inhalts (Null-Byte)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Ausblenden von Dateien durch Leeren ihres Inhalts (Null-Byte){#hide-a-file-by-emptying-it-zero-byte}

{{eol}}

Wenn Sie keine Berechtigung zum Löschen von Dateien aus einem Profil haben oder eine Datei nicht dauerhaft löschen möchten, können Sie leere (Null-Byte-)Dateien verwenden, um Dateien auszublenden.

Im [!DNL Profile Manager], ein Bindestrich (-) anstelle eines Kontrollkästchens, in einer Spalte eine Nullbytedatei angibt.

![](assets/vis_ProfMgr_Zero-byte.png)

Im Gegensatz zu anderen Methoden zum Ausblenden von Dateien (z. B. [!DNL order.txt], dem Parameter Anzeigen und dem Parameter Ausgeblendet ), behandelt Data Workbench Nullbyte-Dateien als nicht vorhanden. Wenn Sie beispielsweise eine Dimension mit einem Nullbyte-Wert verwenden, die in einer Visualisierung oder Metrikdefinition verwendet wurde, erzeugt Data Workbench einen Fehler für diese Visualisierung bzw. Metrik.

Diese Funktion ist aus verschiedenen Gründen nützlich, z. B. wenn Sie Folgendes tun möchten:

* **Unbrauchbare Datei machen** in der Data Workbench, ohne dass die zum Löschen der Datei erforderlichen Profilberechtigungen erforderlich sind.
* **Verschieben von Metriken, Dimensionen oder Filtern** an einen anderen Speicherort klicken, ohne dass die erforderlichen Profilberechtigungen zum Löschen der Datei vom ursprünglichen Speicherort erforderlich sind.
* **Ausblenden von Menüelementen.** Beispiel: die [!DNL Base] ein Profil [!DNL Metric Legend] definiert im [!DNL Metric.vw] -Datei. Angenommen, Ihr Unternehmen hat drei Metriklegenden erstellt, die Sie im Untermenü Legende hinzufügen > Metrik anzeigen möchten. Sie können die [!DNL Base] profile [!DNL Metric.vw] -Datei, sodass nur Ihr neues Untermenü und drei neue Metriklegenden angezeigt werden.

**So blenden Sie eine Datei aus**

1. Im [!DNL Profile Manager], öffnen Sie die erforderlichen Ordner und Unterordner, um die Datei zu finden, die Sie als Nullbyte-Datei verwenden möchten.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben dem Dateinamen und klicken Sie auf **[!UICONTROL Make Local]**.
1. Öffnen Sie die lokale Datei und löschen Sie den Inhalt.
1. Speichern und schließen Sie die Datei.
