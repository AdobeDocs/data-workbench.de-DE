---
description: Sie können einen Arbeitsbereich als PNG-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.
solution: Analytics
title: Eine Arbeitsfläche exportieren
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Eine Arbeitsfläche exportieren{#export-a-workspace}

Sie können einen Arbeitsbereich als PNG-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.

## Arbeitsbereiche als PNG-Datei exportieren {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Sie können eine Momentaufnahme eines Arbeitsbereichs im Portable Network Graphic-Format (`.png` -Dateien) speichern. Beim Speichern von Arbeitsbereichen als `.png` Dateien stehen die folgenden Farboptionen zur Verfügung:

* **Der Arbeitsbereich wird mit schwarzem Hintergrund** kopiert.
* **Der weiße Hintergrund** kopiert die Elemente des Arbeitsbereichs in Farbe und zeigt sie auf einem weißen Hintergrund an.
* **Der weiße Hintergrund (B&amp;W)** kopiert die Elemente des Arbeitsbereichs in Graustufen und zeigt sie auf einem weißen Hintergrund an.

**So exportieren Sie eine Arbeitsfläche als PNG-Datei**

Klicken Sie im Menü der Titelleiste eines Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

Das [!UICONTROL Save Image As] Dialogfeld wird angezeigt.

Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern möchten, ändern Sie bei Bedarf den Namen der Datei und klicken Sie auf **[!UICONTROL Save]**.

## Arbeitsflächendaten nach Microsoft Excel exportieren {#section-fe214e3dbc364d2eba3834d62d295acb}

Beim Exportieren eines Arbeitsbereichs in Excel exportiert Data Workbench Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt.

Um Arbeitsflächen und einzelne Fenster in Microsoft Excel zu exportieren, müssen die folgenden Anforderungen erfüllt sein:

* Microsoft Excel muss auf demselben Computer wie Data Workbench installiert sein.
* Das Benutzerkonto, unter dem der Data Workbench-Prozess ausgeführt wird, muss über die Berechtigung zum Zugriff auf Microsoft Excel verfügen.

>[!NOTE]
>
>* Wenn Sie Daten als Excel-Dateien exportieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Vorgang finden Sie unter [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Obwohl Data Workbench mehr als 256 Spalten und 65.536 Datenzeilen unterstützt, ist Microsoft Excel-Versionen vor 8.0 nicht verfügbar.
>



Wenn diese Anforderungen erfüllt sind, startet Data Workbench automatisch Microsoft Excel und exportiert die Daten in eine neue Excel-Arbeitsmappe. Daten werden nicht aus den folgenden Visualisierungen exportiert: Diagramme, Pfadbrowser, Prozesskarten, Streudiagramme und Globes.

## Anwenden benutzerdefinierter Titel {#section-a332e157554546cb8e88922a8d7a4fa2}

Sofern Sie keinen benutzerdefinierten Titel für das Fenster im [!UICONTROL Export] Menü angegeben haben, wird die [!UICONTROL Export title] aufgelistete Tabelle (z. B. City Table) als Arbeitsblattname verwendet.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf das **[!UICONTROL Custom title]** Feld.
1. Geben Sie den Titel ein, den Sie auf das Fenster anwenden möchten.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Wenn Sie einen Bindestrich (-) in das [!UICONTROL Custom title] Feld eingeben, wird diese Visualisierung nicht mit der Arbeitsfläche exportiert.

Wenn Sie den Arbeitsbereich in Excel exportieren, wird das Arbeitsblatt, das die Daten für dieses Fenster enthält, mit dem angegebenen Titel anstelle des Titels im [!UICONTROL Export title] Feld benannt.

## Eine Arbeitsfläche oder Seitenleiste in Excel exportieren {#section-360438b66d5f4734826ab463b4a01a75}

**So exportieren Sie Arbeitsflächendaten in eine neue[!DNL .xls]oder[!DNL .xlsx]-Datei**

1. Klicken Sie in der Titelleiste des Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Geben Sie an, ob der Arbeitsbereich, die Seitenleiste oder beides exportiert werden soll.

## In Excel-Vorlagendatei exportieren {#section-814772929ca64cf6b92b89d3fdd02302}

Sie können Daten in Ihrer Arbeitsfläche in eine Excel-Vorlagendatei (`.xls` oder `.xlsx`) exportieren. Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie mit der Formatierung Ihrer Daten verbringen, wenn der Arbeitsbereich exportiert wird.

>[!NOTE]
>
>Diese Vorlagendatei muss eine `.xls` oder `.xlsx` -Datei und keine `.xlt` Datei sein.

Wenn die Daten exportiert werden, werden die vorhandenen Registerkarten in der Vorlage (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Arbeitsbereich repliziert, während alle neuen Fenster, die nicht in der Vorlage als Arbeitsblatt vorhanden sind, ignoriert werden. Alle anderen Registerkarten in der Vorlagendatei bleiben unverändert.

Wenn in der Excel-Vorlagendatei ein Makro definiert ist, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;ein.

Nehmen wir an, Sie möchten exportierte Kampagnendaten aus einer Tabellenvisualisierung in einem Kreisdiagramm auf einem anderen Tabellenblatt in einer Excel-Datei verwenden und diese Informationen wöchentlich aktualisieren. Sie können eine Vorlage verwenden, damit Sie Ihre Verweise nicht jedes Mal neu erstellen müssen, wenn Sie die Daten aktualisieren möchten, vom Tabellenblatt der Tabelle auf das Tabellenblatt des Kreisdiagramms. Die Tabellendaten werden beim Export aktualisiert, wodurch das Kreisdiagramm automatisch aktualisiert wird.

**So exportieren Sie Arbeitsflächendaten in eine Vorlage[!DNL .xls]oder[!DNL .xlsx]Datei**

1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Geben Sie an, ob eine Arbeitsfläche, Seitenleiste oder beides exportiert werden soll.

   Das [!UICONTROL Select a template worksheet] Dialogfeld wird geöffnet.

1. Führen Sie je nach Bedarf einen der folgenden Schritte aus:

   * Wenn Sie eine `.xls` Vorlagendatei verwenden:

      1. Navigieren Sie zur `.xls` Vorlagendatei und wählen Sie sie aus.
      1. Klicken Sie auf **[!UICONTROL Open]**.
   * Wenn Sie eine `.xlsx` Vorlagendatei verwenden:

      1. Navigieren Sie zum Speicherort der Vorlagendatei. Der `.xlsx` Dateiname wird nicht angezeigt.
      1. Geben Sie in das [!UICONTROL File name] Feld ein `.xlsx` und klicken Sie auf **[!UICONTROL Open]**. Alle `.xlsx` Dateinamen werden in der Dateiliste angezeigt.

      1. Wählen Sie die `.xlsx` Vorlagendatei aus.
      1. Klicken Sie auf **[!UICONTROL Open]**.


