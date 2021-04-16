---
description: Sie können einen Arbeitsbereich als PNG-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.
title: Exportieren eines Arbeitsbereichs
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exportieren eines Arbeitsbereichs{#export-a-workspace}

Sie können einen Arbeitsbereich als PNG-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.

## Arbeitsbereiche als PNG-Datei {#section-f9fbe0f0a1c341e2b063cce106cac35e} exportieren

Sie können eine Momentaufnahme eines Arbeitsbereichs im Portable Network Graphic-Format (`.png`-Dateien) speichern. Die folgenden Farboptionen sind beim Speichern von Arbeitsbereichen als `.png`-Dateien verfügbar:

* **Schwarzer** Hintergrund kopiert den Arbeitsbereich wie angezeigt.
* **Der weiße** Hintergrund kopiert die Elemente des Arbeitsbereichs farbig und zeigt sie auf einem weißen Hintergrund an.
* **Der weiße Hintergrund (B&amp;W)** kopiert die Elemente des Arbeitsbereichs in Graustufen und zeigt sie auf einem weißen Hintergrund an.

**So exportieren Sie eine Arbeitsfläche als PNG-Datei**

Klicken Sie im Menü der Titelleiste eines Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]***.

Das Dialogfeld [!UICONTROL Save Image As] wird angezeigt.

Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern möchten, ändern Sie bei Bedarf den Namen der Datei und klicken Sie auf **[!UICONTROL Save]**.

## Exportieren von Workspace-Daten in Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Beim Exportieren einer Arbeitsfläche in Excel exportiert Data Workbench Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt.

Um Arbeitsflächen und einzelne Fenster in Microsoft Excel zu exportieren, müssen die folgenden Anforderungen erfüllt sein:

* Microsoft Excel muss auf demselben Computer wie die Data Workbench installiert sein.
* Das Benutzerkonto, unter dem die Data Workbench ausgeführt wird, muss über die Berechtigung zum Zugriff auf Microsoft Excel verfügen.

>[!NOTE]
>
>* Wenn Sie Daten als Excel-Dateien exportieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Vorgang finden Sie unter [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Obwohl Data Workbench mehr als 256 Spalten und 65.536 Datenzeilen unterstützt, ist Microsoft Excel-Versionen vor 8.0 nicht verfügbar.
>



Wenn diese Anforderungen erfüllt sind, wird bei der Data Workbench automatisch Microsoft Excel Beginn und die Daten in eine neue Excel-Arbeitsmappe exportiert. Daten werden nicht aus den folgenden Visualisierungen exportiert: Diagramme, Pfadbrowser, Prozesskarten, Streudiagramme und Globes.

## Anwenden benutzerdefinierter Titel {#section-a332e157554546cb8e88922a8d7a4fa2}

Sofern Sie im Menü [!UICONTROL Export] keinen benutzerdefinierten Titel für das Fenster angegeben haben, wird das aufgelistete [!UICONTROL Export title] (z. B. &quot;City Table&quot;) als Arbeitsblattname verwendet.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie in das Feld **[!UICONTROL Custom title]**.
1. Geben Sie den Titel ein, den Sie auf das Fenster anwenden möchten.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Wenn Sie im Feld [!UICONTROL Custom title] einen Bindestrich (-) eingeben, wird diese Visualisierung nicht mit der Arbeitsfläche exportiert.

Wenn Sie den Arbeitsbereich in Excel exportieren, wird das Arbeitsblatt mit den Daten für dieses Fenster mit dem Titel benannt, den Sie anstelle des Titels im Feld [!UICONTROL Export title] angegeben haben.

## Eine Arbeitsfläche oder Seitenleiste nach Excel exportieren {#section-360438b66d5f4734826ab463b4a01a75}

**So exportieren Sie Arbeitsflächendaten in eine neue  [!DNL .xls] oder  [!DNL .xlsx] Datei**

1. Klicken Sie in der Titelleiste des Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Geben Sie an, ob der Arbeitsbereich, die Seitenleiste oder beides exportiert werden soll.

## In Excel-Vorlagendatei {#section-814772929ca64cf6b92b89d3fdd02302} exportieren

Sie können Daten in Ihrer Arbeitsfläche in eine Excel-Vorlagendatei (`.xls` oder `.xlsx`) exportieren. Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie mit der Formatierung Ihrer Daten verbringen, wenn der Arbeitsbereich exportiert wird.

>[!NOTE]
>
>Bei dieser Vorlagendatei muss es sich um eine `.xls`- oder `.xlsx`-Datei und nicht um eine `.xlt`-Datei handeln.

Wenn die Daten exportiert werden, werden die vorhandenen Registerkarten in der Vorlage (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Arbeitsbereich repliziert, während alle neuen Fenster, die nicht in der Vorlage als Arbeitsblatt vorhanden sind, ignoriert werden. Alle anderen Registerkarten in der Vorlagendatei bleiben unverändert.

Wenn in der Excel-Vorlagendatei ein Makro definiert ist, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;ein.

Nehmen wir an, Sie möchten exportierte Kampagnen aus einer Tabellenvisualisierung in einem Kreisdiagramm auf einem anderen Tabellenblatt in einer Excel-Datei verwenden und diese Informationen wöchentlich aktualisieren. Sie können eine Vorlage verwenden, damit Sie Ihre Verweise nicht jedes Mal neu erstellen müssen, wenn Sie die Daten aktualisieren möchten, vom Tabellenblatt der Tabelle auf das Tabellenblatt des Kreisdiagramms. Die Tabellendaten werden beim Export aktualisiert, wodurch das Kreisdiagramm automatisch aktualisiert wird.

**So exportieren Sie Arbeitsflächendaten in eine Vorlage  [!DNL .xls] oder  [!DNL .xlsx] Datei**

1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Geben Sie an, ob eine Arbeitsfläche, Seitenleiste oder beides exportiert werden soll.

   Das Dialogfeld [!UICONTROL Select a template worksheet] wird geöffnet.

1. Führen Sie je nach Bedarf einen der folgenden Schritte aus:

   * Wenn Sie eine `.xls`-Vorlagendatei verwenden:

      1. Navigieren Sie zur Vorlage `.xls` und wählen Sie sie aus.
      1. Klicken Sie auf **[!UICONTROL Open]**.
   * Wenn Sie eine `.xlsx`-Vorlagendatei verwenden:

      1. Navigieren Sie zum Speicherort der Vorlagendatei. Der Dateiname `.xlsx` wird nicht angezeigt.
      1. Geben Sie im Feld [!UICONTROL File name] `.xlsx` ein und klicken Sie auf **[!UICONTROL Open]**. Alle `.xlsx`-Dateinamen werden in der Liste angezeigt.

      1. Wählen Sie die Vorlage `.xlsx` aus.
      1. Klicken Sie auf **[!UICONTROL Open]**.
