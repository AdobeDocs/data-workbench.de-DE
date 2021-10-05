---
description: Sie können einen Arbeitsbereich als .png-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.
title: Exportieren eines Arbeitsbereichs
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exportieren eines Arbeitsbereichs{#export-a-workspace}

Sie können einen Arbeitsbereich als .png-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.

## Exportieren von Arbeitsbereichen als PNG-Datei {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Sie können einen Schnappschuss eines Arbeitsbereichs im Portable Network Graphic-Format (`.png` Dateien) speichern. Beim Speichern von Arbeitsbereichen als `.png`-Dateien sind die folgenden Farboptionen verfügbar:

* **Der** Arbeitsbereich wird mit schwarzem Hintergrund kopiert, wie er angezeigt wird.
* **Der weiße** Hintergrund kopiert die Elemente des Arbeitsbereichs in Farbe und zeigt sie auf einem weißen Hintergrund an.
* **Weißer Hintergrund (B&amp;W)** kopiert die Elemente des Arbeitsbereichs in Graustufen und zeigt sie auf einem weißen Hintergrund an.

**So exportieren Sie einen Arbeitsbereich als PNG-Datei**

Klicken Sie im Menü der Titelleiste eines Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]***.

Das Dialogfeld [!UICONTROL Save Image As] wird angezeigt.

Navigieren Sie zu dem Verzeichnis, in dem Sie die Datei speichern möchten, ändern Sie bei Bedarf den Namen der Datei und klicken Sie auf **[!UICONTROL Save]**.

## Exportieren von Workspace-Daten in Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Beim Exportieren eines Arbeitsbereichs in Excel exportiert Data Workbench Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt.

Um Arbeitsbereiche und einzelne Fenster in Microsoft Excel zu exportieren, müssen die folgenden Anforderungen erfüllt sein:

* Microsoft Excel muss auf demselben Computer installiert sein wie Data Workbench.
* Das Benutzerkonto, unter dem die Data Workbench ausgeführt wird, muss über die Berechtigung zum Zugriff auf Microsoft Excel verfügen.

>[!NOTE]
>
>* Wenn Sie Daten als Excel-Dateien exportieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Prozess finden Sie unter [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
>* Data Workbench unterstützt zwar mehr als 256 Spalten und 65.536 Datenzeilen, Versionen von Microsoft Excel vor 8.0 jedoch nicht.
>


Wenn diese Anforderungen erfüllt sind, startet Data Workbench automatisch Microsoft Excel und exportiert die Daten in eine neue Excel-Arbeitsmappe. Daten werden nicht aus den folgenden Visualisierungen exportiert: Grafiken, Pfadbrowser, Prozesskarten, Streudiagramme und Globen.

## Anwenden benutzerdefinierter Titel {#section-a332e157554546cb8e88922a8d7a4fa2}

Sofern Sie im Menü [!UICONTROL Export] keinen benutzerdefinierten Titel für das Fenster angegeben haben, wird der aufgelistete [!UICONTROL Export title] (z. B. &quot;City Table&quot;) als Arbeitsblattname verwendet.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie im Feld **[!UICONTROL Custom title]** auf .
1. Geben Sie den Titel ein, der auf das Fenster angewendet werden soll.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Wenn Sie im Feld [!UICONTROL Custom title] einen Bindestrich (-) eingeben, wird diese Visualisierung nicht mit dem Arbeitsbereich exportiert.

Wenn Sie den Arbeitsbereich nach Excel exportieren, wird das Arbeitsblatt, das die Daten für dieses Fenster enthält, mit dem Titel benannt, den Sie anstelle des Titels im Feld [!UICONTROL Export title] angegeben haben.

## Exportieren eines Arbeitsbereichs oder einer Seitenleiste in Excel {#section-360438b66d5f4734826ab463b4a01a75}

**So exportieren Sie Workspace-Daten in eine neue  [!DNL .xls] oder  [!DNL .xlsx] Datei**

1. Klicken Sie in der Titelleiste des Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Geben Sie an, ob der Arbeitsbereich, die Seitenleiste oder beides exportiert werden soll.

## Exportieren in eine Excel-Vorlagendatei {#section-814772929ca64cf6b92b89d3fdd02302}

Sie können Daten in Ihrem Arbeitsbereich in eine Excel-Vorlagendatei (`.xls` oder `.xlsx`) exportieren. Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie bei jedem Export des Arbeitsbereichs mit der Formatierung Ihrer Daten verbringen.

>[!NOTE]
>
>Diese Vorlagendatei muss eine `.xls`- oder `.xlsx`-Datei sein, keine `.xlt`-Datei.

Beim Exportieren der Daten werden die in der Vorlage vorhandenen Tabellenblätter mit Registerkarten (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Arbeitsbereich repliziert, während alle neuen Fenster, die nicht in der Vorlage als Tabellenblätter vorhanden sind, ignoriert werden. Alle anderen Tabellenblätter in der Vorlagendatei bleiben unverändert.

Wenn Sie außerdem ein Makro in der Excel-Vorlagendatei definiert haben, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;.

Nehmen wir an, Sie möchten exportierte Kampagnendaten aus einer Tabellenvisualisierung in einem Tortendiagramm auf einem anderen Tabellenblatt in einer Excel-Datei verwenden und diese Informationen wöchentlich aktualisieren. Sie können eine Vorlage verwenden, damit Sie Ihre Verweise nicht jedes Mal, wenn Sie die Daten aktualisieren möchten, vom Tabellenblatt der Tabelle in das Tabellenblatt des Tortendiagramms neu erstellen müssen. Die Tabellendaten werden beim Export aktualisiert, wodurch das Kreisdiagramm automatisch aktualisiert wird.

**So exportieren Sie Workspace-Daten in eine Vorlage  [!DNL .xls] oder  [!DNL .xlsx] Datei**

1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Geben Sie an, ob ein Arbeitsbereich, eine Seitenleiste oder beides exportiert werden soll.

   Das Dialogfeld [!UICONTROL Select a template worksheet] wird geöffnet.

1. Führen Sie je nach Bedarf einen der folgenden Schritte aus:

   * Wenn Sie eine Vorlagendatei `.xls` verwenden:

      1. Suchen Sie die Vorlage `.xls` und wählen Sie sie aus.
      1. Klicken Sie auf **[!UICONTROL Open]**.
   * Wenn Sie eine Vorlagendatei `.xlsx` verwenden:

      1. Navigieren Sie zum Speicherort der Vorlagendatei. Der Dateiname `.xlsx` wird nicht angezeigt.
      1. Geben Sie im Feld [!UICONTROL File name] `.xlsx` ein und klicken Sie auf **[!UICONTROL Open]**. Alle `.xlsx` Dateinamen werden in der Dateiliste angezeigt.

      1. Wählen Sie die Vorlage `.xlsx` aus.
      1. Klicken Sie auf **[!UICONTROL Open]**.
