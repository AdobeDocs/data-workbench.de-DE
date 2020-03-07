---
description: Das Traffic-Profil enthält die folgenden Dimensionen zur Identifizierung von Besucheraktionen.
solution: Analytics
title: Traffic-Profildimensionen
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Traffic-Profildimensionen{#traffic-profile-dimensions}

Das Traffic-Profil enthält die folgenden Dimensionen zur Identifizierung von Besucheraktionen.

Die Dimensionen in der folgenden Tabelle sind im Transformationsdataset definiert und enthalten Dateien im Ordner &quot;Traffic\Dataset\Transformation directory&quot;.

| Name | Typ | Ebene | Beschreibung |
|---|---|---|---|
| Tag | Einfach | Sitzung | Der Tag des ersten Protokolleintrags der Sitzung. |
| Wochentag | Einfach | Sitzung | Der Wochentag des ersten Protokolleintrags einer Sitzung. |
| Exakte Seitendauer (ausgeblendet) | Numerisch | Seitenansicht | Die Dauer der Seitenansicht in Millisekunden, gemessen durch Abziehen der Zeit der nächsten Seitenansicht von der Zeit dieser Seitenansicht. Die genaue Dauer der letzten Seitenansicht in einer Sitzung ist immer 0. |
| Stunde | Einfach | Sitzung | Die Stunde des ersten Protokolleintrags einer Sitzung. |
| Stunde des Tages | Einfach | Sitzung | Die Stunde des Tages des ersten Protokolleintrags einer Sitzung. |
| Monat | Einfach | Sitzung | Der Monat des ersten Protokolleintrags einer Sitzung. |
| Seitenansicht | Zählbar | Sitzung | Ein Protokolleintrag oder &quot;Ereignisdatensatz&quot;entsprechend der Seitenansichtsbedingung. |
| Verweisende Stelle | Einfach | Sitzung | Die Domäne der zweiten Ebene der verweisenden Stelle des ersten Protokolleintrags der Sitzung (oder &quot;Keine&quot;, wenn es sich um eine interne Referrer-Domäne handelt). |
| Sitzung | Zählbar | Besucher | Ein Zeitraum zusammenhängender zusammenhängender Aktivitäten eines Besuchers. Sie wird durch einen Inaktivitätszeitraum von 30 Minuten und eine externe Referrer-Domäne oder eine maximale Sitzungsdauer von 48 Stunden begrenzt. Sowohl diese Timeouts als auch der Satz Domänen, die als intern gelten, können in der [!DNL Transformation.cfg] Datei konfiguriert werden. |
| URI | Einfach | Seitenansicht | Der URI-Stamm einer Seitenansicht. Die URI-Dimension kann mithilfe der Konvertierungen ReplaceURI, PrependURI und AppendURI neu definiert werden. |
| Besucher | Zählbar | nicht angegeben | Ein eindeutiger Wert von x-trackingid. Bei Verwendung beständiger Cookies entspricht dies in der Regel einem individuellen Browser. Die x-trackingid kann anderweitig auf der IP-Nummer oder einem anderen eindeutigen Bezeichner, wie z. B. x.509 Common Name, basieren. |
| Woche | Einfach | Sitzung | Die Woche des ersten Protokolleintrags einer Sitzung. |

Die Dimensionen in der folgenden Tabelle werden im Dimensionsverzeichnis des Traffic-Profils definiert:

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
   <td colname="col03"> Besucher </td> 
   <td colname="col3"> Der vom Besucher verwendete Benutzeragenten-Typ, einschließlich der Versionsnummer (z. B. MSIE 6.0) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Browsertyp </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Besucher </td> 
   <td colname="col3"> Der vom Besucher verwendete Benutzeragenten-Typ (z. B. MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchmaschine </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03">Sitzung <p>ERSTE ZEILE </p></td> 
   <td colname="col3"> Die erste Suchmaschine in einer Besuchersitzung, wenn ein Besucher eine benannte Suchmaschine aufgerufen hat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nächster URI </td> 
   <td colname="col2"> Abgeleitet (ShiftDim basierend auf der URI-Dimension) </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der URI des nächsten URI nach dem derzeit ausgewählten URI. Diese abgeleitete Dimension wird verwendet, um Analysen darüber durchzuführen, was Besucher nach einem gegebenen URI als Nächstes tun. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einmal vs. Wiederholen </td> 
   <td colname="col2"> Abgeleitet (SegmentDim basierend auf Metriken zu wiederholten Besuchern und einmaligen Besuchern) </td> 
   <td colname="col03"> Besucher </td> 
   <td colname="col3"> Der Typ des Besuchers: einmalig oder wiederholt. Einmalige Besucher hatten nur eine Sitzung auf der Site, während wiederholte Besucher mehr als eine Sitzung hatten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seite </td> 
   <td colname="col2"> Abgeleitet (Umbenennen von Dim basierend auf der URI-Dimension) </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der Name jeder Seite, die während einer Sitzung besucht wurde. Zunächst ist der Name der einzelnen Seiten identisch mit dem URI, kann aber zur einfacheren Interpretation geändert werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verweisende Stelle </td> 
   <td colname="col2"> Von der integrierten Dimension "Referrer"übernommen </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der Website, die zuerst eine Sitzung an die Site verwiesen hat (wie vom Browser des Besuchers bereitgestellt). </td> 
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
   <td colname="col3"> Jeder Suchbegriff wird von einer Suchmaschine weitergegeben, wenn ein Besucher über einen Clickthrough einer verweisenden Suchmaschine von einer benannten Suchmaschine verfügt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsdauer </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Exakte Seitendauer") </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Dauer einer Sitzung in 30-Sekunden-Schritten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzung Nr. </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Häufigkeit, mit der ein Besucher die Site besucht hat. Beispielsweise haben erstmalige Besucher die Sitzungsnummer "1", zweimalige Besucher die Sitzungsnummer "2" usw. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten der Sitzung </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Seitenansichten") </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Anzahl der Seitenansichten in einer Sitzung. Wenn Sie beispielsweise "3"in der Dimension "Seitenansichten der Sitzung"auswählen, werden alle Sitzungen mit genau 3 Seitenansichten ausgewählt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchmaschine </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der ersten Website, bei der es sich um eine benannte Suchmaschine handelt, die einen Besucher während einer Sitzung zur Site weitergeleitet hat (wie vom Browser des Besuchers bereitgestellt). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitdimensionen </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Stunde, der Tag, die Stunde, die Woche, der Wochentag, der Monat, das Quartal oder das Jahr, in dem die Sitzung begann. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitberichtsdimensionen </td> 
   <td colname="col2"> Abgeleitet (LastN- und Umbenennungsdimensionen basierend auf integrierten Zeitdimensionen) </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Dimensionen einschließlich Tage vor, Tage des letzten Monats, Tage der letzten Woche, Tage des Monats, Tage dieser Woche, Stunden des Tages, Stunden des letzten Tages, letzte 12 Monate, Letzte 2 Monate, Letzte 2 Wochen, Letzte 24 Stunden, Letzte 3 Monate, Letzte 4 Wochen, Letzte 6 Monate, Letzte 7 Tage, Letzte 7 Tage und Heute, Die letzten 8 Wochen, die letzten 9 Monate, der letzte Monat, die letzte Woche, die letzten Monate, der Monat, dieser Monat, diese Woche, diese und die letzten 14 Tage, Diese und die letzten 6 Monate, Diese und Letzten 8 Wochen, Heute, Die heutige Berichterstattung, Heute und Letzte 30 Tage, Wochen vor und gestern bieten eine bequeme Möglichkeit, einen Arbeitsbereich oder Bericht zu erstellen, der immer einen Teil der Daten im Datensatz anzeigt. Jede basiert auf dem Beginn einer Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Von dem integrierten Dimensions-URI übernommen </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der URI jeder angezeigten Seite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten des Besuchers </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Seitenansichten") </td> 
   <td colname="col03"> Besucher </td> 
   <td colname="col3"> Die Anzahl der bis dato angezeigten Seitenansichten eines Besuchers. Wenn Sie beispielsweise in der Dimension "Seitenansichten"des Besuchers "3"auswählen, werden alle Besucher mit genau 3 Seitenansichten in allen Sitzungen ausgewählt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer des Besuchers </td> 
   <td colname="col2"> Von der integrierten Dimension "Referrer"übernommen </td> 
   <td colname="col03"> Besucher </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der Website, die einen Besucher zum ersten Mal für die erste Sitzung an die Site verwiesen hat (wie vom Browser des Besuchers bereitgestellt). </td> 
  </tr> 
 </tbody> 
</table>

