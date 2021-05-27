---
description: Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Längen- und Breitengraddaten zu erhalten, wird der Standort des Punkts durch Abrufen der einzelnen Elemente sowie der zugehörigen Längen- und Breitengrade aus der Lookup-Datei abgerufen.
title: Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 3%

---

# Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien{#define-element-point-layers-referencing-lookup-files}

Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Längen- und Breitengraddaten zu erhalten, wird der Standort des Punkts durch Abrufen der einzelnen Elemente sowie der zugehörigen Längen- und Breitengrade aus der Lookup-Datei abgerufen.

>[!NOTE]
>
>Statt eine Lookup-Datei zu verwenden, können Sie die Funktion &quot;Dynamische Punkte&quot;verwenden, mit der der Längen- und Breitengrad eines Standorts im Namen jedes Elements einer Dimension eingebettet wird. Siehe [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

Um eine Elementpunktebene zu definieren, die auf eine Lookup-Datei verweist, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Eine in der** Datei  [!DNL Transformation.cfg file] oder einer  [!DNL transformation dataset include] Datei definierte Dimension. Informationen zu Konfigurationsdateien für Umwandlungen finden Sie im *Handbuch zur Datensatzkonfiguration*.

* **Eine Lookup-Datei** mit den Daten, die für die Darstellung der einzelnen Datenpunkte verwendet werden. Diese Datei muss mindestens drei Datenspalten für jeden Datenpunkt enthalten: der Schlüssel, der Längengrad und der Breitengrad. Weitere Informationen zum erforderlichen Format der Lookup-Datei finden Sie unter [Element Point Layer File Format](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

* **Eine Ebenendatei,** die den Speicherort der Lookup-Datei angibt und die zugehörige Dimension und Metrik sowie die Schlüssel-, Längen- und Breitenspaltennamen in der Lookup-Datei angibt. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Element Point Layer File Format](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

   >[!NOTE]
   >
   >Die mit dem Profil [!DNL Geography] bereitgestellte Datei [!DNL Zip Points.layer] ist eine Elementpunktebene, die die [!DNL Zipcode.dim]-Datei, die [!DNL Sessions.metric]-Datei, die [!DNL Zip Points.txt]-Lookup-Datei sowie die Namen der Spalten Schlüssel, Längen- und Breitengrad sowie Name in der Lookup-Datei angibt.

## Format der Elementpunkt-Lookup-Datei {#section-0bc8c652c1bd40eb84078f2af71a5c06}

Die Lookup-Datei der Elementpunktebene muss mindestens die folgenden drei Spalten enthalten:

* **[!DNL Key]column:** Diese Spalte sollte gemeinsame Schlüsseldaten enthalten, die es dem Data Workbench-Server ermöglichen, die Daten in der Lookup-Datei mit denen im Datensatz zu verbinden. Die Spalte [!DNL key] muss die erste Spalte in der Lookup-Datei sein. Jede Zeile in dieser Spalte identifiziert ein Element der Dimension.

* **[!DNL Longitude]column:** Diese Spalte sollte den Längengrad für jeden Datenpunkt in der  [!DNL Key] Spalte enthalten.

* **[!DNL Latitude]column:** Diese Spalte sollte den Breitengrad für jeden Datenpunkt in der  [!DNL Key] Spalte enthalten.

* **[!DNL Name]column (optional):** Wenn Sie für jeden Datenpunkt einen Namen angeben möchten, der auf der Zuordnung angezeigt werden soll, können Sie eine  [!DNL Name] Spalte in die Lookup-Datei einfügen.

Jede Zeile in der Lookup-Datei [!DNL Zip Points.txt] enthält in der ersten Spalte eine ZIP-Code-Zeile, gefolgt von Längen- und Breitengrad und dem zugehörigen Stadtnamen.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Dateiformat der Elementpunkteschicht {#section-52d7e92be8354d979af9e7a2210b76f2}

Jede Elementpunktebene [!DNL .layer], die auf eine Lookup-Datei verweist, muss mithilfe der folgenden Vorlage formatiert werden:

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col2"> <p>Der Spaltenname in der Lookup-Datei, der die gemeinsamen Schlüsseldaten enthält. Dadurch kann der Data Workbench-Server die Daten in die Lookup-Datei in den Datensatz integrieren. Dies muss die erste Spalte in der Lookup-Datei sein. </p> <p>Jede Zeile in dieser Spalte ist ein Element einer Dimension. Diese Dimension muss in der Datei <span class="filepath"> Transformation.cfg</span> oder in einer Datei <span class="wintitle"> des Transformationsdatensatzes </span> definiert und im Dateiparameter "Dimension"dieser Datei angegeben werden. Weitere Informationen zu Konfigurationsdateien für Umwandlungen finden Sie im <i>Handbuch zur Datensatzkonfiguration</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">Der Name der Dimension (definiert in einer Umwandlungskonfigurationsdatei), die Elemente enthält, die den Datenzeilen in der Spalte <span class="wintitle"> Schlüssel</span> entsprechen. </td> 
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
   <td colname="col2"> Optional. Der RGB-Farbvektor, der als (rot, grün, blau) angegeben wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1,0, 0,0, 0,0) ist beispielsweise hellrot und (0,5, 0,5, 0,5) grau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendermodus </td> 
   <td colname="col2"> <p>Optional. Ganzzahlwert, der den für die Ebene zu verwendenden Rendermodus darstellt. Die drei verfügbaren Modi lauten wie folgt: 
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Rendermodus 1. Die Punktgröße wird in der Bildschirmgröße definiert (Punkte bleiben im Verhältnis zum Computerbildschirm konstant.) Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. Dies ist der standardmäßige Rendermodus. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Rendermodus 2. Die Punktgröße wird im Weltraum definiert (Punkte bleiben eine konstante Größe relativ zum Globus). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Rendermodus 3. Die Punktgröße wird im Bildschirmbereich definiert. Punkte werden mithilfe von OpenGL-glatten Punkten gerendert. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die Datei [!DNL Zip Points.layer] ist wie folgt formatiert:

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
