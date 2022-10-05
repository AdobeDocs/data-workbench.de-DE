---
description: Data Workbench unterstützt sowohl Längen- und Breitenprojektionen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.
title: Festlegen von Projektionsinformationen für Topografiebilder
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Festlegen von Projektionsinformationen für Topografiebilder{#specify-projection-information-for-terrain-images}

{{eol}}

Data Workbench unterstützt sowohl Längen- und Breitenprojektionen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.

Projektionsinformationen sind für nicht projizierte Raw-Bitmaps und allgemeine, nicht projizierte Bilder erforderlich. Sie können Projektionsinformationen für Bilder mit eingebetteten Projektionsinformationen angeben, dies ist jedoch normalerweise nicht erforderlich, da die Projektionsparameter automatisch aus den im Bild selbst eingebetteten geodätischen Daten bestimmt werden. Die folgenden Abschnitte enthalten Details zum Festlegen dieser Projektionsformate in der [!DNL Terrain Images.cfg] -Datei.

## Breitengrad-Längengrad-Projektionen {#section-6e335357ec28462ba39c565e0a5986c7}

Das Projektionsformat des Breitengrads (LatLonProjection) im [!DNL Terrain Images.cfg] -Datei wird durch vier Parameter für Längen- und Breitengrad definiert.

Um eine LatLonProjection für nicht projizierte Bilder (nicht projizierte Raw-Bitmaps und allgemeine Bilder, nicht projiziert) anzugeben, können Sie Einstellungen für LatLonProjection innerhalb der [!DNL Terrain Images.cfg] in der Data Workbench.

Um eine LatLonProjection für Bilder mit eingebetteten Projektionsinformationen anzugeben, müssen Sie die [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad, setzen Sie den Parameter Projection Info auf LatLonProjection und fügen Sie Einstellungen für die [!DNL LatLonProjection].

**So legen Sie eine LatLonProjection für nicht projizierte Bilder fest**

1. Öffnen Sie die [!DNL Terrain Images.cfg] Datei in Data Workbench hinzufügen und eine Topografiebildeschicht-Quelle hinzufügen, wie hier beschrieben: [So definieren Sie eine Topografiebildebene](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
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

1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um die lokal vorgenommenen Änderungen am Data Workbench-Servercomputer zu speichern, verwenden Sie die [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für [!DNL Terrain Images.cfg] im [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**So legen Sie eine LatLonProjection für Bilder in eingebetteten Projektionsinformationen fest**

Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] -Datei befindet sich in diesem Verzeichnis.

Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte &quot;Servername&quot;für [!DNL Terrain Images.cfg]Klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Terrain Images.cfg].

Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL Terrain Images.cfg] -Datei in einem Editor-Fenster angezeigt.

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

Um eine UTM-Projektion für eine beliebige Topografiebildquelle anzugeben, müssen Sie die [!DNL Terrain Images.cfg] in einem Texteditor wie Notepad, setzen Sie den Parameter Projektionsinformationen auf &quot;TransverseMercatorProjection&quot;und fügen Sie Einstellungen für die UTM-Projektion hinzu.

**So legen Sie eine universelle Transversal-Mercatorprojektion fest**

1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Terrain Images.cfg] -Datei befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte &quot;Servername&quot;für [!DNL Terrain Images.cfg]Klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Terrain Images.cfg.]
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL Terrain Images.cfg] -Datei in einem Editor-Fenster angezeigt.
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
