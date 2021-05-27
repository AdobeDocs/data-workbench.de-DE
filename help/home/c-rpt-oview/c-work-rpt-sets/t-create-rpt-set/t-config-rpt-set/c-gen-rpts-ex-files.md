---
description: Informationen zum Generieren von Berichten als Excel-Dateien.
title: Erstellen von Berichten als Microsoft Excel-Dateien
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 4%

---

# Erstellen von Berichten als Microsoft Excel-Dateien{#generating-reports-as-microsoft-excel-files}

Informationen zum Generieren von Berichten als Excel-Dateien.

Die folgenden Anforderungen müssen erfüllt sein:

* Microsoft Excel muss auf demselben Computer installiert sein wie [!DNL Report Server].
* Das Benutzerkonto, unter dem der [!DNL Report Server]-Prozess ausgeführt wird, muss über Berechtigungen für den Zugriff auf Microsoft Excel verfügen.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Wenn Sie Berichte als Excel-Dateien generieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Prozess finden Sie unter [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
   >    * Obwohl Data Workbench mehr als 256 Spalten und 65.536 Zeilen mit Daten unterstützt, unterstützt Microsoft Excel dies nicht.


Wenn diese Anforderungen erfüllt sind, startet [!DNL Report Server] automatisch Microsoft Excel und gibt Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen aus einer neuen Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt aus.

>[!NOTE]
>
>Daten werden nicht aus Diagrammen, Pfadbrowsern, Prozesskarten, Streudiagrammen und Globen exportiert.

Sofern Sie für die Visualisierung kein [!DNL Custom Title] angegeben haben, wird der Typ des Fensters (z. B. Filmtabelle) als Arbeitsblattname verwendet.

Weitere Informationen zum Festlegen von [!DNL Custom Titles] für Visualisierungen finden Sie im [Data Workbench Client Guide](https://docs.adobe.com/content/help/de-DE/data-workbench/using/client/t-open-ins.html).

## Verwenden einer Vorlagendatei {#section-40ab11916f464b1a88214ab969da6751}

Sie können einen Bericht auch als Excel-Datei mithilfe einer Excel-Vorlagendatei ( [!DNL .xls] oder [!DNL .xlsx]) erstellen. Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie mit der Formatierung Ihrer Daten bei jeder Berichterstellung verbringen.

Diese Vorlagendatei muss eine [!DNL .xls]- oder [!DNL .xlsx]-Datei sein, keine [!DNL .xlt]-Datei.

Sie können eine Vorlage für jeden einzelnen Bericht, eine generische Vorlage für alle Berichte oder eine Kombination aus beidem definieren. Da sich diese beiden Elemente nicht gegenseitig ausschließen, können Sie eine generische Vorlage definieren und anschließend spezifische Vorlagen definieren.

Um einen Bericht mit einer generischen Vorlage zu erstellen, die Sie für alle Berichte verwenden, müssen Sie den Namen dieser Excel-Datei im Parameter Excel-Standardvorlage im [!DNL Report.cfg] für diese Berichtsset-Datei angeben und dann die Vorlagendatei im selben Ordner ablegen wie das [!DNL Report.cfg] für diesen Berichtssatz (*Installationsordner der Data Workbench*\*Profilname*\Reports\*ReportSetName*). Weitere Informationen zu diesem Parameter finden Sie unter [Report.cfg-Parameter](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Um einen Bericht mit einer für einen Bericht spezifischen Vorlage zu erstellen, müssen Sie die Excel-Datei mit der Report Workspace-Datei ( [!DNL .vw]) benennen und die Vorlagendatei dann im selben Ordner wie die Report Workspace-Datei ( [!DNL .vw]) ablegen.

Wenn der Bericht generiert wird, werden die vorhandenen Tabellenblätter mit Registerkarten in der Vorlage (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Bericht repliziert, während alle neuen Fenster, die nicht in der Vorlage als Tabellenblätter vorhanden sind, ignoriert werden. Alle anderen Tabellenblätter in der Vorlagendatei bleiben unverändert.

Wenn Sie außerdem ein Makro in der Excel-Vorlagendatei definiert haben, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;.
