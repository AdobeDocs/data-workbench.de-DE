---
description: Tabelle, die die Parameter für die Benutzergruppe definiert.
title: Benutzergruppen für die Abfragewarteschlage
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Benutzergruppen für die Abfragewarteschlage{#query-queue-user-groups}

Tabelle, die die Parameter für die Benutzergruppe definiert.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>Ein benutzerdefinierter Name der Benutzergruppe, z. B. Analysten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Richtlinien </p> </td> 
   <td colname="col2"> <p>Vektor </p> </td> 
   <td colname="col3"> <p>Gibt einen Richtlinientyp an. Klicken Sie mit der rechten Maustaste, um "Standardrichtlinie"oder "Tageszeitplan"auszuwählen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardrichtlinie </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Eine Standardrichtlinie stellt sicher, dass Benutzer mit einer niedrigen Priorität inkrementell in die Warteschlange verschoben und geplant werden, auch wenn Benutzer mit höherer Priorität in die Warteschlange einsteigen. Sie können einer Gruppe mehrere Richtlinien desselben Typs hinzufügen, deren Auswirkungen kumulativ sind. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Prioritätsbegrenzung:</b> Die Beschränkung, oberhalb derer die Priorität nicht erhöht wird. Der Wert für die maximale Priorität. Sie können diesen Wert verwenden, um die mit dieser Richtlinie generierten Prioritäten in einem bestimmten Bereich zu belassen (z. B. damit die Prioritäten für einige andere Benutzergruppen immer höher sind, sodass sie nicht über die Priorität "Unberührbar"hinausgehen. </li> 
     </ul> </p> <p> <b>Standardrichtlinien-Inkrementierungen</b> </p> <p>Die Inkrementierungseinstellungen für die Standardrichtlinie erhöhen die Priorität einer Abfrage im Zeitverlauf. Dies erzwingt nicht die Planung der Stapel, Sie können diese Einstellungen jedoch verwenden, um Benutzer zu priorisieren, die schon lange warten. Die in die Warteschlange gestellten Parameter wirken sich auf Abfragen aus, die sich derzeit in der Warteschlange befinden (z. B. aufgrund unzureichender Ressourcen zum Abschließen). Die geplanten Parameter wirken sich auf Abfragen aus, die beantwortet werden. Die Priorität einer Abfrage erhöht sich um die in den entsprechenden Feldern für Inkrement- und Inkrementierungsintervall angegebene Anzahl: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Warteschlangeninkrementierung: </b> Legt die Prioritätszunahme pro Update während der Warteschlange fest. Diese Einstellung stellt sicher, dass Benutzer mit niedriger Priorität in die Warteschlange verschoben werden. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Inkrementierungsintervall in der Warteschlange: </b> Legt die Anzahl der Sekunden zwischen Aktualisierungen während der Warteschlange fest. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Geplante Erhöhung: </b> Legt die Prioritätszunahme pro Aktualisierung während der Planung fest. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Geplantes Inkrementierungsintervall: </b> Legt die Anzahl der Sekunden zwischen den geplanten Aktualisierungen fest. <p> <p>Hinweis:  Das Festlegen von Inkrement- und Intervallaktualisierungsraten, die für in die Warteschlange gestellte Bundches höher sind als für geplante Bundches, kann zu Oszillationen führen. (Angenommen, Sie setzen den Wert für "Queued Increment"auf 100 und für "Scheduled Increment"auf 0 und setzen den Wert für "Queued Increment Interval"auf 1 und für "Unberührbare Priorität"auf hoch. Wenn zwei Abfragen-Bundches mit einer Grundpriorität von 0 eingehen und nicht genügend Ressourcen vorhanden sind, um beide Abfragen gleichzeitig auszuführen, wird eine davon eingeplant. Nach einer Sekunde hat die Abfrage, die nicht geplant war, eine Priorität von 100 und greift der geplanten vor. Nach zwei weiteren Sekunden hat die vorweggenommene nun eine Priorität von 200, und die beiden Switches werden wieder platziert. Keine der beiden Abfragen ist abgeschlossen, da alle zwei Sekunden die zu berechnete Abfrage vorweggenommen wird, damit die andere Abfrage ausgeführt werden kann.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Richtlinie für den täglichen Zeitplan </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Hiermit können Sie die Priorität zu bestimmten Tageszeiten ändern. Dieser Zeitplan ist nützlich für automatisierte Clients, wie z. B. <span class="wintitle"> Report Server</span> und wenn Benutzer des Systems in verschiedenen Zeitzonen leben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Änderungen </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Klicken Sie mit der rechten Maustaste, um eine geplante Änderung der Priorität hinzuzufügen. Die Änderungszeit ist die Zeit des Tages, an dem die Änderung erfolgt. Das Format lautet Stunde:Minuten AM/PM. Wenn AM oder PM nicht eingegeben wird, verwendet das System militärische Zeit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prioritätsgrenze </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Der maximale Prioritätswert, der sich aus einer Änderung ergibt. Die Änderung der Priorität ist der Betrag, der der Priorität hinzugefügt wird. Der Wert 0 gibt beispielsweise eine Standardpriorität zurück. Jeder andere Wert führt zu einer Priorität der Standardpriorität plus dieser Zahl. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer </p> </td> 
   <td colname="col2"> <p>Vektor </p> </td> 
   <td colname="col3"> <p>Liste der Gruppenmitglieder. </p> <p> <b>Name:</b> Der Name des Benutzers, wie er im Zertifikat des Benutzers im Feld "Allgemeiner Name"angezeigt wird. </p> <p> <b>Zusätzliche Priorität: </b> Bietet zusätzliche Priorität für die Basispriorität der Benutzergruppe, um die Startpriorität für diesen Benutzer zu bestimmen. </p> </td> 
  </tr> 
 </tbody> 
</table>
