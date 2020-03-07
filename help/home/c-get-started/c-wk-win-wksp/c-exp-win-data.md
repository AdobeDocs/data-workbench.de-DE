---
description: Sie können die Daten in bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) oder in eine tabulatorgetrennte Wertedatei (.tsv) exportieren.
solution: Analytics
title: Fensterdaten exportieren
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fensterdaten exportieren{#export-window-data}

Sie können die Daten in bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) oder in eine tabulatorgetrennte Wertedatei (.tsv) exportieren.

Daten werden nicht aus Diagrammen, Pfadbrowsern, Prozesskarten, Streudiagrammen und Globes exportiert.

## Exportieren von Fensterdaten in Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Um individuelle Fensterdaten in Microsoft Excel zu exportieren, müssen die folgenden Anforderungen erfüllt sein:

* Microsoft Excel muss auf demselben Computer wie Data Workbench installiert sein.
* Das Benutzerkonto, unter dem der Data Workbench-Prozess ausgeführt wird, muss über die Berechtigung zum Zugriff auf Microsoft Excel verfügen.
* Wenn Sie Daten als Excel-Dateien exportieren, öffnen Sie eine neue Instanz von Excel.
* Obwohl Data Workbench mehr als 256 Spalten und 65.536 Datenzeilen unterstützt, ist Microsoft Excel-Versionen vor 8.0 nicht verfügbar.

Wenn diese Anforderungen erfüllt sind, startet Data Workbench automatisch Microsoft Excel und exportiert die Daten in eine neue Excel-Arbeitsmappe, wenn Sie die **[!UICONTROL Export To Excel]** Menüoption auswählen.

**So exportieren Sie Fensterdaten in eine .xls- oder .xlsx-Datei**

Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel öffnet eine neue Arbeitsmappe, die die exportierten Daten enthält. Sofern Sie keinen benutzerdefinierten Titel angegeben haben (wie im folgenden Abschnitt beschrieben), wird diese Arbeitsmappe mit dem [!DNL Export title] (Tag-Tabelle im Beispiel oben) benannt.

## Anwenden benutzerdefinierter Titel {#section-2a6559df812a470685e43923b7b9024e}

Wenn Sie einen benutzerdefinierten Titel für ein Fenster angeben (mithilfe des [!DNL Custom title] Felds im [!DNL Export] Menü), wird das Arbeitsblatt, in das Data Workbench die Daten exportiert, mit diesem benutzerdefinierten Titel anstelle des Titels im Feld (Tabelle am Tag im Beispiel oben) benannt [!DNL Export title] .

**So wenden Sie einen benutzerdefinierten Titel auf eine Visualisierung an**

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf das **[!UICONTROL Custom title]** Feld.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Wenn Sie die Visualisierung in Excel exportieren, wird das Arbeitsblatt, das die Daten für dieses Fenster enthält, mit dem angegebenen Titel anstelle des Titels im [!DNL Export title] Feld benannt.

## Exportieren von Fensterdaten in eine TSV-Datei {#section-93c6b24f7338430aaf5a63b99b9489e8}

**So exportieren Sie ein Fenster in eine .tsv-Datei**

Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. Das [!DNL Save Window] Dialogfeld wird angezeigt.
1. Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern möchten. Ändern Sie bei Bedarf den Namen der Datei und klicken Sie auf **[!UICONTROL Save]**.

