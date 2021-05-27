---
description: Das Traffic-Profil enthält die folgenden Dimensionen, um Besucheraktionen zu identifizieren.
title: Traffic-Profil-Dimensionen
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# Traffic-Profil-Dimensionen{#traffic-profile-dimensions}

Das Traffic-Profil enthält die folgenden Dimensionen, um Besucheraktionen zu identifizieren.

Die Dimensionen in der folgenden Tabelle werden im Transformationsdatensatz definiert und enthalten Dateien in der Datei Traffic\Dataset\Transformation directory.

| Name | Typ | Ebene | Beschreibung |
|---|---|---|---|
| Tag | Einfach | Sitzung | Der Tag des ersten Protokolleintrags der Sitzung. |
| Wochentag | Einfach | Sitzung | Der Wochentag des ersten Protokolleintrags einer Sitzung. |
| Exakte Seitendauer (ausgeblendet) | Numerisch | Seitenansicht | Die Dauer der Seitenansicht in Millisekunden, gemessen durch Abzug der Zeit der nächsten Seitenansicht vom Zeitpunkt dieser Seitenansicht. Die genaue Dauer der letzten Seitenansicht in einer Sitzung ist immer 0. |
| Stunde | Einfach | Sitzung | Die Stunde des ersten Protokolleintrags einer Sitzung. |
| Stunde des Tages | Einfach | Sitzung | Die Stunde des Tages des ersten Protokolleintrags einer Sitzung. |
| Monat | Einfach | Sitzung | Der Monat des ersten Protokolleintrags einer Sitzung. |
| Seitenansicht | Zählbar | Sitzung | Ein Protokolleintrag oder &quot;Ereignisdatensatz&quot;, der die Seitenansichtsbedingung erfüllt. |
| Referrer | Einfach | Sitzung | Die Domäne der zweiten Ebene des Referrers des ersten Protokolleintrags der Sitzung (oder Keine , wenn es sich um eine interne Referrer-Domäne handelt). |
| Sitzung | Zählbar | Besucher. | Ein Zeitraum zusammenhängender fortlaufender Aktivitäten eines Besuchers. Trennzeichen sind ein Inaktivitätszeitraum von 30 Minuten und eine externe Referrer-Domäne oder eine maximale Sitzungsdauer von 48 Stunden. Sowohl diese Timeouts als auch der Satz der Domänen, die als intern gelten, können in der Datei [!DNL Transformation.cfg] konfiguriert werden. |
| URI | Einfach | Seitenansicht | Der URI-Stamm einer Seitenansicht. Die URI-Dimension kann mithilfe der Transformationen ReplaceURI, PrependURI und AppendURI neu definiert werden. |
| Besucher. | Zählbar | Nicht angegeben | Ein eindeutiger Wert von x-trackingid. Normalerweise einem eindeutigen Browser entspricht, wenn persistente Cookies verwendet werden. Die x-trackingid kann anderweitig auf der IP-Nummer oder einer anderen eindeutigen Kennung wie x.509 Common Name basieren. |
| Woche | Einfach | Sitzung | Die Woche des ersten Protokolleintrags einer Sitzung. |

