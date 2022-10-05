---
description: Formatierungsinformationen über die Elementpunkteschichtdatei.
title: Format der Elementpunkt-Schichtdatei
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---

# Format der Elementpunkt-Schichtdatei{#element-point-layer-file-format}

{{eol}}

Formatierungsinformationen über die Elementpunkteschichtdatei.

Jede Elementpunktebene [!DNL .layer] -Datei, die auf eine Lookup-Datei verweist, muss mithilfe der folgenden Vorlage formatiert werden:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Datenpfade </td> 
   <td colname="col2"> Pfad zur Lookup-Datei mit Längen- und Breitengraddaten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Längengrad-Spalte </td> 
   <td colname="col2"> Der Name der Spalte in der Lookup-Datei, die die Längengraddaten enthält. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Breitengrad, Spalte </td> 
   <td colname="col2"> Der Name der Spalte in der Lookup-Datei mit den Breitengraddaten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namensspalte </td> 
   <td colname="col2"> Optional. Der Name der Spalte in der Lookup-Datei, die die Namen der Positionen enthält, die durch die Längen- und Breitengraddaten dargestellt werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schlüsselspalte </td> 
   <td colname="col2"> <p>Der Name der Spalte in der Lookup-Datei, die die gemeinsamen Schlüsseldaten enthält. Dadurch kann der Data Workbench-Server die Daten in die Lookup-Datei in den Datensatz integrieren. Dies muss die erste Spalte in der Lookup-Datei sein. </p> <p>Jede Zeile in dieser Spalte ist ein Element einer Dimension. Diese Dimension muss im <span class="filepath"> Transformation.cfg</span> -Datei oder einem Transformationsdatensatz enthält eine -Datei und wird im Dateiparameter "Dimension"dieser Datei angegeben. Weitere Informationen zu Konfigurationsdateien für Umwandlungen finden Sie in der <i>Anleitung zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">Der Name der Dimension (definiert in einer Umwandlungskonfigurationsdatei), die Elemente enthält, die den Datenzeilen in der <span class="wintitle"> Schlüssel</span> Spalte. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrik </td> 
   <td colname="col2"> Der Name der Metrik, die über die im Parameter "Dimension"angegebene Dimension ausgewertet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skalieren </td> 
   <td colname="col2"> Optional. Wert, der zur Größe der Punkte in der Ebene verwendet wird. Der Standardwert lautet 100. Größere Werte machen die Punkte größer und kleinere Werte machen sie kleiner. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Farbe </td> 
   <td colname="col2"> Optional. Der Farbvektor der RGB, der als (rot, grün, blau) angegeben wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1,0, 0,0, 0,0) ist beispielsweise hellrot und (0,5, 0,5, 0,5) grau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendermodus </td> 
   <td colname="col2"> <p>Optional. Ganzzahlwert, der den für die Ebene zu verwendenden Rendermodus darstellt. Die drei verfügbaren Modi lauten wie folgt: 
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Rendermodus 1. Die Punktgröße wird in der Bildschirmgröße definiert (Punkte bleiben im Verhältnis zum Computerbildschirm konstant.) Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. Dies ist der standardmäßige Rendermodus. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Rendermodus 2. Die Punktgröße wird im Weltraum definiert (Punkte bleiben eine konstante Größe relativ zum Globus). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Rendermodus 3. Die Punktgröße wird im Bildschirmbereich definiert. Punkte werden mithilfe von OpenGL-glatten Punkten gerendert. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die [!DNL Zip Points.layer] -Datei wie folgt formatiert:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
