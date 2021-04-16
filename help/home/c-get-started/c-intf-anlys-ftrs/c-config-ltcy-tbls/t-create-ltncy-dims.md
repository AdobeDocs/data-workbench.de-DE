---
description: Latenzdimensionen werden aus einer übergeordneten zählbaren Dimension wie Sitzungen und einer Zeitdimension wie Tag erstellt.
title: Erstellen von Latenzdimensionen
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Erstellen von Latenzdimensionen{#create-a-latency-dimension}

Latenzdimensionen werden aus einer übergeordneten zählbaren Dimension wie Sitzungen und einer Zeitdimension wie Tag erstellt.

Wenn Sie eine Latenztabelle in der Data Workbench erstellen, fügen Sie der Visualisierungsdatei (.vw) automatisch eine Latenzdimension hinzu. Sie können die Latenzdimension einer Tabelle wie folgt bearbeiten:

**So bearbeiten Sie eine Latenzdimension**

1. Öffnen Sie die von Ihnen erstellte Latenztabelle in einem Texteditor wie Notepad. Sie befindet sich im Ordner &quot;User&quot;> &quot;`working profile name`&quot;> &quot;Work&quot;im Installationsordner Ihrer Data Workbench.

   Die definierte Latenzdimension umfasst die Parameter, die im folgenden Beispiel gezeigt werden. (Die Definition der Latenzdimension kann zusätzliche Parameter enthalten.) Das [!DNL line entity = LatencyDim:] gibt den Beginn der Definition der Latenzdimension an.

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
      <td colname="col2"> <p>Eine zählbare Dimension, die der Dimension "Latenz"übergeordnet ist. Beispiele sind Sitzung, Besucher und Ansicht der Seite. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Eine zählbare Dimension, die eine Eins-zu-viele-Beziehung zur Ebene der Latenzdimension hat. Die Latenz wird nicht über die Grenzen dieser Dimension hinweg berechnet. Wenn Sie z. B. eine Ansicht der Seite und einen Sitzungsclip angeben, werden die Latenzen für die Ansichten berechnet, die während der gleichen Sitzung wie das Ereignis aufgetreten sind. </p> <p>Weitere Informationen zu 1-zu-n-Dimensionen (einfach) finden Sie im Handbuch <i>Konfiguration von Datensätzen</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit </p> </td> 
      <td colname="col2"> <p>Die Dimension, die zum Messen der verstrichenen Zeit für die Latenzdimension verwendet wird. Diese Dimension kann eine Zeitdimension sein, z. B. Tag oder Stunde, oder eine zählbare Dimension wie Besucher-, Sitzungs- oder Seiten-Ansicht. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Format </td> 
      <td colname="col2"> <p>Optional. Gibt das Erscheinungsbild der Latenzvisualisierung in der Data Workbench an. Im Parameter Format können Sie die folgenden Werte bearbeiten: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Uhrzeit-Zeichenfolge. Die Zeiteinheit, die in der Latenzvisualisierung angezeigt wird, z. B. Tag oder Woche. Achten Sie darauf, die Uhrzeit-Zeichenfolge zu ändern, wenn Sie die Zeitdimension ändern. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Versatz. Eine ganze Zahl, die dem negativen Wert für "Zeit vor"entspricht. Wenn "Zeit vor"beispielsweise den Wert 7 hat, sollte der Offset -7 betragen. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit vor </p> </td> 
      <td colname="col2"> <p>Die maximale Zeitdauer (ausgedrückt in Zeiteinheiten) vor dem Ereignis, für das die Latenz berechnet wird. Wenn dieser Wert auf 0 gesetzt ist oder gar nicht, wird die Latenz nur für die Vorwärtsrichtung berechnet. </p> <p>Wenn Sie diesen Wert ändern, vergewissern Sie sich, dass Sie den Versatzwert im Parameter Format ändern: Der Offset ist der negative Wert für "Zeit vor". </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Zeit nach </p> </td> 
      <td colname="col2"> <p>Die maximale Zeitdauer (ausgedrückt in Zeiteinheiten) nach dem Ereignis, für das die Latenz berechnet wird. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern Sie die Datei [!DNL .vw] im Ordner &quot;User\*working Profil name*\Work&quot;.

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

   In der folgenden Latenzdimension wird die Latenz der einzelnen Sitzungs-Ereignis in Stunden und Zeit vor auf Null gesetzt. Daher wird die Latenz nur für die Sitzungen berechnet, die innerhalb von 24 Stunden nach dem definierten Ereignis erfolgten.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
