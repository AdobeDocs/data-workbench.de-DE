---
description: Das Projektionsformat "LatLonProjection"in der Datei "Terrain Images.cfg"wird durch vier Parameter für Längen- und Breitengrad definiert.
solution: Analytics
title: Breitengradprojektionen
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Breitengradprojektionen{#latitude-longitude-projections}

Das Projektionsformat &quot;LatLonProjection&quot;in der Datei &quot;Terrain Images.cfg&quot;wird durch vier Parameter für Längen- und Breitengrad definiert.

Um eine LatLonProjection für nicht projizierte Bilder (unprojizierte unprojizierte Bitmaps und allgemeine Bilder, nicht projiziert) anzugeben, können Sie die Einstellungen für LatLonProjection im [!DNL Terrain Images.cfg] Fenster in der Data Workbench eingeben. Siehe [So legen Sie eine LatLonProjection für nicht projizierte Bilder](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)fest.

Um für Bilder mit eingebetteten Projektionsinformationen eine LatLonProjection-Datei anzugeben, müssen Sie die [!DNL Terrain Images.cfg] Datei in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf &quot;LatLonProjection&quot;setzen und Einstellungen für LatLonProjection hinzufügen. Siehe [So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [So legen Sie eine LatLonProjection für nicht projizierte Bilder fest](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## So legen Sie eine LatLonProjection für nicht projizierte Bilder fest {#section-26554eefe645481faba68396fa13756a}

1. Öffnen Sie die [!DNL Terrain Images.cfg] Datei in der Data Workbench und fügen Sie eine Bodenbildschichtquelle hinzu, wie unter [So definieren Sie eine Terrain-Bildebene](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)beschrieben.

1. Bearbeiten Sie die Parameter für Projektinformationen mithilfe der folgenden Parametertabelle als Anleitung:

   | Parameter | Beschreibung |
   |---|---|
   | Lat0 | Die Breite der oberen Kante des Bildes in Grad, wobei 90 der Nordpol und -90 der Südpol ist. |
   | Lat1 | Die Breite der unteren Kante des Bilds. |
   | Lon0 | Der Längengrad der linken Kante des Bildes in Grad, wobei positive Zahlen östlich und negative Zahlen westliche Längen sind. |
   | Lon1 | Der Längengrad der rechten Kante des Bilds. |

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters klicken und auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen am Data Workbench-Server zu speichern, klicken Sie mit der rechten Maustaste auf das [!DNL Server Files Manager]Häkchen für [!DNL Terrain Images.cfg] die [!DNL Temp] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] Datei befindet sich in diesem Ordner.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Terrain Images.cfg]und klicken Sie dann auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Terrain Images.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL Terrain Images.cfg] Datei wird in einem Editor-Fenster angezeigt.

1. Bearbeiten Sie die Parameter &quot;Projektinfo&quot;mithilfe des folgenden Musterdateifragments als Anleitung. Achten Sie darauf, den Projektionstyp wie unten hervorgehoben anzugeben. Beschreibungen der Parameter finden Sie in der Tabelle LatLonProjection Parameters im vorherigen Verfahren.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

