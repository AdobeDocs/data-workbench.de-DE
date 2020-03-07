---
description: Latenzdimensionen werden aus einer übergeordneten zählbaren Dimension wie Sitzungen und einer Zeitdimension wie Tag erstellt.
solution: Analytics
title: Erstellen einer Latenzdimension
topic: Data workbench
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen einer Latenzdimension{#create-a-latency-dimension}

Latenzdimensionen werden aus einer übergeordneten zählbaren Dimension wie Sitzungen und einer Zeitdimension wie Tag erstellt.

Wenn Sie eine Latenztabelle in Data Workbench erstellen, fügen Sie der Visualisierungsdatei (.vw) automatisch eine Latenzdimension hinzu. Sie können die Latenzdimension einer Tabelle wie folgt bearbeiten:

**So bearbeiten Sie eine Latenzdimension**

1. Öffnen Sie die von Ihnen erstellte Latenztabelle in einem Texteditor wie Notepad. Sie befindet sich im Ordner &quot;Benutzer&quot;> `working profile name` &quot;Arbeit&quot;in Ihrem Installationsordner von Data Workbench.

   Die definierte Latenzdimension umfasst die Parameter, die im folgenden Beispiel gezeigt werden. (Die Definition der Latenzdimension kann zusätzliche Parameter enthalten.) Die [!DNL line entity = LatencyDim:] gibt den Anfang der Definition der Latenzdimension an.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Bearbeiten Sie die Werte für die Parameter &quot;Name&quot;, &quot;Ebene&quot;, &quot;Clip&quot;, &quot;Zeit&quot;, &quot;Format&quot;, &quot;Zeit vor&quot;oder &quot;Zeit nach&quot;, indem Sie die folgende Tabelle als Anleitung verwenden:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Für diesen Parameter... </th> 
      <th colname="col2" class="entry"> Geben Sie diese Informationen ein... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Name </p> </td> 
      <td colname="col2"> <p>Optional. Der Name der Latenzdimension, die im Kontextmenü angezeigt wird, wenn Sie mit der rechten Maustaste auf die Dimensionsbeschriftung oder die Elemente klicken. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Ebene </p> </td> 
      <td colname="col2"> <p>Eine zählbare Dimension, die der Dimension "Latenz"übergeordnet ist. Beispiele sind Sitzung, Besucher und Seitenansicht. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Eine zählbare Dimension, die eine Eins-zu-viele-Beziehung zur Ebene der Latenzdimension hat. Die Latenz wird nicht über die Grenzen dieser Dimension hinweg berechnet. Wenn Sie beispielsweise eine Ebene für die Seitenansicht und einen Clip für die Sitzung angeben, werden die Latenzen für die Seitenansichten berechnet, die während der gleichen Sitzung wie das Ereignis auftraten. </p> <p>Weitere Informationen zu 1-zu-n-Dimensionen (einfache Dimensionen) finden Sie im Handbuch zur <i>Datensatzkonfiguration</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit </p> </td> 
      <td colname="col2"> <p>Die Dimension, die zum Messen der verstrichenen Zeit für die Latenzdimension verwendet wird. Diese Dimension kann eine Zeitdimension wie Tag oder Stunde oder eine zählbare Dimension wie Besucher, Sitzung oder Seitenansicht sein. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Format </td> 
      <td colname="col2"> <p>Optional. Gibt das Erscheinungsbild der Latenzvisualisierung in Data Workbench an. Im Parameter Format können Sie die folgenden Werte bearbeiten: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Uhrzeit-Zeichenfolge. Die Zeiteinheit, die in der Latenzvisualisierung angezeigt wird, z. B. Tag oder Woche. Achten Sie darauf, die Uhrzeit-Zeichenfolge zu ändern, wenn Sie die Zeitdimension ändern. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Versatz. Eine ganze Zahl, die dem negativen Wert für "Zeit vor"entspricht. Wenn "Zeit vor"beispielsweise den Wert 7 hat, sollte der Offset -7 betragen. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit vor </p> </td> 
      <td colname="col2"> <p>Die maximale Zeit (ausgedrückt in den Einheiten der Zeitdimension) vor dem Ereignis, für das Latenzzeiten berechnet werden. Wenn dieser Wert auf 0 gesetzt ist oder gar nicht, wird die Latenz nur für die Vorwärtsrichtung berechnet. </p> <p>Wenn Sie diesen Wert ändern, vergewissern Sie sich, dass Sie den Versatzwert im Parameter Format ändern: Der Offset ist der negative Wert für "Zeit vor". </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit nach </p> </td> 
      <td colname="col2"> <p>Die maximale Zeit (ausgedrückt in den Einheiten der Zeitdimension) nach dem Ereignis, für das Latenzzeiten berechnet werden. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern Sie die [!DNL .vw] Datei im Ordner &quot;User\*working profile name*\Work&quot;.

   Im Folgenden finden Sie die Einstellungen für die standardmäßige Latenzdimension:

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   In der folgenden Latenzdimension wird die Latenz jedes Sitzungsereignisses in Stunden und Zeit vor auf Null berechnet. Daher wird die Latenz nur für die Sitzungen berechnet, die innerhalb von 24 Stunden nach dem definierten Ereignis erfolgten.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
