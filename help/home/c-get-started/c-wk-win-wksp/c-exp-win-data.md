---
description: Sie können die Daten in bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) oder in eine tabulatorgetrennte Wertedatei (.tsv) exportieren.
title: Exportieren der Daten eines Fensters
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Exportieren der Daten eines Fensters{#export-window-data}

Sie können die Daten in bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) oder in eine tabulatorgetrennte Wertedatei (.tsv) exportieren.

Daten werden nicht aus Diagrammen, Pfadbrowsern, Prozesskarten, Streudiagrammen und Globes exportiert.

## Exportieren von Fensterdaten nach Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Um individuelle Fensterdaten in Microsoft Excel zu exportieren, müssen die folgenden Anforderungen erfüllt sein:

* Microsoft Excel muss auf demselben Computer wie die Data Workbench installiert sein.
* Das Benutzerkonto, unter dem die Data Workbench ausgeführt wird, muss über die Berechtigung zum Zugriff auf Microsoft Excel verfügen.
* Wenn Sie Daten als Excel-Dateien exportieren, öffnen Sie eine neue Instanz von Excel.
* Obwohl Data Workbench mehr als 256 Spalten und 65.536 Datenzeilen unterstützt, ist Microsoft Excel-Versionen vor 8.0 nicht verfügbar.

Wenn diese Anforderungen erfüllt sind, wird bei der Data Workbench automatisch Microsoft Excel Beginn und die Daten in eine neue Excel-Arbeitsmappe exportiert, wenn Sie die Menüoption **[!UICONTROL Export To Excel]** auswählen.

**So exportieren Sie Fensterdaten in eine .xls- oder .xlsx-Datei**

Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel öffnet eine neue Arbeitsmappe, die die exportierten Daten enthält. Sofern Sie keinen benutzerdefinierten Titel angegeben haben (wie im folgenden Abschnitt beschrieben), wird diese Arbeitsmappe mit dem Namen [!DNL Export title] (Tag-Tabelle im Beispiel oben) benannt.

## Anwenden benutzerdefinierter Titel {#section-2a6559df812a470685e43923b7b9024e}

Wenn Sie einen benutzerdefinierten Titel für ein Fenster angeben (mithilfe des Felds [!DNL Custom title] im Menü [!DNL Export]), wird das Arbeitsblatt, in das die Data Workbench die Daten exportiert, mit diesem benutzerdefinierten Titel anstelle des Titels im Feld [!DNL Export title] (Tabelle &quot;Tag&quot;im obigen Beispiel) benannt.

**So wenden Sie einen benutzerdefinierten Titel auf eine Visualisierung an**

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie in das Feld **[!UICONTROL Custom title]**.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Wenn Sie die Visualisierung in Excel exportieren, wird das Arbeitsblatt mit den Daten für dieses Fenster mit dem Titel benannt, den Sie anstelle des Titels im Feld [!DNL Export title] angegeben haben.

## Exportieren von Fensterdaten in eine TSV-Datei {#section-93c6b24f7338430aaf5a63b99b9489e8}

**So exportieren Sie ein Fenster in eine .tsv-Datei**

Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. Das Dialogfeld [!DNL Save Window] wird angezeigt.
1. Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern möchten. Ändern Sie bei Bedarf den Namen der Datei und klicken Sie auf **[!UICONTROL Save]**.
