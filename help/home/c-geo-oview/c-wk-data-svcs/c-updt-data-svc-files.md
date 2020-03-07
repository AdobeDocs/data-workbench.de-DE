---
description: Wenn Sie einen der Datendienste abonnieren, müssen Sie die von Adobe bereitgestellten Datendienstdateien in regelmäßigen Abständen aktualisieren.
solution: Analytics
title: Aktualisieren von Datendienstdateien
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aktualisieren von Datendienstdateien{#updating-data-service-files}

Wenn Sie einen der Datendienste abonnieren, müssen Sie die von Adobe bereitgestellten Datendienstdateien in regelmäßigen Abständen aktualisieren.

Dazu müssen Sie Zugriff auf die Dateien auf dem Data Workbench-Server haben.

Zum Laden [!DNL IP Geo-location] oder Laden von [!DNL IP Geo-intelligence] Datendateien müssen Sie die folgenden Schritte ausführen.

## Datendatei ersetzen {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Klicken Sie in Data Workbench auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den [!DNL Servers Manager] Arbeitsbereich zu öffnen.

1. Klicken Sie im [!DNL Servers Manager] Fenster mit der rechten Maustaste auf das Symbol des Data Workbench-Servers, auf den Sie die Dateien laden möchten, und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie im [!DNL Server Files Manager]Kontextmenü mit der rechten Maustaste in die **[!UICONTROL Temp]** Spalte für **[!UICONTROL Lookups\IP Geo-location]** oder **[!UICONTROL Lookups\IP Geo-intelligence]** und klicken Sie auf **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopieren Sie die von Adobe bereitgestellte [!DNL .bin] Datendatei in das Ordnerfenster Suchen\IP Geo-Position oder Suchen\IP Geo-Intelligence.
1. Speichern Sie die Datei auf dem Computer des Data Workbench-Servers, indem Sie mit der rechten Maustaste auf die [!DNL Temp] Spalte für die Datendatei klicken und auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* klicken.

   Wenn Sie einen Cluster ausführen, laden Sie die Dateien auf den Master-Data Workbench-Server im Cluster hoch.

## IPLookup-Transformation aktualisieren {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Klicken Sie im [!DNL Profile Manager]Fenster auf **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** und **[!UICONTROL Geography]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL IP Lookup.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neue Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Es wird ein Fenster zur Konvertierungskonfiguration angezeigt.

1. Klicken Sie im Fenster auf **[!UICONTROL Transformation]** und dann auf **[!UICONTROL Transformations]**.

1. Suchen Sie nach einem **[!UICONTROL IPLookup Quova]** oder **[!UICONTROL IPLookup Digital Envoy]** klicken Sie darauf.

1. Aktualisieren Sie für den Parameter &quot;Datei&quot;den Namen der Datei so, dass er mit dem Namen der von Adobe bereitgestellten neuen Datendatei ( [!DNL .bin]) übereinstimmt.
1. Speichern Sie die Konvertierungskonfigurationsdatei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Konfigurationsfenster auf klicken **[!UICONTROL Save]**.

1. Speichern Sie die geänderte Konfigurationsdatei in jedem Profil, das den Datendienst verwendet, indem Sie mit der rechten Maustaste auf das Häkchen neben [!DNL IP Lookup.cfg] der [!DNL User] Spalte klicken und auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* klicken. Die Datenumwandlung beginnt nach der Synchronisierung des Datensatzprofils.

   Weitere Informationen zur Umgestaltung des Datensatzes finden Sie im Kapitel &quot;Verarbeitung und Umformung&quot;im Handbuch zur *Datenkonfiguration*.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich des Profils [!DNL IP Geo-location] [!DNL IP Geo-intelligence] oder des Profils), da Ihre Änderungen überschrieben werden, wenn Sie Updates für diese Profile installieren.

Wenn Sie den Datendienst [!DNL IP Geo-intelligence] und den [!DNL IP Geo-location] Datendienst für Version 5.1 oder höher installiert haben, haben Sie die Aktualisierung des Datendienstes abgeschlossen. Wenn Sie jedoch den [!DNL IP Geo-intelligence] und den [!DNL IP Geo-location] Datendienst vor Version 5.1 installiert haben, müssen Sie die folgenden zusätzlichen Verfahren durchführen.

## Ersetzen der Suchdatei {#section-ced1efa38a76419d812edd35423dbff7}

Führen Sie die folgenden Schritte nur aus, wenn Sie den [!DNL IP Geo-intelligence] und den [!DNL IP Geo-location] Datendienst vor Version 5.1 installiert haben.

1. Klicken Sie im [!DNL Server Files Manager]Fenster auf entweder **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** oder **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, und klicken Sie dann auf **[!UICONTROL Maps]** , um den Inhalt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste in die **[!UICONTROL Temp]** Spalte für **[!UICONTROL Maps]** und klicken Sie auf **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopieren Sie die von Adobe bereitgestellte neue [!DNL .txt] Datei in das Ordnerfenster &quot;Maps&quot;.
1. Speichern Sie die Datei auf dem Computer des Data Workbench-Servers, indem Sie mit der rechten Maustaste auf das Häkchen in der [!DNL Temp] Spalte für die [!DNL .txt] Datei klicken und auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* klicken.

>[!NOTE]
>
>Wenn Sie einen Cluster ausführen, laden Sie die Dateien auf den Master-Data Workbench-Server im Cluster hoch.

## Aktualisieren der Ebenendateien {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Führen Sie die folgenden Schritte nur aus, wenn Sie den [!DNL IP Geo-intelligence] und den [!DNL IP Geo-location] Datendienst vor Version 5.1 installiert haben.

Führen Sie diese Schritte für jede Ebene ( [!DNL .layer])-Datei aus, die auf die [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] Lookup-Datei verweist ( [!DNL .txt]).

1. Öffnen Sie die Datei im Ordner &quot;Profiles\*data service name*\Maps&quot;im Installationsordner des Data Workbench-Servers in einem Texteditor wie Notepad. [!DNL .layer]

1. Aktualisieren Sie im [!DNL Data Paths] Vektor den Namen der [!DNL .txt] Lookup-Datei so, dass er dem Namen der von Adobe bereitgestellten neuen [!DNL .txt] Datei entspricht, wie im folgenden Dateimuster dargestellt:

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Speichern Sie die aktualisierte Ebenendatei.
1. Wiederholen Sie die Schritte 2 und 3 für jede [!DNL .layer] Datei, die auf die [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] [!DNL .txt] Datei verweist.

