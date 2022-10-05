---
description: Beim Erstellen einer Elementpunktebene mit dynamischen Punkten werden die Längen- und Breitengraddaten in jedes Element der Dimension eingebettet.
title: Definieren von Elementpunktebenen anhand von dynamischen Punkten
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# Definieren von Elementpunktebenen anhand von dynamischen Punkten{#defining-element-point-layers-using-dynamic-points}

{{eol}}

Beim Erstellen einer Elementpunktebene mit dynamischen Punkten werden die Längen- und Breitengraddaten in jedes Element der Dimension eingebettet.

Um eine Elementpunktebene mithilfe von dynamischen Punkten zu definieren, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Dimension**, definiert im [!DNL Transformation.cfg] -Datei oder einer Umwandlungsdatensatzeinschlussdatei, in der jedes Element die Zeichenfolge &quot;latitude,longitude&quot;oder &quot;latitude,longitude,name&quot;enthält.

   Anweisungen zum Erstellen einer Dimension finden Sie unter *Anleitung zur Datensatzkonfiguration*.

* **Ebenendatei** , der die zugehörige Dimension angibt.

   Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Format der Elementpunkt-Schichtdatei](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Bei Verwendung von [!DNL Dynamic Points]muss unbedingt sichergestellt werden, dass die Kardinalität der in der Ebenendatei angegebenen Dimension angemessen ist. Wenn jede Zeile eines Datensatzes einen anderen Längen- und Breitengrad aufweist, füllt sich die Dimension schnell an und die meisten Zeilen werden in ein Element &quot;Kleinste Elemente&quot;umgewandelt. Da das Element &quot;Kleine Elemente&quot;keinen Längen- und Breitengrad aufweist, wird es nicht auf der Welt angezeigt.

## Format der Elementpunkt-Schichtdatei {#section-bbcc2baa2f754dba81eba93339a97cbd}

Jede Elementpunktebenen-Datei, die dynamische Punkte verwendet, muss mithilfe der folgenden Vorlage formatiert werden:

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
   <td colname="col2"> <p>Der Name der Dimension (definiert in einer Transformationskonfigurationsdatei), die Elemente mit der Zeichenfolge "latitude,longitude"oder "latitude,longitude,name"enthalten muss, wie in den folgenden Beispielen gezeigt: 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181, 77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126, irgendwo </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrik </td> 
   <td colname="col2"> Der Name der Metrik, die über die im Parameter "Dimension"angegebene Dimension ausgewertet wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamische Punkte </td> 
   <td colname="col2"> Aktiviert dynamische Punkte. Auf "true"setzen. </td> 
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
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Rendermodus 1. Die Punktgröße wird in der Bildschirmgröße definiert (Punkte bleiben im Verhältnis zum Computerbildschirm konstant.) Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. Dies ist der standardmäßige Rendermodus. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Rendermodus 2. Die Punktgröße wird im Weltraum definiert (Punkte bleiben eine konstante Größe relativ zum Globus). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Rendermodus 3. Die Punktgröße wird im Bildschirmbereich definiert. Punkte werden mithilfe von OpenGL-glatten Punkten gerendert. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die [!DNL IP Coordinates.layer] -Datei wie folgt formatiert:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
