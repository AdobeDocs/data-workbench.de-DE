---
description: Sie können einfach eine Segmentexportdefinition aus der Detailtabellenvisualisierung im Data Workbench Client erstellen.
title: Segmentexport
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Segmentexport{#segment-export}

{{eol}}

Sie können einfach eine Segmentexportdefinition aus der Detailtabellenvisualisierung im Data Workbench Client erstellen.

Darüber hinaus [!DNL Segment Exports] die Ergebnisse werden automatisch zu einem einzelnen Server kombiniert, anstatt für jede DPU partielle Ergebnisse zu erzeugen, die Sie mithilfe eines externen Prozesses kombinieren müssen. Sie können eine Segmentexportdatei erstellen und in der [!DNL Profile Manager]und laden Sie die Ausgabedatei auf einen Server Ihrer Wahl hoch.

**So konfigurieren Sie den Segmentexportserver**

Die [!DNL Segment Export] -Funktion eine einzelne Ausgabedatei auf dem Segmentexportserver erstellt, anstatt für jede DPU separate Ausgabedateien zu erstellen. Der Segmentexportserver ist für gewöhnlich so konfiguriert, dass er auf der FSU ausgeführt wird.

Im Ordner Datensatz\ im [!DNL Profile Manager], öffnen Sie die [!DNL Segment Export.cfg] und geben Sie die Adresse Ihres Servers an. (Ihre Adresse kann eine IP-Adresse oder ein vollständig qualifizierter Domänenname sein.):

![](assets/segment_export_cfg.png)

Dies ist die IP des Data Workbench-Servers, der die Ergebnisse des Segmentexports erhält. Dies ist eine einmalige Einrichtung. Wenn die Variable [!DNL Segment Export.cfg] nicht vorhanden ist, werden die Exporte nicht ausgeführt.

**So konfigurieren Sie Exportverzeichnisse**

Aus Sicherheitsgründen müssen sich ausführbare Dateien oder Batch-Dateien, die nach einem Segmentexport ausgeführt werden, im konfigurierbaren Ordner Scripts\ des Segmentexportservers befinden.

Die [!DNL .part] und die endgültige Ausgabe muss sich im konfigurierbaren Verzeichnis &quot;Exporte&quot;befinden. Der auszuführende Befehl ist in den Befehls- und Befehlsargumenten vorhanden. Instanzen von %file% in den Befehlsargumenten werden durch den Pfad der Ausgabedatei ersetzt.

>[!NOTE]
>
>Neu in Data Workbench 5.4 ist, dass der Ordner \Exporte automatisch erstellt wird. Vorherige Exportverzeichnisse, die vor Version 5.4 eingerichtet wurden, erforderten für jeden Segmentexport ein Präfix Exporte\ vor dem Dateinamen. Das Hinzufügen dieses Präfixes ist jetzt redundant.

1. In [!DNL Communications.cfg] auf dem Zielserver für [!DNL Segment Exports], fügen Sie einen SegmentExportServer zur Liste der Server hinzu. (Beispiel in rot).

   ![](assets/communications_cfg_example.png)

   Exportverzeichnis: Gibt an, wo abgelegt werden soll [!DNL .part] und Ausgabedateien. Dies kann ein freigegebener Ordner sein.

   Skriptverzeichnis: Gibt den Ordner an, aus dem alle ausführbaren Dateien oder Batch-Dateien ausgeführt werden.

1. [!DNL Access Control.cfg]Fügen Sie auf demselben Server Lese- und Schreibzugriff auf den URI /SegmentExportServer/ zur Zugriffsgruppe für Cluster-Server hinzu:

   ![](assets/accesscontrol_cfg_example.png)

1. Ändern Sie Ihre [!DNL .export] -Dateien:

   ![](assets/segment_export_query_example.png)

1. Für jedes Profil wird die [!DNL Segment Export.cfg] befindet sich im Ordner Datensatz\ mit folgendem Inhalt:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Stellen Sie sicher, dass die Ordner, auf die in &quot;Verzeichnis exportieren&quot;und &quot;Skriptverzeichnis&quot;verwiesen wird, vorhanden sind.

   Nur ausführbare Dateien und Batch-Dateien im Skriptverzeichnis können als Befehl zum Segmentexport ausgeführt werden.

**So erstellen Sie eine Segmentexportdatei**

1. Erstellen Sie in einem Arbeitsbereich eine Detailtabelle mit Teilmengen von Daten (Visualisierung > Detailtabelle) und fügen Sie Attribute hinzu.
1. Treffen Sie bei Bedarf eine Auswahl im Arbeitsbereich. (Alle Auswahlen oder Filter werden auf den Export angewendet.)

   ![](assets/create_segment_export_file.png)

1. Klicken Sie in der Kopfzeile der Detailtabelle mit der rechten Maustaste und wählen Sie **[!UICONTROL Create Segment Export File]**.
1. In [!DNL Save as], geben Sie einen Namen für die [!DNL .export] -Datei.
1. Im [!DNL .export] -Datei, konfigurieren Sie die Parameter nach Bedarf.

   Alle Auswahlen oder Filter im Arbeitsbereich werden in die Exportdatei eingefügt.

1. Speichern Sie die [!DNL .export] -Datei.

   Die gespeicherte Datei wird im [!DNL Profile Manager] , damit Sie auf dem Server speichern können. Wenn Sie die Datei auf dem Server speichern, beginnt der Export.
