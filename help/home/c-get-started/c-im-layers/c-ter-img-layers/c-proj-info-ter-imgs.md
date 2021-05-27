---
description: Data Workbench unterstützt sowohl Längen- und Breitenprojektionen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.
title: Festlegen von Projektionsinformationen für Topografiebilder
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Festlegen von Projektionsinformationen für Topografiebilder{#specify-projection-information-for-terrain-images}

Data Workbench unterstützt sowohl Längen- und Breitenprojektionen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.

Projektionsinformationen sind für nicht projizierte Raw-Bitmaps und allgemeine, nicht projizierte Bilder erforderlich. Sie können Projektionsinformationen für Bilder mit eingebetteten Projektionsinformationen angeben, dies ist jedoch normalerweise nicht erforderlich, da die Projektionsparameter automatisch aus den im Bild selbst eingebetteten geodätischen Daten bestimmt werden. In den folgenden Abschnitten finden Sie Details zum Festlegen dieser Projektionsformate in der Datei [!DNL Terrain Images.cfg] .

## Breitengrad-Längengrad-Projektionen {#section-6e335357ec28462ba39c565e0a5986c7}

Das Projektionsformat &quot;latitude-longitude&quot;(LatLonProjection) in der Datei [!DNL Terrain Images.cfg] wird durch vier Parameter für Längen- und Breitengrad definiert.

Um eine LatLonProjection für nicht projizierte Bilder (unprojizierte Raw- und allgemeine Bitmaps, nicht projiziert) anzugeben, können Sie die Einstellungen für LatLonProjection im Fenster [!DNL Terrain Images.cfg] der Data Workbench eingeben.

Um eine LatLonProjection für Bilder mit eingebetteten Projektionsinformationen anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf LatLonProjection setzen und Einstellungen für [!DNL LatLonProjection] hinzufügen.

**So legen Sie eine LatLonProjection für nicht projizierte Bilder fest**

1. Öffnen Sie die Datei [!DNL Terrain Images.cfg] in Data Workbench und fügen Sie eine Topografiebildequelle hinzu, wie unter [So definieren Sie eine Topografiebildeschicht](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f) beschrieben.
1. Bearbeiten Sie die Parameter Projektionsinformationen mithilfe der folgenden Parametertabelle als Anleitung:

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
   <td colname="col2"> <p>Der Breitengrad der oberen Bildkante in Grad, wobei 90 der Nordpol und -90 der Südpol ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Der Breitengrad der unteren Bildkante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>Der Längengrad des linken Bildrands in Grad, wobei positive Zahlen östlich und negative Zahlen westliche Längengrade sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Der Längengrad der rechten Kante des Bildes. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und **[!UICONTROL Save]** klicken.
1. Um die lokal vorgenommenen Änderungen am Data Workbench-Servercomputer zu speichern, klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

**So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektionsinformationen fest**

Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.

Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte mit dem Servernamen für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg] wird ein Häkchen angezeigt.

Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg] wird in einem Editor-Fenster angezeigt.

Bearbeiten Sie die Parameter Projektionsinformationen mithilfe des folgenden Beispieldateifragments als Anleitung. Stellen Sie sicher, dass Sie den Projektionstyp wie unten hervorgehoben angeben. Beschreibungen der Parameter finden Sie in der Tabelle LatLonProjection Parameters im vorherigen Verfahren.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Universelle Transversal-Mercatorprojektionen {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

Die UTM-Projektion (Universal Transverse Mercator) wird durch acht Parameter definiert. Wenn Sie eine universelle Transversal-Mercatorprojektion für eine Topografiebildebene festlegen, müssen Ihre Topografiebildedateien mit false (projiziert) nördlich an die Bildspitze und false Eastern an die rechte Bildseite ausgerichtet werden.

Um eine UTM-Projektion für eine beliebige Topografiebildquelle anzugeben, müssen Sie die Datei [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad öffnen, den Parameter Projektionsinformationen auf &quot;TransverseMercatorProjection&quot;setzen und Einstellungen für die UTM-Projektion hinzufügen.

**So legen Sie eine universelle Transversal-Mercatorprojektion fest**

1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Terrain Images.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte mit dem Servernamen für [!DNL Terrain Images.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. Ein Häkchen wird in der Spalte [!DNL Temp] für [!DNL Terrain Images.cfg.] angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL Terrain Images.cfg] wird in einem Editor-Fenster angezeigt.
1. Bearbeiten Sie die Parameter Projektionsinformationen mithilfe des folgenden Beispieldateifragments und der Parametertabelle als Handbücher. Stellen Sie sicher, dass Sie den Projektionstyp wie unten hervorgehoben angeben.

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
   <td colname="col1"> <p>Ellipsoid Inverse Flatening, Ellipsoid Semimajor Axis </p> </td> 
   <td colname="col2"> <p>Die Parameter des für die Projektion verwendeten Auslassungspunkts. Die Achse der Hauptachsen ist in Metern angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falsch verzehrt </p> </td> 
   <td colname="col2"> <p>Das falsche Ost des zentralen Meridians der Projektion in Metern. Für UTM ist dies immer 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falsche Normung </p> </td> 
   <td colname="col2"> <p>Die falsche Normalisierung des Äquators in der Projektion in Metern. UTM: 0 für die Zonen auf der Nordhalbkugel und 10.000 für die Gebiete auf der Südhalbkugel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nordwest-Kornkoordinaten, Südostkornkoordinaten </p> </td> 
   <td colname="col2"> <p>Die Koordinaten (in projizierten Metern) der oberen linken und unteren rechten Ecke des Bildes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premierminister Meridian </p> </td> 
   <td colname="col2"> <p>Der Längengrad des zentralen Längenkreises der Projektion, angegeben in Grad östlich von Greenwich. Negative Zahlen können verwendet werden, um westliche Grade anzugeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skalierungsfaktor </p> </td> 
   <td colname="col2"> <p>Das Verhältnis zwischen dem Radius des Projektionszylinders und der halben Achse des Ellipsoiums. Für UTM-Projektionen (Universal Transverse Mercator) ist dies immer 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