Die Dimensionen in der folgenden Tabelle werden im Verzeichnis Dimension des Traffic-Profils definiert:

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
   <td colname="col3"> Der Typ des vom Besucher verwendeten Benutzeragenten, einschließlich der Versionsnummer (z. B. MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Browser-Typ </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der Typ des vom Besucher verwendeten Benutzeragenten (z. B. MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchmaschine </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03">Sitzung <p>ERSTE ZEILE </p></td> 
   <td colname="col3"> Die erste Suchmaschine in der Sitzung eines Besuchers, wenn ein Besucher von einer benannten Suchmaschine aus gesucht hat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nächster URI </td> 
   <td colname="col2"> Abgeleitet (ShiftDim basierend auf URI-Dimension) </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der URI des nächsten URI nach dem derzeit ausgewählten URI. Diese abgeleitete Dimension wird verwendet, um Analysen dazu durchzuführen, was Besucher nach einem bestimmten URI als Nächstes tun. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime vs. Repeat </td> 
   <td colname="col2"> Abgeleitet (SegmentDim basierend auf den Metriken "Wiederholte Besucher"und "Einmalige Besucher") </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der Typ des Besuchers: einmalig oder wiederholt. Einmalige Besucher hatten nur eine Sitzung auf der Site, während wiederholte Besucher mehr als eine Sitzung hatten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seite </td> 
   <td colname="col2"> Abgeleitet (Umbenennen von Dim basierend auf der URI-Dimension) </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der Name jeder Seite, die während einer Sitzung besucht wird. Zunächst ist der Name jeder Seite mit dem URI identisch, kann aber zur einfacheren Interpretation geändert werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer </td> 
   <td colname="col2"> Von der integrierten Dimension "Referrer"übernommen </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der Website, die zuerst eine Sitzung an die Site verwiesen hat (wie vom Browser des Besuchers angegeben). </td> 
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
   <td colname="col3"> Jeder Suchbegriff, der von einer Suchmaschine weitergegeben wird, wenn ein Besucher über einen Suchverweiser-Clickthrough von einer benannten Suchmaschine verfügt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsdauer </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Exact Page Duration") </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Dauer einer Sitzung in 30-Sekunden-Schritten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsnummer </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Häufigkeit, mit der ein Besucher die Site besucht hat. Beispielsweise haben erstmalige Besucher eine Sitzungsnummer "1", zweimalige Besucher eine Sitzungsnummer "2" usw. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsseitenansichten </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Seitenansichten") </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Anzahl der Seitenansichten in einer Sitzung. Wenn Sie beispielsweise "3"in der Dimension "Sitzungsseitenansichten"auswählen, werden alle Sitzungen mit genau 3 Seitenansichten ausgewählt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suchmaschine </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der ersten Website, bei der es sich um eine benannte Suchmaschine handelt, die einen Besucher während einer Sitzung auf die Site verwiesen hat (wie vom Browser des Besuchers angegeben). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitdimensionen </td> 
   <td colname="col2"> Einfach </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Die Stunde, der Tag, die Stunde, die Woche, der Tag der Woche, des Monats, des Quartals oder des Jahres, in der/dem die Sitzung begonnen hat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensionen für Zeitberichte </td> 
   <td colname="col2"> Abgeleitet (Dimensionen "LastN"und "Umbenennen"basierend auf integrierten Zeitdimensionen) </td> 
   <td colname="col03"> Sitzung </td> 
   <td colname="col3"> Dimensionen wie z. B. Tage vor, Tage des letzten Monats, Tage der letzten Woche, Tage dieses Monats, Tage dieser Woche, Stunden von heute, Stunden von gestern, Letzte 12 Monate, Letzte 2 Monate, Letzte 2 Wochen, Letzte 24 Stunden, Letzte 3 Monate, Letzte 4 Wochen, Letzte 6 Monate, Letzte 7 Tage, Letzte 7 Tage und Heute, Letzte 8 Wochen, Letzte 9 Monate, Letzter Monat, Letzte Woche, Vor Monaten, diesem Monat, dieser Woche, dieser und der letzten 14 Tage, Dies und Letzte 6 Monate, Diese und Letzte 8 Wochen, Heute, Berichterstellung, Heute und Letzte 30 Tage, Wochen vor und Gestern bieten eine praktische Möglichkeit, einen Arbeitsbereich oder Bericht zu erstellen, der immer einen Teil der Daten im Datensatz anzeigt . Jede basiert auf dem Beginn einer Sitzung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Aus dem integrierten Dimensionen-URI übernommen </td> 
   <td colname="col03"> Seitenansicht </td> 
   <td colname="col3"> Der URI jeder angezeigten Seite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucherseitenansichten </td> 
   <td colname="col2"> Abgeleitet (MetricDim basierend auf der Metrik "Seitenansichten") </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Die Anzahl der bisherigen Seitenansichten für einen Besucher. Wenn Sie beispielsweise "3"in der Dimension "Besucherseitenansichten"auswählen, werden alle Besucher mit genau 3 Seitenansichten für alle Sitzungen ausgewählt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucherverweiser </td> 
   <td colname="col2"> Vom integrierten Dimensionsverweiser übernommen </td> 
   <td colname="col03"> Besucher. </td> 
   <td colname="col3"> Der Domänenname der zweiten Ebene der Website, die einen Besucher zum ersten Mal für die erste Sitzung an die Site verwiesen hat (wie vom Browser des Besuchers angegeben). </td> 
  </tr> 
 </tbody> 
</table>
