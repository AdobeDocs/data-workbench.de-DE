---
description: Das Traffic-Profil enthält die folgenden Dimensionen, um Besucher-Aktionen leichter identifizieren zu können.
title: Traffic-Profil-Dimensionen
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# Traffic-Profil-Dimensionen{#traffic-profile-dimensions}

Das Traffic-Profil enthält die folgenden Dimensionen, um Besucher-Aktionen leichter identifizieren zu können.

Die Dimensionen in der folgenden Tabelle sind im Transformationsdataset definiert und enthalten Dateien im Ordner &quot;Traffic\Dataset\Transformation directory&quot;.

| Name | Typ | Ebene | Beschreibung |
|---|---|---|---|
| Tag | Einfach | Sitzung | Der Tag des ersten Protokolleintrags der Sitzung. |
| Wochentag | Einfach | Sitzung | Der Wochentag des ersten Protokolleintrags einer Sitzung. |
| Exakte Seitendauer (ausgeblendet) | Numerisch | Seitenansicht | Die Ansicht der Seite in Millisekunden, gemessen durch Abziehen der Ansicht der nächsten Seite vom Zeitpunkt der Ansicht der Seite. Die genaue Dauer der letzten Ansicht einer Sitzung ist immer 0. |
| Stunde | Einfach | Sitzung | Die Stunde des ersten Protokolleintrags einer Sitzung. |
| Stunde des Tages | Einfach | Sitzung | Die Stunde des Tages des ersten Protokolleintrags einer Sitzung. |
| Monat | Einfach | Sitzung | Der Monat des ersten Protokolleintrags einer Sitzung. |
| Seitenansicht | Zählbar | Sitzung | Ein Protokolleintrag oder &quot;Ereignis-Datensatz&quot;entsprechend der Ansicht der Seite. |
| Referrer | Einfach | Sitzung | Die Zweitstufendomäne des Werbers des ersten Protokolleintrags der Sitzung (oder Keine, wenn es sich um eine interne Werber-Domäne handelt). |
| Sitzung | Zählbar | Besucher. | Ein Zeitraum zusammenhängender zusammenhängender Aktivitäten durch einen Besucher. Sie wird durch einen Inaktivitätszeitraum von 30 Minuten und eine externe Werber-Domäne oder eine maximale Sitzungsdauer von 48 Stunden begrenzt. Sowohl diese Timeouts als auch der Satz von Domänen, die als intern gelten, können in der Datei [!DNL Transformation.cfg] konfiguriert werden. |
| URI | Einfach | Seitenansicht | Der URI-Stamm einer Ansicht. Die URI-Dimension kann mithilfe der Konvertierungen ReplaceURI, PrependURI und AppendURI neu definiert werden. |
| Besucher. | Zählbar | Nicht angegeben | Ein eindeutiger Wert von x-trackingid. Bei Verwendung beständiger Cookies entspricht dies in der Regel einem individuellen Browser. Die x-trackingid kann anderweitig auf der IP-Nummer oder einem anderen eindeutigen Bezeichner, wie z. B. x.509 Common Name, basieren. |
| Woche | Einfach | Sitzung | Die Woche des ersten Protokolleintrags einer Sitzung. |

