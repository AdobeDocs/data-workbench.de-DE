---
description: Sie können einfach eine Segmentexportdefinition aus der Detailtabellenvisualisierung im Data Workbench-Client erstellen.
solution: Analytics
title: Segmentexport
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segmentexport{#segment-export}

Sie können einfach eine Segmentexportdefinition aus der Detailtabellenvisualisierung im Data Workbench-Client erstellen.

Darüber hinaus können die Ergebnisse [!DNL Segment Exports] automatisch zu einem einzelnen Server kombiniert werden, anstatt für jede DPU, die Sie mit einem externen Prozess kombinieren müssen, partielle Ergebnisse zu erzielen. Sie können eine Segmentexportdatei erstellen, in der Datei speichern [!DNL Profile Manager]und die Ausgabedatei auf einen Server Ihrer Wahl hochladen.

**So konfigurieren Sie den Segmentexportserver**

Die [!DNL Segment Export] Funktion erstellt eine einzelne Ausgabedatei auf dem Segmentexportserver und keine separaten Ausgabedateien, die auf jeder DPU erstellt werden. Der Segmentexportserver ist für gewöhnlich für die Ausführung auf der FSU konfiguriert.

Öffnen Sie im Ordner &quot;DataSet\&quot;im Ordner [!DNL Profile Manager]den Ordner [!DNL Segment Export.cfg] &quot;Workstation&quot;und geben Sie die Adresse des Servers an. (Ihre Adresse kann eine IP oder ein vollständig qualifizierter Domänenname sein.)

![](assets/segment_export_cfg.png)

Dies ist die IP des Data Workbench-Servers, der die Ergebnisse des Segmentexports erhält. Dies ist ein einmaliges Setup. Wenn das [!DNL Segment Export.cfg] nicht vorhanden ist, werden die Exporte nicht ausgeführt.

**So konfigurieren Sie Exportordner**

Aus Sicherheitsgründen müssen sich ausführbare Dateien oder Stapeldateien, die nach einem Segmentexport ausgeführt werden, im konfigurierbaren Scripts\-Ordner des Segmentexportservers befinden.

Die [!DNL .part] und die endgültige Ausgabe müssen sich im konfigurierbaren Exportverzeichnis befinden. Der auszuführende Befehl ist in Command Arguments vorhanden. Instanzen von %file% in den Befehlsargumenten werden durch den Pfad der Ausgabedatei ersetzt.

>[!NOTE]
>
>Neu bei Data Workbench 5.4 wird der Ordner \Export automatisch erstellt. Für die vorherigen Exportordner, die vor Version 5.4 eingerichtet wurden, war vor dem Dateinamen für jeden Segmentexport ein Präfix &quot;Exporte\&quot;erforderlich. Das Hinzufügen dieses Präfix ist jetzt überflüssig.

1. Fügen Sie [!DNL Communications.cfg] auf dem Zielserver für [!DNL Segment Exports]einen SegmentExportServer zur Liste der Server hinzu. (Beispiel rot).

   ![](assets/communications_cfg_example.png)

   Exportverzeichnis: Gibt an, wo Dateien abgelegt [!DNL .part] und ausgegeben werden sollen. Dies kann ein freigegebener Ordner sein.

   Skriptverzeichnis: Gibt den Ordner an, aus dem alle ausführbaren Dateien oder Stapeldateien ausgeführt werden.

1. [!DNL Access Control.cfg], fügen Sie auf demselben Server dem Cluster Servers AccessGroup Lese-Schreibzugriff auf den URI /SegmentExportServer/ hinzu:

   ![](assets/accesscontrol_cfg_example.png)

1. Ändern Sie Ihre [!DNL .export] Dateien:

   ![](assets/segment_export_query_example.png)

1. Für jedes Profil [!DNL Segment Export.cfg] befindet sich der Ordner &quot;DataSet\&quot;mit folgendem Inhalt:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Stellen Sie sicher, dass die Ordner, auf die im Exportverzeichnis und im Skriptverzeichnis verwiesen wird, vorhanden sind.

   Als Befehl zum Segmentexport können nur ausführbare Dateien und Stapeldateien im Skriptordner ausgeführt werden.

**So erstellen Sie eine Segmentexportdatei**

1. Erstellen Sie in einem Arbeitsbereich eine Detailtabelle mit Teildatensätzen (Visualisierung > Detailtabelle) und fügen Sie Attribute hinzu.
1. Treffen Sie bei Bedarf eine Auswahl im Arbeitsbereich. (Alle Auswahlen oder Filter werden auf den Export angewendet.)

   ![](assets/create_segment_export_file.png)

1. Klicken Sie in der Kopfzeile der Detailtabelle mit der rechten Maustaste und wählen Sie **[!UICONTROL Create Segment Export File]**.
1. Geben Sie [!DNL Save as]einen Namen für die [!DNL .export] Datei ein.
1. Konfigurieren Sie die Parameter in der [!DNL .export] Datei nach Bedarf.

   Alle Auswahlen oder Filter im Arbeitsbereich werden in die Exportdatei aufgenommen.

1. Save the [!DNL .export] file.

   Die gespeicherte Datei wird in der angezeigt, [!DNL Profile Manager] damit Sie sie auf dem Server speichern können. Wenn Sie die Datei auf dem Server speichern, beginnt der Export.

