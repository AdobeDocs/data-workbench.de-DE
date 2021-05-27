---
description: Beim Erstellen einer Elementpunktebene mit dynamischen Punkten werden die Längen- und Breitengraddaten in jedes Element der Dimension eingebettet.
title: Definieren von Elementpunktebenen anhand von dynamischen Punkten
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
exl-id: 5f6e264c-5804-47fa-a3ca-8608a3f7e9d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 5%

---

# Definieren von Elementpunktebenen anhand von dynamischen Punkten{#define-element-point-layers-using-dynamic-points}

Beim Erstellen einer Elementpunktebene mit dynamischen Punkten werden die Längen- und Breitengraddaten in jedes Element der Dimension eingebettet.

Um eine Elementpunktebene mithilfe von dynamischen Punkten zu definieren, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* Eine Dimension, die in der Datei [!DNL Transformation.cfg] oder in der Datei [!DNL transformation dataset include] definiert ist und in der jedes Element die Zeichenfolge &quot;latitude,longitude&quot;oder &quot;latitude,longitude,name&quot;enthält.

   Anweisungen zum Erstellen einer Dimension finden Sie im *Handbuch zur Datensatzkonfiguration*.

* Eine Ebenendatei, die die zugehörige Dimension angibt.

Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Element Point Layer File Format](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0).

>[!NOTE]
>
>Bei Verwendung von [!DNL Dynamic Points] ist es wichtig sicherzustellen, dass die Kardinalität der in der Ebenendatei angegebenen Dimension angemessen ist. Wenn jede Zeile eines Datensatzes einen anderen Längen- und Breitengrad aufweist, füllt sich die Dimension schnell an und die meisten Zeilen werden in ein Element &quot;Kleinste Elemente&quot;umgewandelt. Da das Element &quot;Kleine Elemente&quot;keinen Längen- und Breitengrad aufweist, wird es nicht auf der Welt angezeigt.

## Dateiformat der Elementpunkteschicht {#section-0645fbc761c14bb986f3d6f02df407a0}

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

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
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
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181, 77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126, irgendwo </li> 
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
   <td colname="col2"> Optional. Der RGB-Farbvektor, der als (rot, grün, blau) angegeben wird. Für jede Farbe im Vektor können Sie einen Wert zwischen 0,0 und 1,0 eingeben. (1,0, 0,0, 0,0) ist beispielsweise hellrot und (0,5, 0,5, 0,5) grau. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendermodus </td> 
   <td colname="col2"> <p>Optional. Ganzzahlwert, der den für die Ebene zu verwendenden Rendermodus darstellt. Die drei verfügbaren Modi lauten wie folgt: 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">Rendermodus 1. Die Punktgröße wird in der Bildschirmgröße definiert (Punkte bleiben im Verhältnis zum Computerbildschirm konstant.) Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. Dies ist der standardmäßige Rendermodus. </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">Rendermodus 2. Die Punktgröße wird im Weltraum definiert (Punkte bleiben eine konstante Größe relativ zum Globus). Punkte werden mit Polygonen gerendert, sodass es keine Obergrenze für die Punktgröße gibt. </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">Rendermodus 3. Die Punktgröße wird im Bildschirmbereich definiert. Punkte werden mithilfe von OpenGL-glatten Punkten gerendert. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die Datei [!DNL IP Coordinates.layer] ist wie folgt formatiert:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
