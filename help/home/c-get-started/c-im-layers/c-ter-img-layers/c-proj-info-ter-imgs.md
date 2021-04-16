---
description: Data Workbench unterstützt sowohl Breiten- und Längengradprojektionen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Bodenbildquellen.
title: Festlegen von Projektionsinformationen für Topografiebilder
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Festlegen von Projektionsinformationen für Topografiebilder{#specify-projection-information-for-terrain-images}

Data Workbench unterstützt sowohl Breiten- und Längengradprojektionen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Bodenbildquellen.

Projektionsinformationen sind für unprojizierte und nicht projizierte Rohdaten und allgemeine Bilder erforderlich. Sie können Projektionsinformationen für Bilder mit eingebetteten Projektionsinformationen angeben, die jedoch normalerweise nicht erforderlich sind, da die Parameter der Projektion automatisch anhand der im Bild selbst eingebetteten geodätischen Daten bestimmt werden. Die folgenden Abschnitte enthalten Details zum Festlegen dieser Projektionsformate in der Datei [!DNL Terrain Images.cfg].

## Breitengrad-Längengrad-Projektionen {#section-6e335357ec28462ba39c565e0a5986c7}

Das Projektionsformat &quot;LatLonProjection&quot;in der Datei [!DNL Terrain Images.cfg] wird durch vier Parameter für Längen- und Breitengrad definiert.

Um eine LatLonProjection für nicht projizierte Bilder (unprojizierte unprojizierte Bitmaps und allgemeine Bilder, nicht projiziert) anzugeben, können Sie die Einstellungen für LatLonProjection im Fenster [!DNL Terrain Images.cfg] in der Data Workbench eingeben.

Um für Bilder mit eingebetteten Projektionsinformationen eine LatLonProjection-Datei anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf LatLonProjection einstellen und Einstellungen für [!DNL LatLonProjection] hinzufügen.

**So legen Sie eine LatLonProjection für nicht projizierte Bilder fest**

1. Öffnen Sie die Datei [!DNL Terrain Images.cfg] in Data Workbench und fügen Sie eine Bildschichtquelle für Geländebilder hinzu, wie unter [So definieren Sie eine Terrain-Bildebene](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f) beschrieben.
1. Bearbeiten Sie die Parameter für Projektinformationen mithilfe der folgenden Parametertabelle als Anleitung:

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>Die Breite der oberen Kante des Bildes in Grad, wobei 90 der Nordpol und -90 der Südpol ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Die Breite der unteren Kante des Bilds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>Der Längengrad der linken Kante des Bildes in Grad, wobei positive Zahlen östlich und negative Zahlen westliche Längen sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Der Längengrad der rechten Kante des Bilds. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und auf **[!UICONTROL Save]** klicken.
1. Klicken Sie zum Speichern der lokal vorgenommenen Änderungen auf dem Servercomputer der Data Workbench in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

**So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektionsinformationen fest**

Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.

Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg] wird ein Häkchen angezeigt.

Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg] wird in einem Editor-Fenster angezeigt.

Bearbeiten Sie die Parameter &quot;Projektinfo&quot;mithilfe des folgenden Musterdateifragments als Anleitung. Achten Sie darauf, den Projektionstyp wie unten hervorgehoben anzugeben. Beschreibungen der Parameter finden Sie in der Tabelle LatLonProjection Parameters im vorherigen Verfahren.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Universelle Transversal-Mercatorprojektionen {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

Die UTM-Projektion (Universal Transverse Mercator) wird durch acht Parameter definiert. Wenn Sie eine universelle Transverse-Mercator-Projektion für eine Terrain-Bildebene festlegen, müssen Ihre Terrain-Bilddateien mit &quot;false&quot;(projiziert) nach Norden gegen den oberen Bildrand und &quot;false east&quot;rechts neben dem Bild ausgerichtet werden.

Um eine UTM-Projektion für eine beliebige Terrain-Bildquelle anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf &quot;TransverseMercatorProjection&quot;setzen und Einstellungen für die UTM-Projektion hinzufügen.

**So legen Sie eine universelle Transverse-Mercator-Projektion fest**

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg.] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg] wird in einem Editor-Fenster angezeigt.
1. Bearbeiten Sie die Parameter &quot;Projektinfo&quot;mithilfe des folgenden Beispieldateifragments und der Parametertabelle als Hilfslinien. Achten Sie darauf, den Projektionstyp wie unten hervorgehoben anzugeben.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoid Inverse Flatting, Ellipsoid Semimajor Axis </p> </td> 
   <td colname="col2"> <p>Die Parameter des für die Projektion verwendeten Ellipsoids. Die Achse der Mittelachse ist in Metern angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fehl </p> </td> 
   <td colname="col2"> <p>Die falsche Ostlage des zentralen Meridians der Projektion in Metern. Für UTM ist das immer 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falsche Normsetzung </p> </td> 
   <td colname="col2"> <p>Die falsche Normsetzung des Äquators in der Projektion in Metern. Für UTM ist dies 0 für die Zonen auf der Nordhalbkugel und 10.000 für die Zonen auf der Südhalbkugel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nordwest-Corner-Koordinaten, Südost-Koordinaten </p> </td> 
   <td colname="col2"> <p>Die Koordinaten (in projizierten Metern) der oberen linken und unteren rechten Ecke des Bildes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premierminister Meridian </p> </td> 
   <td colname="col2"> <p>Der Längengrad des zentralen Längenkreises der Projektion, angegeben in Grad östlich von Greenwich. Negative Zahlen können verwendet werden, um Grad westlich anzugeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skalierungsfaktor </p> </td> 
   <td colname="col2"> <p>Das Verhältnis zwischen dem Radius des Projektionszylinders und der Mittellinie des Ellipsoids. Bei UTM-Projektionen (Universal Transverse Mercator) ist dies immer 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
