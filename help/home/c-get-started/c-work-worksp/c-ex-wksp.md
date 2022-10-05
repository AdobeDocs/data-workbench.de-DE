---
description: Sie können einen Arbeitsbereich als .png-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.
title: Exportieren eines Arbeitsbereichs
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exportieren eines Arbeitsbereichs{#export-a-workspace}

{{eol}}

Sie können einen Arbeitsbereich als .png-Bilddatei exportieren oder die Daten aus bestimmten Fenstern in eine Excel-Datei (.xls oder .xlsx) exportieren.

## Exportieren von Arbeitsbereichen als PNG-Datei {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Sie können eine Momentaufnahme eines Arbeitsbereichs im Grafikformat des Portable Network (`.png` -Dateien). Die folgenden Farboptionen sind beim Speichern von Arbeitsbereichen als `.png` -Dateien:

* **Schwarzer Hintergrund** kopiert den Arbeitsbereich wie angezeigt.
* **Weißer Hintergrund** kopiert die Elemente des Arbeitsbereichs in Farbe und zeigt sie auf einem weißen Hintergrund an.
* **Weißer Hintergrund (B&amp;W)** kopiert die Elemente des Arbeitsbereichs in Graustufen und zeigt sie auf einem weißen Hintergrund an.

**So exportieren Sie einen Arbeitsbereich als PNG-Datei**

Klicken Sie im Menü der Titelleiste eines Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

Das Dialogfeld [!UICONTROL Save Image As] wird angezeigt.

Navigieren Sie zum Verzeichnis, in dem Sie die Datei speichern möchten, ändern Sie ggf. den Namen der Datei und klicken Sie auf **[!UICONTROL Save]**.

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

Wenn Sie keinen benutzerdefinierten Titel für das Fenster auf der [!UICONTROL Export] Menü, [!UICONTROL Export title] aufgeführt (z. B. City Table) wird als Arbeitsblattname verwendet.

1. Klicken Sie mit der rechten Maustaste auf den oberen Rand des Fensters und klicken Sie auf die Schaltfläche **[!UICONTROL Custom title]** -Feld.
1. Geben Sie den Titel ein, der auf das Fenster angewendet werden soll.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Wenn Sie einen Bindestrich (-) im [!UICONTROL Custom title] -Feld, wird diese Visualisierung nicht mit dem Arbeitsbereich exportiert.

Wenn Sie den Arbeitsbereich nach Excel exportieren, wird das Arbeitsblatt, das die Daten für dieses Fenster enthält, mit dem Titel benannt, den Sie anstelle des Titels im [!UICONTROL Export title] -Feld.

## Exportieren eines Arbeitsbereichs oder einer Seitenleiste in Excel {#section-360438b66d5f4734826ab463b4a01a75}

**So exportieren Sie Workspace-Daten in eine neue [!DNL .xls] oder [!DNL .xlsx] file**

1. Klicken Sie in der Titelleiste des Arbeitsbereichs auf **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Geben Sie an, ob der Arbeitsbereich, die Seitenleiste oder beides exportiert werden soll.

## Exportieren in eine Excel-Vorlagendatei {#section-814772929ca64cf6b92b89d3fdd02302}

Sie können Daten in Ihrem Arbeitsbereich in eine Excel-Vorlagendatei (`.xls` oder `.xlsx`). Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie bei jedem Export des Arbeitsbereichs mit der Formatierung Ihrer Daten verbringen.

>[!NOTE]
>
>Diese Vorlagendatei muss ein `.xls` oder `.xlsx` nicht `.xlt` -Datei.

Beim Exportieren der Daten werden die in der Vorlage vorhandenen Tabellenblätter mit Registerkarten (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Arbeitsbereich repliziert, während alle neuen Fenster, die nicht in der Vorlage als Tabellenblätter vorhanden sind, ignoriert werden. Alle anderen Tabellenblätter in der Vorlagendatei bleiben unverändert.

Wenn Sie außerdem ein Makro in der Excel-Vorlagendatei definiert haben, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;.

Nehmen wir an, Sie möchten exportierte Kampagnendaten aus einer Tabellenvisualisierung in einem Tortendiagramm auf einem anderen Tabellenblatt in einer Excel-Datei verwenden und diese Informationen wöchentlich aktualisieren. Sie können eine Vorlage verwenden, damit Sie Ihre Verweise nicht jedes Mal, wenn Sie die Daten aktualisieren möchten, vom Tabellenblatt der Tabelle in das Tabellenblatt des Tortendiagramms neu erstellen müssen. Die Tabellendaten werden beim Export aktualisiert, wodurch das Kreisdiagramm automatisch aktualisiert wird.

**So exportieren Sie Workspace-Daten in eine Vorlage [!DNL .xls] oder [!DNL .xlsx] file**

1. Klicken Sie mit der rechten Maustaste auf die Titelleiste des Arbeitsbereichs und klicken Sie auf **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Geben Sie an, ob ein Arbeitsbereich, eine Seitenleiste oder beides exportiert werden soll.

   Die [!UICONTROL Select a template worksheet] wird geöffnet.

1. Führen Sie je nach Bedarf einen der folgenden Schritte aus:

   * Wenn Sie eine `.xls` Vorlagendatei:

      1. Vorlage suchen und auswählen `.xls` -Datei.
      1. Klicken Sie auf **[!UICONTROL Open]**.
   * Wenn Sie eine `.xlsx` Vorlagendatei:

      1. Navigieren Sie zum Speicherort der Vorlagendatei. Die `.xlsx` Dateiname wird nicht angezeigt.
      1. Im [!UICONTROL File name] Feld, Typ `.xlsx` und klicken Sie auf **[!UICONTROL Open]**. Alle `.xlsx` Dateinamen werden in der Dateiliste angezeigt.

      1. Vorlage auswählen `.xlsx` -Datei.
      1. Klicken Sie auf **[!UICONTROL Open]**.
