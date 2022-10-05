---
description: Tabelle, die die Parameter für Benutzergruppen definiert.
title: Benutzergruppen für die Abfragewarteschlage
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Benutzergruppen für die Abfragewarteschlage{#query-queue-user-groups}

{{eol}}

Tabelle, die die Parameter für Benutzergruppen definiert.

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
   <td colname="col3"> <p>Gibt einen Richtlinientyp an. Klicken Sie mit der rechten Maustaste, um Standardrichtlinie oder Tageszeitplan auszuwählen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardrichtlinie </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Eine Standardrichtlinie stellt sicher, dass Benutzer mit einer niedrigen Priorität schrittweise in die Warteschlange verschoben und geplant werden, selbst wenn Benutzer mit höherer Priorität in die Warteschlange eintreten. Sie können mehrere Richtlinien desselben Typs zu einer Gruppe hinzufügen, deren Wirkung kumulativ ist. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Prioritätsgrenze:</b> Die Begrenzung, ab der die Priorität nicht erhöht wird. Der Wert der maximalen Priorität. Sie können diesen Wert verwenden, um die von dieser Richtlinie erzeugten Prioritäten in einem bestimmten Bereich zu belassen (z. B. damit die Prioritäten für einige andere Benutzergruppen immer höher sind oder sie nicht über die Priorität "Unberührbar"hinausgehen. </li> 
     </ul> </p> <p> <b>Standardmäßige Richtliniensteigerungen</b> </p> <p>Die Inkrementierungseinstellungen für die Standardrichtlinie erhöhen im Laufe der Zeit die Priorität einer Abfrage. Dies erzwingt nicht die Planung der Bundches. Sie können diese Einstellungen jedoch verwenden, um Benutzer zu priorisieren, die schon lange gewartet haben. Die in der Warteschlange befindlichen Parameter wirken sich auf Abfragen aus, die sich derzeit in der Warteschlange befinden (z. B. aufgrund unzureichender Ressourcen, um sie abzuschließen). Die geplanten Parameter betreffen Abfragen, die beantwortet werden. Die Priorität einer Abfrage erhöht sich um die in den entsprechenden Inkrement- und Inkrementierungsintervallfeldern angegebene Zahl: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>In Warteschlange eingestellte Inkrementierung:</b> Legt die Prioritätsstufe pro Update während der Warteschlange fest. Diese Einstellung stellt sicher, dass Benutzer mit niedriger Priorität in die Planungswarteschlange verschoben werden. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Inkrementierungsintervall in Warteschlange:</b> Legt die Anzahl der Sekunden zwischen Aktualisierungen während der Warteschlange fest. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Geplante Erhöhung:</b> Legt die Prioritätsstufe pro Aktualisierung während der Planung fest. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Geplantes Erhöhungsintervall:</b> Legt die Anzahl der Sekunden zwischen Aktualisierungen während der Planung fest. <p> <p>Hinweis: Das Festlegen der Inkrement- und Intervallaktualisierungsraten für in der Warteschlange befindliche Bundles höher als für geplante Bundches kann zu einer Oszillation führen. (Angenommen, Sie legen den Wert für "Inkrementierung in Warteschlange"auf 100 und die "Geplante Inkrementierung"auf 0 fest und setzen den Wert für "Intervall in Warteschlange"auf 1 und die Priorität "Unberührbar"auf einen hohen Wert. Wenn zwei Abfragen mit der Basispriorität 0 enthalten und nicht genügend Ressourcen vorhanden sind, um beide Abfragen gleichzeitig auszuführen, wird einer von ihnen geplant. Nach einer Sekunde hat die nicht geplante Abfrage eine Priorität von 100 und greift der geplanten vor. Nach zwei weiteren Sekunden hat die vorweggenommene jetzt Priorität 200, und die beiden Switches werden erneut platziert. Keine der beiden Abfragen wird beendet, da die Abfrage, die berechnet wird, alle zwei Sekunden vorangestellt wird, damit die andere Abfrage ausgeführt werden kann.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Richtlinien für den täglichen Zeitplan </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Hiermit können Sie die Priorität zu bestimmten Tageszeiten ändern. Dieser Zeitplan ist für automatisierte Clients nützlich, z. B. <span class="wintitle"> Berichtsserver</span>und wenn Benutzer des Systems in verschiedenen Zeitzonen leben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Änderungen </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Klicken Sie mit der rechten Maustaste, um eine geplante Prioritätsänderung hinzuzufügen. Die Änderungszeit ist die Tageszeit, zu der die Änderung erfolgt. Das Format lautet Hunde:Minuten AM/PM. Wenn AM oder PM nicht eingegeben wird, verwendet das System militärische Zeit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prioritätsgrenze </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Der aus einer Änderung resultierende maximale Prioritätswert. Die Prioritätsänderung ist der zur Priorität hinzugefügte Betrag. Beispielsweise gibt der Wert 0 eine Standardpriorität zurück. Alle anderen Werte haben die Priorität der Standardpriorität plus dieser Zahl. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer </p> </td> 
   <td colname="col2"> <p>Vektor </p> </td> 
   <td colname="col3"> <p>Listet die Benutzer auf, die Mitglieder der Gruppe sind. </p> <p> <b>Name:</b> Der Name des Benutzers, wie er im Feld Allgemeiner Name im Zertifikat des Benutzers angezeigt wird. </p> <p> <b>Zusätzliche Priorität:</b> Bietet zusätzliche Priorität für die Basispriorität der Benutzergruppe, um die Startpriorität für diesen Benutzer zu bestimmen. </p> </td> 
  </tr> 
 </tbody> 
</table>
