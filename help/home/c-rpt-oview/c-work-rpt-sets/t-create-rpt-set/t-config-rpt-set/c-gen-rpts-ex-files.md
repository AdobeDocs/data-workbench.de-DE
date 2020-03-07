---
description: Informationen zum Generieren von Berichten als Excel-Dateien.
solution: Analytics
title: Erstellen von Berichten als Microsoft Excel-Dateien
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Erstellen von Berichten als Microsoft Excel-Dateien{#generating-reports-as-microsoft-excel-files}

Informationen zum Generieren von Berichten als Excel-Dateien.

Folgende Anforderungen müssen erfüllt sein:

* Microsoft Excel muss auf demselben Computer installiert sein wie [!DNL Report Server].
* Das Benutzerkonto, unter dem der [!DNL Report Server] Prozess ausgeführt wird, muss Zugriff auf Microsoft Excel haben.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Wenn Sie Berichte als Excel-Dateien generieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Vorgang finden Sie unter [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
   >    * Obwohl Data Workbench mehr als 256 Spalten und 65.536 Datenzeilen unterstützt, ist dies in Microsoft Excel nicht der Fall.


Wenn diese Anforderungen erfüllt sind, wird Microsoft Excel [!DNL Report Server] automatisch gestartet und Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen werden in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt ausgegeben.

>[!NOTE]
>
>Daten werden nicht aus Diagrammen, Pfadbrowsern, Prozesskarten, Streudiagrammen und Globes exportiert.

Sofern Sie keine Angabe [!DNL Custom Title] für die Visualisierung vorgenommen haben, wird der Typ des Fensters (z. B. Filmtabelle) als Arbeitsblattname verwendet.

Weitere Informationen zum Festlegen [!DNL Custom Titles] für Visualisierungen finden Sie im [Data Workbench Client-Handbuch](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html).

## Verwenden einer Vorlagendatei {#section-40ab11916f464b1a88214ab969da6751}

Sie können einen Bericht auch als Excel-Datei mit einer Excel-Vorlagendatei ( [!DNL .xls] oder [!DNL .xlsx]) erstellen. Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie mit der Formatierung Ihrer Daten verbringen, wenn der Bericht erstellt wird.

Diese Vorlagendatei muss eine [!DNL .xls] oder [!DNL .xlsx] -Datei und keine [!DNL .xlt] Datei sein.

Sie können eine Vorlage für jeden einzelnen Bericht, eine allgemeine Vorlage für alle Berichte oder eine Kombination aus beiden festlegen. Da sich diese beiden Elemente nicht gegenseitig ausschließen, können Sie eine generische Vorlage definieren und dann auch bestimmte Vorlagen definieren.

Um einen Bericht mit einer generischen Vorlage zu erstellen, die Sie für alle Berichte verwenden, müssen Sie den Namen dieser Excel-Datei im Parameter &quot;Excel-Standardvorlage&quot;in der Datei [!DNL Report.cfg] für diesen Berichtssatz angeben und dann die Vorlagendatei in demselben Ordner wie der [!DNL Report.cfg] für diesen Berichtsatz ablegen (*Datenbasis-Installationsordner*\*Profilname*\Reports\*ReportSetName*). Informationen zu diesem Parameter finden Sie unter [Report.cfg-Parameter](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Um einen Bericht mit einer Vorlage zu erstellen, die für einen Bericht spezifisch ist, müssen Sie der Excel-Datei denselben Namen geben wie der Bericht-Arbeitsbereich ( [!DNL .vw]) und dann die Vorlagendatei in demselben Ordner wie die Berichtsarbeitsdatei ( [!DNL .vw]) ablegen.

Wenn der Bericht erstellt wird, werden die vorhandenen Registerkarten in der Vorlage (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Bericht repliziert, während alle neuen Fenster, die nicht in der Vorlage als Tabellenblätter vorhanden sind, ignoriert werden. Alle anderen Registerkarten in der Vorlagendatei bleiben unverändert.

Wenn in der Excel-Vorlagendatei ein Makro definiert ist, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;ein.
