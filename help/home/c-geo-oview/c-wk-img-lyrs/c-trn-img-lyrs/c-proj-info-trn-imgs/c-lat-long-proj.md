---
description: Das Projektionsformat "latitude-longitude"(LatLonProjection) in der Datei "Terrain Images.cfg"wird durch vier Parameter für Längen- und Breitengrad definiert.
title: Breitengrad-Längengrad-Projektionen
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Breitengrad-Längengrad-Projektionen{#latitude-longitude-projections}

{{eol}}

Das Projektionsformat &quot;latitude-longitude&quot;(LatLonProjection) in der Datei &quot;Terrain Images.cfg&quot;wird durch vier Parameter für Längen- und Breitengrad definiert.

Um eine LatLonProjection für nicht projizierte Bilder (nicht projizierte Raw-Bitmaps und allgemeine Bilder, nicht projiziert) anzugeben, können Sie Einstellungen für LatLonProjection innerhalb der [!DNL Terrain Images.cfg] in Data Workbench angezeigt. Siehe [So legen Sie eine LatLonProjection für nicht projizierte Bilder fest](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Um eine LatLonProjection für Bilder mit eingebetteten Projektionsinformationen anzugeben, müssen Sie die [!DNL Terrain Images.cfg] -Datei in einem Texteditor wie Notepad, setzen Sie den Parameter Projection Info auf &quot;LatLonProjection&quot;und fügen Sie Einstellungen für LatLonProjection hinzu. Siehe [So legen Sie LatLonProjection für Bilder in eingebetteten Projektionsinformationen fest..](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [So legen Sie eine LatLonProjection für nicht projizierte Bilder fest](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektionsinformationen fest..](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## So legen Sie eine LatLonProjection für nicht projizierte Bilder fest {#section-26554eefe645481faba68396fa13756a}

1. Öffnen Sie die [!DNL Terrain Images.cfg] Datei in Data Workbench hinzufügen und eine Topografiebildeschicht-Quelle hinzufügen, wie hier beschrieben: [So definieren Sie eine Topografiebildebene](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Bearbeiten Sie die Parameter Projektionsinformationen mithilfe der folgenden Parametertabelle als Anleitung:

   | Parameter | Beschreibung |
   |---|---|
   | Lat0 | Der Breitengrad der oberen Bildkante in Grad, wobei 90 der Nordpol und -90 der Südpol ist. |
   | Lat1 | Der Breitengrad der unteren Bildkante. |
   | Lon0 | Der Längengrad des linken Bildrands in Grad, wobei positive Zahlen östlich und negative Zahlen westliche Längengrade sind. |
   | Lon1 | Der Längengrad der rechten Kante des Bildes. |

1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen am Data Workbench-Server-Computer zu speichern, speichern Sie im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] im [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektinformationen fest {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] -Datei befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte &quot;Servername&quot;für [!DNL Terrain Images.cfg]Klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Terrain Images.cfg].

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL Terrain Images.cfg] -Datei in einem Editor-Fenster angezeigt.

1. Bearbeiten Sie die Parameter Projektionsinformationen mithilfe des folgenden Beispieldateifragments als Anleitung. Stellen Sie sicher, dass Sie den Projektionstyp wie unten hervorgehoben angeben. Beschreibungen der Parameter finden Sie in der Tabelle LatLonProjection Parameters im vorherigen Verfahren.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