Die Dimensionen in der folgenden Tabelle sind im Verzeichnis Dimension des Traffic-Profils definiert:

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col03" class="entry"> Ebene </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Browser </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der vom Besucher verwendete Benutzeragenten-Typ, einschließlich der Versionsnummer (z. B. MSIE 6.0) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Browser-Typ </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der vom Besucher verwendete Benutzeragenten-Typ (z. B. MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchmaschine  </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03">Sitzung <p>ERSTE ZEILE </p></td> 
   <td colname="col3"> Die erste Suchmaschine in der Sitzung eines Besuchers, wenn ein Besucher eine benannte Suchmaschine durchsucht hat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nächster URI </td> 
   <td colname="col2"> Abgeleitet (ShiftDim basierend auf der URI-Dimension) </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der URI des nächsten URI nach dem derzeit ausgewählten URI. Diese abgeleitete Dimension dient zur Durchführung von Analysen darüber, was Besucher nach einem gegebenen URI als Nächstes tun. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einmal vs. Wiederholen </td> 
   <td colname="col2"> Abgeleitet (SegmentDim basierend auf Metriken zu wiederholten Besuchern und einmaligen Besuchern) </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der Typ des Besuchers: einmalig oder wiederholt. Einmalige Besucher hatten nur eine Sitzung auf der Site, während wiederholte Besucher mehr als eine Sitzung hatten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seite </td> 
   <td colname="col2"> Abgeleitet (Umbenennen von Dim basierend auf der URI-Dimension) </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der Name jeder Seite, die während einer Sitzung besucht wurde. Zunächst ist der Name der einzelnen Seiten identisch mit dem URI, kann aber zur einfacheren Interpretation geändert werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Werber </td> 
   <td colname="col2"> Von der Dimension "Integrierter Werber"übernommen </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der Website, die die Sitzung zum ersten Mal an die Site verwiesen hat (wie vom Browser des Besuchers angegeben). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchbegriff </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03">Sitzung <p>ERSTE ZEILE </p></td> 
   <td colname="col3"> Der erste Suchbegriff in der Sitzung eines Besuchers, der von einer Suchmaschine weitergegeben wird, wenn ein Besucher von einer benannten Suchmaschine aus gesucht hat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchbegriff </td> 
   <td colname="col2"> Viele-zu-viele </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Jeder Suchbegriff wird von einer Suchmaschine weitergegeben, wenn ein Besucher über einen Durchklick auf einen Werber von einer benannten Suchmaschine verfügt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsdauer </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Exakte Seitendauer") </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Dauer einer Sitzung in 30-Sekunden-Schritten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsnummer </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Häufigkeit, mit der ein Besucher die Site besucht hat. Beispielsweise haben erstmalige Besucher die Sitzungsnummer "1", zweimalige Besucher die Sitzungsnummer "2" usw. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ansichten der Sitzungsseite </td> 
   <td colname="col2"> Abgeleitet (MetricDim, basierend auf der Metrik "Ansichten der Seite") </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Anzahl der Ansichten einer Sitzung. Wenn Sie beispielsweise "3"in der Dimension "Sitzungsseite"auswählen, werden alle Ansichten mit genau 3 Ansichten ausgewählt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchmaschine  </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der ersten Website, bei der es sich um eine benannte Suchmaschine handelt, die einen Besucher während einer Sitzung an die Site verwiesen hat (wie vom Browser des Besuchers angegeben). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitdimensionen </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Stunde, der Tag, die Stunde, die Woche, der Wochentag, der Monat, das Quartal oder das Jahr, in dem die Sitzung begann. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensionen des Berichte </td> 
   <td colname="col2"> Abgeleitet (LastN- und Umbenennungsdimensionen basierend auf integrierten Zeitdimensionen) </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Dimensionen wie "Tage vor", "Tage des letzten Monats", "Tage der letzten Woche", "Tage dieses Monats", "Wochentage", "Stunden des Tages", "Gestern", "Letzte 12 Monate", "Letzte 2 Monate", "Letzte 2 Wochen", "Letzte 24 Stunden", "Letzte 3 Monate", "Letzte 4 Wochen", "Letzte 6 Monate", "Letzte 7 Tage", "Letzte 7 Tage", "Letzte 7 Tage", "Heute", Die letzten 8 Wochen, die letzten 9 Monate, der letzte Monat, die letzte Woche, die letzten 6 Monate, der Monat, diese Woche, diese und die letzten 14 Tage, Diese und die letzten 6 Monate, Diese und die letzten 8 Wochen, Heute, Heute Berichte, Heute und Letzte 30 Tage, Wochen vor und gestern bieten eine praktische Möglichkeit, einen Arbeitsbereich oder Bericht zu erstellen, der immer einen Teil der Daten in den Daten anzeigt et. Jede basiert auf dem Beginn einer Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Von der integrierten Dimensionen-URI übernommen </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der URI jeder angezeigten Seite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ansichten der Besucher-Seite </td> 
   <td colname="col2"> Abgeleitet (MetricDim, basierend auf der Metrik "Ansichten der Seite") </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Die Anzahl der bisherigen Ansichten eines Besuchers. Wenn Sie beispielsweise "3"in der Dimension "Ansichten der Besucher-Seite"auswählen, werden alle Besucher mit genau 3 Ansichten für alle Sitzungen ausgewählt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucherverweiser </td> 
   <td colname="col2"> Vom integrierten Dimension-Werber übernommen </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der Website, die einen Besucher zum ersten Mal zur ersten Sitzung an die Site verwiesen hat (wie vom Browser des Besuchers bereitgestellt). </td> 
  </tr> 
 </tbody> 
</table>
