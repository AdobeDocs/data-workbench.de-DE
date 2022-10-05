---
description: Informationen zum Generieren von Berichten als Excel-Dateien.
title: Erstellen von Berichten als Microsoft Excel-Dateien
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 4%

---

# Erstellen von Berichten als Microsoft Excel-Dateien{#generating-reports-as-microsoft-excel-files}

{{eol}}

Informationen zum Generieren von Berichten als Excel-Dateien.

Die folgenden Anforderungen müssen erfüllt sein:

* Microsoft Excel muss auf demselben Computer installiert sein wie [!DNL Report Server].
* Das Benutzerkonto, unter dem die [!DNL Report Server] Prozess wird ausgeführt muss über die Berechtigung für den Zugriff auf Microsoft Excel verfügen.

   >[!NOTE]
   >
   >
   >
   >
   >    * Wenn Sie Berichte als Excel-Dateien generieren, öffnen Sie eine neue Instanz von Excel. Weitere Informationen zu diesem Prozess finden Sie unter [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Obwohl Data Workbench mehr als 256 Spalten und 65.536 Datenzeilen unterstützt, ist dies in Microsoft Excel nicht der Fall.


Wenn diese Anforderungen erfüllt sind, [!DNL Report Server] startet Microsoft Excel automatisch und gibt Daten aus bestimmten Visualisierungen, Dimensions- und Wertlegenden sowie Textanmerkungen in eine neue Excel-Arbeitsmappe mit einer Visualisierung pro Arbeitsblatt aus.

>[!NOTE]
>
>Daten werden nicht aus Diagrammen, Pfadbrowsern, Prozesskarten, Streudiagrammen und Globen exportiert.

Wenn Sie nicht eine [!DNL Custom Title] für die Visualisierung wird der Typ des Fensters (z. B. Filmtabelle) als Arbeitsblattname verwendet.

Weitere Informationen zum [!DNL Custom Titles] Informationen zu Visualisierungen finden Sie unter [Data Workbench Client-Handbuch](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=de).

## Verwenden einer Vorlagendatei {#section-40ab11916f464b1a88214ab969da6751}

Sie können einen Bericht auch als Excel-Datei mithilfe einer Excel-Vorlage erstellen ( [!DNL .xls] oder [!DNL .xlsx]). Die Verwendung einer Vorlagendatei kann die Zeit verringern, die Sie mit der Formatierung Ihrer Daten bei jeder Berichterstellung verbringen.

Diese Vorlagendatei muss ein [!DNL .xls] oder [!DNL .xlsx] nicht [!DNL .xlt] -Datei.

Sie können eine Vorlage für jeden einzelnen Bericht, eine generische Vorlage für alle Berichte oder eine Kombination aus beidem definieren. Da sich diese beiden Elemente nicht gegenseitig ausschließen, können Sie eine generische Vorlage definieren und anschließend spezifische Vorlagen definieren.

Um einen Bericht mit einer generischen Vorlage zu erstellen, die Sie für alle Berichte verwenden, müssen Sie den Namen dieser Excel-Datei im Parameter Excel-Standardvorlage im [!DNL Report.cfg] für diese Berichtssatzdatei und legen Sie dann die Vorlagendatei im selben Ordner ab wie die [!DNL Report.cfg] für diesen Berichtssatz (*Installationsordner von Data Workbench*\*Profilname*\Berichte\*ReportSetName*). Weitere Informationen zu diesem Parameter finden Sie unter [Parameter &quot;Report.cfg&quot;](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Um einen Bericht mit einer berichtsspezifischen Vorlage zu erstellen, müssen Sie die Excel-Datei mit dem Report Workspace ( [!DNL .vw]) und platzieren Sie dann die Vorlagendatei im selben Ordner wie den Berichtsarbeitsbereich ( [!DNL .vw]).

Wenn der Bericht generiert wird, werden die vorhandenen Tabellenblätter mit Registerkarten in der Vorlage (die jeweils eine Visualisierung darstellen) mit den neuesten Daten aus dem Bericht repliziert, während alle neuen Fenster, die nicht in der Vorlage als Tabellenblätter vorhanden sind, ignoriert werden. Alle anderen Tabellenblätter in der Vorlagendatei bleiben unverändert.

Wenn Sie außerdem ein Makro in der Excel-Vorlagendatei definiert haben, das Sie bei der Berichterstellung automatisch ausführen möchten, geben Sie dem Makro den Namen &quot;VSExport&quot;.
