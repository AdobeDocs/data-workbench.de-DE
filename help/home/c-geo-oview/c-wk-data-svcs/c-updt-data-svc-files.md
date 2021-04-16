---
description: Wenn Sie einen der Datendienste abonnieren, müssen Sie die von der Adobe bereitgestellten Datendienstdateien in regelmäßigen Abständen aktualisieren.
title: Aktualisieren von Daten-Service-Dateien
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Aktualisieren von Daten-Service-Dateien{#updating-data-service-files}

Wenn Sie einen der Datendienste abonnieren, müssen Sie die von der Adobe bereitgestellten Datendienstdateien in regelmäßigen Abständen aktualisieren.

Dazu müssen Sie Zugriff auf die Dateien auf dem Data Workbench-Server haben.

Zum Laden der Datendateien [!DNL IP Geo-location] oder [!DNL IP Geo-intelligence] müssen Sie die folgenden Schritte ausführen.

## Ersetzen der Datendatei {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Klicken Sie in Data Workbench auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht von **[!UICONTROL Servers Manager]**, um den Arbeitsbereich [!DNL Servers Manager] zu öffnen.

1. Klicken Sie im Fenster [!DNL Servers Manager] mit der rechten Maustaste auf das Symbol des Data Workbench-Servers, auf den Sie die Dateien laden möchten, und klicken Sie auf **[!UICONTROL Server Files]**.

1. Klicken Sie in [!DNL Server Files Manager] mit der rechten Maustaste in die Spalte **[!UICONTROL Temp]** für **[!UICONTROL Lookups\IP Geo-location]** oder **[!UICONTROL Lookups\IP Geo-intelligence]** und klicken Sie auf **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Kopieren Sie die von der Adobe bereitgestellte Datendatei [!DNL .bin] in das Fenster Suchen\IP Geo-Position oder Suchen\IP Geo-Intelligence.
1. Speichern Sie die Datei auf dem Computer des Data Workbench-Servers, indem Sie mit der rechten Maustaste auf die Spalte [!DNL Temp] für die Datendatei klicken und auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]*** klicken.

   Wenn Sie einen Cluster ausführen, laden Sie die Dateien auf den Übergeordnet Data Workbench-Server im Cluster hoch.

## IPLookup Transformation {#section-a8b99afe3eb04afabe88e15bd465f935} aktualisieren

1. Klicken Sie in [!DNL Profile Manager] auf **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** und **[!UICONTROL Geography]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL IP Lookup.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neue Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Es wird ein Fenster zur Konvertierungskonfiguration angezeigt.

1. Klicken Sie im Fenster auf **[!UICONTROL Transformation]** und dann auf **[!UICONTROL Transformations]**.

1. Klicken Sie auf **[!UICONTROL IPLookup Quova]** oder **[!UICONTROL IPLookup Digital Envoy]**.

1. Aktualisieren Sie den Dateinamen für den Dateiparameter so, dass er mit dem Dateinamen der von der Adobe bereitgestellten neuen Datendatei ( [!DNL .bin]) übereinstimmt.
1. Speichern Sie die Konvertierungskonfigurationsdatei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Konfigurationsfenster klicken und auf **[!UICONTROL Save]** klicken.

1. Speichern Sie die geänderte Konfigurationsdatei in jedem Profil, das den Datendienst verwendet, indem Sie mit der rechten Maustaste auf das Häkchen neben [!DNL IP Lookup.cfg] in der Spalte [!DNL User] klicken und dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]*** klicken. Die Datenumwandlung beginnt nach der Synchronisierung des DataSet-Profils.

   Weitere Informationen zur Umgestaltung Ihres Datensatzes finden Sie im Kapitel &quot;Verarbeitung und Umformung&quot;des Handbuchs *Konfiguration des Datensatzes*.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil (einschließlich des [!DNL IP Geo-location]- oder [!DNL IP Geo-intelligence]-Profils), da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

Wenn Sie den Datendienst [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] für Version 5.1 oder höher installiert haben, haben Sie die Aktualisierung des Datendienstes abgeschlossen. Wenn Sie jedoch den Datendienst [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] vor Version 5.1 installiert haben, müssen Sie die folgenden zusätzlichen Verfahren durchführen.

## Ersetzen der Suchdatei {#section-ced1efa38a76419d812edd35423dbff7}

Führen Sie die folgenden Schritte nur aus, wenn Sie den Datendienst [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] vor Version 5.1 installiert haben.

1. Klicken Sie in [!DNL Server Files Manager] entweder auf **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** oder **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** und klicken Sie dann auf **[!UICONTROL Maps]**, um den Inhalt Ansicht.

1. Klicken Sie mit der rechten Maustaste in die Spalte **[!UICONTROL Temp]** für **[!UICONTROL Maps]** und klicken Sie auf **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Kopieren Sie die von der Adobe bereitgestellte neue [!DNL .txt]-Datei in das Ordnerfenster &quot;Maps&quot;.
1. Speichern Sie die Datei auf dem Computer des Data Workbench-Servers, indem Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL Temp] für die Datei [!DNL .txt] klicken und auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]*** klicken.

>[!NOTE]
>
>Wenn Sie einen Cluster ausführen, laden Sie die Dateien auf den Übergeordnet Data Workbench-Server im Cluster hoch.

## Aktualisieren der Ebenendateien {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Führen Sie die folgenden Schritte nur aus, wenn Sie den Datendienst [!DNL IP Geo-intelligence] und [!DNL IP Geo-location] vor Version 5.1 installiert haben.

Führen Sie diese Schritte für jede Ebene ( [!DNL .layer])-Datei aus, die auf die [!DNL IP Geo-intelligence]- oder [!DNL IP Geo-location]-Nachschlagedatei ( [!DNL .txt]) verweist.

1. Öffnen Sie im Ordner &quot;Profils\*data service name*\Maps&quot;des Installationsordners des Data Workbench-Servers die Datei [!DNL .layer] in einem Texteditor wie Notepad.

1. Aktualisieren Sie im Vektor [!DNL Data Paths] den Namen der [!DNL .txt]-Nachschlagedatei, damit er mit dem Namen der neuen [!DNL .txt]-Adobe übereinstimmt, wie im folgenden Dateibeispiel dargestellt:

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
1. Wiederholen Sie die Schritte 2 und 3 für jede [!DNL .layer]-Datei, die auf die [!DNL IP Geo-intelligence]- oder [!DNL IP Geo-location] [!DNL .txt]-Datei verweist.
