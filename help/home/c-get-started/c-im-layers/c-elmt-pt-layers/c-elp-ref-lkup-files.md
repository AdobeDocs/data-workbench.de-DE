---
description: Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Breiten- und Längengraddaten abzurufen, wird die Position des Punkts durch Abrufen der einzelnen Elemente und der zugehörigen Längen- und Breitengrad aus der Lookup-Datei ermittelt.
solution: Analytics
title: Definieren von Elementpunktebenen, die auf Lookup-Dateien verweisen
topic: Data workbench
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definieren von Elementpunktebenen, die auf Lookup-Dateien verweisen{#define-element-point-layers-referencing-lookup-files}

Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Breiten- und Längengraddaten abzurufen, wird die Position des Punkts durch Abrufen der einzelnen Elemente und der zugehörigen Längen- und Breitengrad aus der Lookup-Datei ermittelt.

>[!NOTE]
>
>Statt eine Lookup-Datei zu verwenden, können Sie die Funktion &quot;Dynamische Punkte&quot;verwenden, mit der der Breiten- und Längengrad einer Position im Namen jedes Elements einer Dimension eingebettet wird. Siehe [Definieren von Elementpunktebenen mithilfe von dynamischen Punkten](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

Um eine Elementpunktebene zu definieren, die auf eine Lookup-Datei verweist, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Eine Dimension** , die in der [!DNL Transformation.cfg file] Datei oder in einer [!DNL transformation dataset include] Datei definiert ist. Weitere Informationen zu Transformationskonfigurationsdateien finden Sie im Handbuch zur Konfiguration von *DataSet*.

* **Eine Lookup-Datei** , die die Daten enthält, die zur Darstellung der einzelnen Datenpunkte verwendet werden. Diese Datei muss mindestens drei Datenspalten für jeden Datenpunkt enthalten: Schlüssel, Längengrad und Breitengrad. Weitere Informationen zum erforderlichen Format der Lookup-Datei finden Sie unter [Element Point Layer-Dateiformat](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

* **Eine Ebenendatei** , die den Speicherort der Lookup-Datei angibt und die zugehörige Dimension und Metrik sowie die Schlüssel-, Längen- und Breitenspaltennamen in der Lookup-Datei identifiziert. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter Dateiformat für [Elementpunkte](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

   >[!NOTE]
   >
   >Die mit dem [!DNL Zip Points.layer] Profil bereitgestellte [!DNL Geography] Datei ist eine Elementpunktebene, die die [!DNL Zipcode.dim] Datei, die [!DNL Sessions.metric] Datei, die [!DNL Zip Points.txt] Nachschlagedatei und die Namen der Schlüssel-, Längen-, Breiten- und Namensspalten in der Nachschlagedatei identifiziert.

## Elementpunktsuchdateiformat {#section-0bc8c652c1bd40eb84078f2af71a5c06}

Die Abfragedatei der Elementpunktebene muss mindestens die folgenden drei Spalten enthalten:

* **[!DNL Key]column:**Diese Spalte sollte allgemeine Schlüsseldaten enthalten, die es dem Data Workbench-Server ermöglichen, die Daten in der Abfragedatei mit denen im Datensatz zu verbinden. Die[!DNL key]Spalte muss die erste Spalte in der Lookup-Datei sein. Jede Zeile in dieser Spalte identifiziert ein Element der Dimension.

* **[!DNL Longitude]column:**Diese Spalte sollte den Längengrad für jeden Datenpunkt in der[!DNL Key]Spalte enthalten.

* **[!DNL Latitude]column:**Diese Spalte sollte den Breitengrad für jeden Datenpunkt in der[!DNL Key]Spalte enthalten.

* **[!DNL Name]Spalte (Optional):**Wenn Sie für jeden Datenpunkt einen Namen angeben möchten, der auf der Zuordnung angezeigt werden soll, können Sie eine[!DNL Name]Spalte in die Lookup-Datei einfügen.

Jede Zeile in der [!DNL Zip Points.txt] Abfragedatei enthält einen Postleitzahl in der ersten Spalte gefolgt von Längen- und Breitengrad sowie dem zugehörigen Ortsnamen.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Dateiformat der Elementpunktebene {#section-52d7e92be8354d979af9e7a2210b76f2}

Jede Elementpunktebenendatei, [!DNL .layer] die auf eine Lookup-Datei verweist, muss mithilfe der folgenden Vorlage formatiert werden:

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
   <td colname="col2"> Pfad zur Lookup-Datei, die Breiten- und Längengraddaten enthält. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Längengradspalte </td> 
   <td colname="col2"> Der Name der Spalte in der Lookup-Datei, die die Längengraddaten enthält. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Breitenspalte </td> 
   <td colname="col2"> Der Name der Spalte in der Lookup-Datei, die die Breitendaten enthält. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namensspalte </td> 
   <td colname="col2"> Optional. Der Name der Spalte in der Lookup-Datei, die die Namen der Positionen enthält, die durch die Breiten- und Längengraddaten dargestellt werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schlüsselspalte </td> 
   <td colname="col2"> <p>Der Name der Spalte in der Lookup-Datei, die die allgemeinen Schlüsseldaten enthält, wodurch der Data Workbench-Server die Daten in die Lookup-Datei in den Datensatz integrieren kann. Dies muss die erste Spalte in der Lookup-Datei sein. </p> <p>Jede Zeile in dieser Spalte ist ein Element einer Dimension. Diese Dimension muss in der Datei " <span class="filepath"> Transformation.cfg</span> "oder in einem <span class="wintitle"> Transformationsdataset einschließlich</span> der Datei definiert und im Parameter "Dimension"dieser Datei angegeben werden. Weitere Informationen zu Transformationskonfigurationsdateien finden Sie im Handbuch zur Konfiguration von <i>DataSet</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">Der Name der Dimension (in einer Konvertierungskonfigurationsdatei definiert), die Elemente enthält, die den Datenzeilen in der Spalte " <span class="wintitle"> Schlüssel</span> "entsprechen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrik </td> 
   <td colname="col2"> Der Name der Metrik, die über die im Parameter Dimension angegebene Dimension ausgewertet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skalierung </td> 
   <td colname="col2"> Optional. Der Wert, der zur Größe der Punkte in der Ebene verwendet wird. Der Standardwert lautet 100. Größere Werte machen die Punkte größer und kleinere Werte verkleinern sie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kanalfarbe </td> 
   <td colname="col2"> Optional. Der RGB-Farbvektor, der als (rot, grün, blau) ausgedrückt wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1.0, 0.0, 0.0) ist beispielsweise hellrot und (0.5, 0.5, 0.5) grau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendermodus </td> 
   <td colname="col2"> <p>Optional. Ganzzahlwert, der den für die Ebene zu verwendenden Rendermodus darstellt. Die drei verfügbaren Modi lauten wie folgt: 
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Rendermodus 1. Die Punktgröße wird im Bildschirmbereich definiert (Punkte bleiben relativ zum Computerbildschirm konstant). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. Dies ist der standardmäßige Rendermodus. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Rendermodus 2. Die Punktgröße wird im Weltraum definiert (Punkte bleiben im Verhältnis zum Globus konstant). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Rendermodus 3. Die Punktgröße wird im Bildschirmbereich definiert. Punkte werden mit OpenGL-Übergangspunkten gerendert. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die [!DNL Zip Points.layer] Datei ist wie folgt formatiert:

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

