---
description: Wenn Sie einen der Datendienste abonnieren, müssen Sie die von Adobe bereitgestellten Datendienstdateien regelmäßig aktualisieren.
title: Aktualisieren von Daten-Service-Dateien
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Aktualisieren von Daten-Service-Dateien{#updating-data-service-files}

{{eol}}

Wenn Sie einen der Datendienste abonnieren, müssen Sie die von Adobe bereitgestellten Datendienstdateien regelmäßig aktualisieren.

Dazu müssen Sie Zugriff auf die Dateien auf dem Data Workbench-Server haben.

Zum Laden [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] -Datendateien, müssen Sie die folgenden Schritte ausführen.

## Ersetzen der Datendatei {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. In Data Workbench auf der [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht zum Öffnen der [!DNL Servers Manager] Arbeitsbereich.

1. Innerhalb der [!DNL Servers Manager] klicken Sie mit der rechten Maustaste auf das Symbol des Data Workbench-Servers, auf den Sie die Dateien laden möchten, und klicken Sie auf **[!UICONTROL Server Files]**.

1. Im [!DNL Server Files Manager], klicken Sie mit der rechten Maustaste in die **[!UICONTROL Temp]** Spalte für **[!UICONTROL Lookups\IP Geo-location]** oder **[!UICONTROL Lookups\IP Geo-intelligence]** und klicken Sie auf **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopieren Sie die [!DNL .bin] Datendatei, die von der Adobe zum Fenster Suchen\IP-Geostandort oder Suchen\IP-Geo-Intelligence-Ordnerfenster bereitgestellt wird.
1. Speichern Sie die Datei auf dem Computer des Data Workbench-Servers, indem Sie mit der rechten Maustaste auf das [!DNL Temp] Spalte für die Datendatei und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Wenn Sie einen Cluster ausführen, laden Sie die Dateien auf den Übergeordneten Data Workbench-Server im Cluster hoch.

## IPLookup-Transformation aktualisieren {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Im [!DNL Profile Manager]klicken **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** und **[!UICONTROL Geography]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL IP Lookup.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

1. Klicken Sie mit der rechten Maustaste auf das neue Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Ein Konfigurationsfenster für die Transformation wird angezeigt.

1. Klicken Sie im Fenster auf **[!UICONTROL Transformation]** Klicken Sie auf **[!UICONTROL Transformations]**.

1. Suchen Sie nach und klicken Sie auf **[!UICONTROL IPLookup Quova]** oder **[!UICONTROL IPLookup Digital Envoy]**.

1. Aktualisieren Sie für den Parameter &quot;File&quot;den Namen der Datei, sodass er mit dem Namen der neuen Daten übereinstimmt ( [!DNL .bin]) von Adobe bereitgestellt.
1. Speichern Sie die Konfigurationsdatei für die Umwandlung, indem Sie mit der rechten Maustaste darauf klicken. **[!UICONTROL (modified)]** oben im Konfigurationsfenster und klicken Sie auf **[!UICONTROL Save]**.

1. Speichern Sie die geänderte Konfigurationsdatei in jedem Profil, das den Datendienst verwendet, indem Sie mit der rechten Maustaste auf das Häkchen neben [!DNL IP Lookup.cfg] im [!DNL User] Spalte und Klicken **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. Die erneute Umwandlung der Daten beginnt nach der Synchronisierung des Datensatzprofils.

   Weitere Informationen zur Neuumwandlung Ihres Datensatzes finden Sie im Kapitel Wiederaufbereitung und erneute Umwandlung des *Anleitung zur Datensatzkonfiguration*.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile (einschließlich der Variablen [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] Profil), da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

Wenn Sie die [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] -Datendienst für Version 5.1 oder höher, haben Sie die Aktualisierung des Datendienstes abgeschlossen. Wenn Sie jedoch die [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] -Datendienst vor Version 5.1, müssen Sie die folgenden zusätzlichen Verfahren ausführen.

## Ersetzen der Lookup-Datei {#section-ced1efa38a76419d812edd35423dbff7}

Sie sollten die folgenden Schritte nur ausführen, wenn Sie die [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] Datendienst vor Version 5.1.

1. Im [!DNL Server Files Manager]Klicken Sie auf **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** oder **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** Klicken Sie auf **[!UICONTROL Maps]** , um den Inhalt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Temp]** Spalte für **[!UICONTROL Maps]** und klicken Sie auf **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Neue kopieren [!DNL .txt] -Datei, die von der Adobe zum Maps-Ordnerfenster bereitgestellt wird.
1. Speichern Sie die Datei auf dem Computer des Data Workbench-Servers, indem Sie mit der rechten Maustaste auf das Häkchen im [!DNL Temp] Spalte für [!DNL .txt] Datei und Klicken auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Wenn Sie einen Cluster ausführen, laden Sie die Dateien auf den Übergeordneten Data Workbench-Server im Cluster hoch.

## Aktualisieren der Ebenendateien {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Sie sollten die folgenden Schritte nur ausführen, wenn Sie die [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] Datendienst vor Version 5.1.

Führen Sie diese Schritte für jede Ebene aus ( [!DNL .layer]), die auf die [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] Nachschlagen ( [!DNL .txt]).

1. Öffnen Sie im Ordner Profile\*data service name*\Maps im Installationsordner des Data Workbench-Servers den Ordner [!DNL .layer] in einem Texteditor wie Notepad.

1. Im [!DNL Data Paths] vektor, den Namen des [!DNL .txt] Lookup-Datei, die dem Namen der neuen [!DNL .txt] -Datei, die von Adobe bereitgestellt wird, wie im folgenden Dateibeispiel hervorgehoben:

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
1. Wiederholen Sie die Schritte 2 und 3 für jede [!DNL .layer] -Datei, die auf die [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] [!DNL .txt] -Datei.
