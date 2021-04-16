---
description: Das Projektionsformat "LatLonProjection"in der Datei "Terrain Images.cfg"wird durch vier Parameter für Längen- und Breitengrad definiert.
title: Breitengrad-Längengrad-Projektionen
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Breitengrad-Längengrad-Projektionen{#latitude-longitude-projections}

Das Projektionsformat &quot;LatLonProjection&quot;in der Datei &quot;Terrain Images.cfg&quot;wird durch vier Parameter für Längen- und Breitengrad definiert.

Um eine LatLonProjection für nicht projizierte Bilder (unprojizierte unprojizierte Bitmaps und allgemeine Bilder, nicht projiziert) anzugeben, können Sie die Einstellungen für LatLonProjection im Fenster [!DNL Terrain Images.cfg] in der Data Workbench eingeben. Siehe [So legen Sie eine LatLonProjection für nicht projizierte Bilder](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a) fest.

Um für Bilder mit eingebetteten Projektionsinformationen eine LatLonProjection-Datei anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf &quot;LatLonProjection&quot;setzen und Einstellungen für LatLonProjection hinzufügen. Siehe [So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [So legen Sie eine LatLonProjection für nicht projizierte Bilder fest](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## So legen Sie eine LatLonProjection für nicht projizierte Bilder fest {#section-26554eefe645481faba68396fa13756a}

1. Öffnen Sie die Datei [!DNL Terrain Images.cfg] in der Data Workbench und fügen Sie eine Quelle für Bodenbild-Ebenen hinzu, wie unter [So definieren Sie eine Terrain-Bildebene](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf) beschrieben.

1. Bearbeiten Sie die Parameter für Projektinformationen mithilfe der folgenden Parametertabelle als Anleitung:

   | Parameter | Beschreibung |
   |---|---|
   | Lat0 | Die Breite der oberen Kante des Bildes in Grad, wobei 90 der Nordpol und -90 der Südpol ist. |
   | Lat1 | Die Breite der unteren Kante des Bilds. |
   | Lon0 | Der Längengrad der linken Kante des Bildes in Grad, wobei positive Zahlen östlich und negative Zahlen westliche Längen sind. |
   | Lon1 | Der Längengrad der rechten Kante des Bilds. |

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und auf **[!UICONTROL Save]** klicken.

1. Um die lokal vorgenommenen Änderungen am Data Workbench-Servercomputer zu speichern, klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg] wird in einem Editor-Fenster angezeigt.

1. Bearbeiten Sie die Parameter &quot;Projektinfo&quot;mithilfe des folgenden Musterdateifragments als Anleitung. Achten Sie darauf, den Projektionstyp wie unten hervorgehoben anzugeben. Beschreibungen der Parameter finden Sie in der Tabelle LatLonProjection Parameters im vorherigen Verfahren.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
