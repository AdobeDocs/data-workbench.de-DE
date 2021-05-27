---
description: Latenzdimensionen werden aus einer übergeordneten zählbaren Dimension wie Sitzungen und einer Zeitdimension wie Tag erstellt.
title: Erstellen von Latenzdimensionen
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Erstellen von Latenzdimensionen{#create-a-latency-dimension}

Latenzdimensionen werden aus einer übergeordneten zählbaren Dimension wie Sitzungen und einer Zeitdimension wie Tag erstellt.

Wenn Sie eine Latenztabelle in Data Workbench erstellen, fügen Sie der Visualisierungsdatei (.vw) automatisch eine Latenzdimension hinzu. Sie können die Latenzdimension einer Tabelle bearbeiten, indem Sie die folgenden Schritte ausführen.

**So bearbeiten Sie eine Latenzdimension**

1. Öffnen Sie die von Ihnen erstellte Latenztabelle in einem Texteditor wie Notepad. Sie befindet sich im Ordner &quot;User&quot;> &quot;`working profile name`&quot;> &quot;Work&quot;im Installationsverzeichnis Ihrer Data Workbench.

   Die definierte Latenzdimension umfasst die im folgenden Beispiel dargestellten Parameter. (Die Definition Ihrer Latenzdimension kann zusätzliche Parameter enthalten.) [!DNL line entity = LatencyDim:] gibt den Beginn der Definition der Latenzdimension an.

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

1. Bearbeiten Sie die Werte für die Parameter &quot;Name&quot;, &quot;Level&quot;, &quot;Clip&quot;, &quot;Zeit&quot;, &quot;Format&quot;, &quot;Zeit vor&quot;oder &quot;Zeit nach&quot;, indem Sie die folgende Tabelle als Anleitung verwenden:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Für diesen Parameter ... </th> 
      <th colname="col2" class="entry"> Geben Sie diese Informationen an... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Name </p> </td> 
      <td colname="col2"> <p>Optional. Der Name der Latenzdimension, der im Kontextmenü angezeigt wird, wenn Sie mit der rechten Maustaste auf die Dimensionsbezeichnung oder die Elemente klicken. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Ebene </p> </td> 
      <td colname="col2"> <p>Eine zählbare Dimension, die der Latenzdimension übergeordnet ist. Beispiele sind Sitzung, Besucher und Seitenansicht. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Eine zählbare Dimension, die eine Eins-zu-viele-Beziehung zur Ebene der Latenzdimension aufweist. Die Latenz wird nicht über die Grenzen dieser Dimension hinweg berechnet. Wenn Sie beispielsweise eine Seitenansichtsebene und einen Sitzungsabschnitt angeben, werden Latenzen für die Seitenansichten berechnet, die während derselben Sitzung wie das Ereignis aufgetreten sind. </p> <p>Weitere Informationen zu Eins-zu-viele-Dimensionen (einfach) finden Sie im <i>Handbuch zur Datensatzkonfiguration</i>. </p> </td> 
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
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Versatz. Eine Ganzzahl, die dem negativen Wert für "Zeit vor"entspricht. Wenn beispielsweise "Zeit vor"den Wert 7 hat, sollte der Versatz -7 betragen. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit vor </p> </td> 
      <td colname="col2"> <p>Die maximale Zeitdauer (ausgedrückt in Einheiten der Zeitdimension) vor dem Ereignis, für das Latenzzeiten berechnet werden. Wenn dieser Wert auf 0 gesetzt oder gar nicht festgelegt ist, wird die Latenz nur für die Vorwärtsrichtung berechnet. </p> <p>Wenn Sie diesen Wert ändern, müssen Sie den Offset-Wert im Parameter Format ändern: Der Versatz ist der negative Wert für "Zeit vor". </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit nach </p> </td> 
      <td colname="col2"> <p>Die maximale Zeitdauer (ausgedrückt in Einheiten der Zeitdimension) nach dem Ereignis, für das Latenzzeiten berechnet werden. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern Sie die Datei [!DNL .vw] im Ordner Benutzer\*Arbeitsprofilname*\Work .

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

   In der folgenden Latenzdimension wird die Latenz jedes Sitzungsereignisses in Stunden und Zeit vor auf null gesetzt. Daher wird die Latenz nur für die Sitzungen berechnet, die innerhalb von 24 Stunden nach dem definierten Ereignis stattgefunden haben.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
