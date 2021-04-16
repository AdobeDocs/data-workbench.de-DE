---
description: Sie können eine Segmentexportdefinition einfach aus der Detailtabellenvisualisierung im Data Workbench Client erstellen.
title: Segmentexport
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Segmentexport{#segment-export}

Sie können eine Segmentexportdefinition einfach aus der Detailtabellenvisualisierung im Data Workbench Client erstellen.

Darüber hinaus werden die Ergebnisse von [!DNL Segment Exports] automatisch zu einem einzelnen Server kombiniert, anstatt partielle Ergebnisse für jede DPU zu erzeugen, die Sie mit einem externen Prozess kombinieren müssen. Sie können eine Segmentexportdatei erstellen, sie im Ordner [!DNL Profile Manager] speichern und die Ausgabedatei auf einen Server Ihrer Wahl hochladen.

**So konfigurieren Sie den Segmentexportserver**

Mit der Funktion [!DNL Segment Export] wird auf dem Segmentexportserver eine einzelne Ausgabedatei statt separater Ausgabedateien erstellt, die auf jeder DPU erstellt werden. Der Segmentexportserver ist für gewöhnlich für die Ausführung auf der FSU konfiguriert.

Öffnen Sie im Ordner &quot;DataSet\&quot;in [!DNL Profile Manager] den Ordner [!DNL Segment Export.cfg] in Workstation und geben Sie die Adresse des Servers an. (Ihre Adresse kann eine IP oder ein vollständig qualifizierter Domänenname sein.)

![](assets/segment_export_cfg.png)

Dies ist die IP des Segmentservers, der die Ergebnisse des Segmentexports erhält. Dies ist ein einmaliges Setup. Wenn [!DNL Segment Export.cfg] nicht vorhanden ist, werden Exporte nicht ausgeführt.

**So konfigurieren Sie Exportordner**

Aus Sicherheitsgründen müssen sich ausführbare Dateien oder Stapeldateien, die nach einem Segmentexport ausgeführt werden, im konfigurierbaren Scripts\-Ordner des Segmentexportservers befinden.

Die [!DNL .part]- und die finale Ausgabe müssen sich im konfigurierbaren Exportverzeichnis befinden. Der auszuführende Befehl ist in Command Arguments vorhanden. Instanzen von %file% in den Befehlsargumenten werden durch den Pfad der Ausgabedatei ersetzt.

>[!NOTE]
>
>Neu in Data Workbench 5.4 wird der Ordner \Exporte automatisch erstellt. Für die vorherigen Exportordner, die vor Version 5.4 eingerichtet wurden, war vor dem Dateinamen für jeden Segmentexport ein Präfix &quot;Exporte\&quot;erforderlich. Das Hinzufügen dieses Präfix ist jetzt redundant.

1. Fügen Sie in [!DNL Communications.cfg] auf dem Zielserver für [!DNL Segment Exports] der Liste der Server einen SegmentExportServer hinzu. (Beispiel rot).

   ![](assets/communications_cfg_example.png)

   Exportverzeichnis: Gibt an, wo [!DNL .part]- und Ausgabedateien abgelegt werden sollen. Dies kann ein freigegebener Ordner sein.

   Skriptverzeichnis: Gibt den Ordner an, aus dem alle ausführbaren Dateien oder Stapeldateien ausgeführt werden.

1. [!DNL Access Control.cfg], fügen Sie auf demselben Server dem Cluster Servers AccessGroup Lese-Schreibzugriff auf den URI /SegmentExportServer/ hinzu:

   ![](assets/accesscontrol_cfg_example.png)

1. Ändern Sie die [!DNL .export]-Dateien:

   ![](assets/segment_export_query_example.png)

1. Für jedes Profil befindet sich das [!DNL Segment Export.cfg] im Ordner &quot;Dataset\&quot; mit folgendem Inhalt:

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
1. Geben Sie in [!DNL Save as] einen Namen für die Datei [!DNL .export] ein.
1. Konfigurieren Sie in der Datei [!DNL .export] die Parameter nach Bedarf.

   Alle Auswahlen oder Filter im Arbeitsbereich werden in die Exportdatei aufgenommen.

1. Speichern Sie die Datei [!DNL .export].

   Die gespeicherte Datei wird im Ordner [!DNL Profile Manager] angezeigt, damit Sie sie auf dem Server speichern können. Wenn Sie die Datei auf dem Server speichern, beginnt der Export.
