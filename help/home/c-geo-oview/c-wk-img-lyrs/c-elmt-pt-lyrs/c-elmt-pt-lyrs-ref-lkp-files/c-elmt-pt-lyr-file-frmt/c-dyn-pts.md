---
description: Beim Erstellen einer Elementpunktebene mit dynamischen Punkten werden die Breiten- und Längengraddaten in jedes Element der Dimension eingebettet.
solution: Analytics
title: Definieren von Elementpunktebenen mithilfe von dynamischen Punkten
topic: Data workbench
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definieren von Elementpunktebenen mithilfe von dynamischen Punkten{#defining-element-point-layers-using-dynamic-points}

Beim Erstellen einer Elementpunktebene mit dynamischen Punkten werden die Breiten- und Längengraddaten in jedes Element der Dimension eingebettet.

Um eine Elementpunktebene mit dynamischen Punkten zu definieren, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Eine Dimension**[!DNL Transformation.cfg] , die in der Datei oder in einem Transformationsdataset definiert ist, enthält die Datei, in der jedes Element die Zeichenfolge &quot;Breitengrad,Längengrad&quot;oder &quot;Breitengrad,Längengrad,Name&quot;enthält.

   Anweisungen zum Erstellen einer Dimension finden Sie im Handbuch zur Konfiguration von *Datasets*.

* **Eine Ebenendatei** , die die zugehörige Dimension angibt.

   Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter Dateiformat für [Elementpunkte](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Bei der Verwendung [!DNL Dynamic Points]muss unbedingt sichergestellt werden, dass die Kardinalität der in der Ebenendatei angegebenen Dimension angemessen ist. Wenn jede Zeile eines Datensatzes einen anderen Breiten- und Längengrad aufweist, füllt sich die Dimension schnell und die meisten Zeilen werden in ein Element mit kleinen Elementen umgewandelt. Da das Element &quot;Kleine Elemente&quot;keine Längen- und Breitengrad aufweist, wird es nicht auf der Welt angezeigt.

## Dateiformat des Elementpunktes {#section-bbcc2baa2f754dba81eba93339a97cbd}

Jede Elementpunktebenendatei mit dynamischen Punkten muss mit der folgenden Vorlage formatiert werden:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>Der Name der Dimension (in einer Konvertierungskonfigurationsdatei definiert), die Elemente mit der Zeichenfolge "latitude,Längengrad"oder "latitude,Längengrad,name"enthalten muss, wie in den folgenden Beispielen dargestellt: 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126, irgendwo </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrik </td> 
   <td colname="col2"> Der Name der Metrik, die über die im Parameter Dimension angegebene Dimension ausgewertet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamische Punkte </td> 
   <td colname="col2"> Aktiviert dynamische Punkte. Auf true setzen. </td> 
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
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Rendermodus 1. Die Punktgröße wird im Bildschirmbereich definiert (Punkte bleiben relativ zum Computerbildschirm konstant). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. Dies ist der standardmäßige Rendermodus. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Rendermodus 2. Die Punktgröße wird im Weltraum definiert (Punkte bleiben im Verhältnis zum Globus konstant). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Rendermodus 3. Die Punktgröße wird im Bildschirmbereich definiert. Punkte werden mit OpenGL-Übergangspunkten gerendert. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die [!DNL IP Coordinates.layer] Datei ist wie folgt formatiert:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

