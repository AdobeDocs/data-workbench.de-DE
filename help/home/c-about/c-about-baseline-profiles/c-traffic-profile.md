---
description: Das Traffic-Profil enthält die folgenden Metriken zur Identifizierung des Besucher-Traffics.
solution: Analytics
title: Traffic-Profilmetriken
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Traffic-Profilmetriken{#traffic-profile-metrics}

Das Traffic-Profil enthält die folgenden Metriken zur Identifizierung des Besucher-Traffics.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Metrikformel und -stufe </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Einträge </td> 
   <td colname="col2">Formel: <span class="filepath"> Page_Views[no shift(None,page_View, session,-1)]</span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die auf jeder Seite die Site aufriefen. Diese Metrik wird nur über die Seitendimension ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausstiegsrate </td> 
   <td colname="col2">Formel: <span class="filepath"> Ausstiege/Seitenansichten </span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen, die die Site von jeder Seite verlassen haben. Die Metrik "Ausstiegsrate"kann nur über die Seitendimension ausgewertet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausstiege </td> 
   <td colname="col2">Formel:<span class="filepath"> Page_Views[no shift(None,page_View, session,1)] </span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die die Site von jeder Seite verlassen haben. Diese Metrik wird nur über die Seitendimension ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formel: <span class="filepath"> (raw(Visitors) - (raw(Visitors) + .69)^0.5 * 1.281551 - 1.2269))*(Visitors/raw(Visitors))</span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Ein Maß für die niedrigste Anzahl möglicher Besucher, wie von Insight berichtet. Mathematisch gibt es die niedrigste Anzahl von Besuchern mit einer 90%igen Wahrscheinlichkeit an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dauer der Seitenansicht </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sum (exact_page_duration, page_view)*0.1/Page_Views[any exact_page_Duration]</span></p> <p>Ebene: Seitenansicht </p> </td> 
   <td colname="col3"> Die durchschnittliche Dauer (MM:SS), die auf einer bestimmten Seite oder Seitengruppe verbracht wurde. Diese Metrik wird nur über die Seitendimension ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten pro Sitzung </td> 
   <td colname="col2"> <p>Formel: " <span class="filepath"> Page_Views/"(Sitzungen nach "Page_View") </span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die durchschnittliche Anzahl der Seitenansichten in jeder Sitzung, die Seitenansichten haben. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten </td> 
   <td colname="col2">Formel: <span class="filepath"> sum(One, Page_View)</span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Die Anzahl der Seitenansichten. Eine Seitenansicht ist eine Anforderung für eine definierte Seite (der Zugriff auf Bilder und andere Arten gefilterter Inhalte werden nicht gezählt). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anteil der Seitenansichten </td> 
   <td colname="col2">Formel: <span class="filepath"> Page_Views/total(page_Views) </span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Der Prozentsatz der Seitenansichten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Teil der Sitzungen </td> 
   <td colname="col2">Formel: Sitzungen/ <span class="filepath"> insgesamt(Sitzungen)</span><p>Ebene: Sitzung </p></td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anteil der Besucher </td> 
   <td colname="col2">Formel: <span class="filepath"> Besucher/insgesamt(Besucher) </span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Der Prozentsatz der Besucher. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct-Referrer </td> 
   <td colname="col2"> <p>Formel: Referred_Visitors/Visitors </p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Der Prozentsatz der Besucher, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer Sitzungen </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen[Verweis&lt;&gt; 'Keine' und Verweis&lt;&gt;'Lesezeichen']</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer-Besucher </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Visitor[Visitor_Referrer&lt;&gt;'None' und Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Treue </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen[Wechsel(Keine,Sitzung,Besucher,1) = ""]/Sitzungen</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen, bei denen es sich nicht um die letzten Sitzungen der Besucher handelt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsdauer </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> (Summe (Exakt_Seitendauer, Sitzung)*.1/Sitzungen)[Sitzungsdauer &lt;= '01:00:00']</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3">Die durchschnittliche Dauer (MM:SS), die ein Besucher in einer Sitzung verbringt. <p><p>Hinweis: Sie können diese Metrik mit der Funktion <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Segmentexport</a> verwenden. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungen nach Seitenansicht </td> 
   <td colname="col2"> <p>Formel: Sitzungen <span class="filepath"> nach Seite_Ansicht</span></p> <p> Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Sitzungen mit Seitenansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungen </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sum(One, Session)</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Anzahl der Besuchersitzungen. Eine Sitzung ist ein Zeitraum der Aktivität für einen Besucher einer Website. Einzelne Sitzungen für jeden Besucher werden mithilfe von Cookies, Timeouts und anderen Heuristiken identifiziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Konfidenz(Sitzungen) * 1.281551 / Sitzungen</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Ein Maß für die Konfidenz der Sessions-Metrik, wie von Data Workbench gemeldet. Mathematisch ist es ein +/- Prozentsatz, der den Bereich angibt, in dem die tatsächliche Antwort 80 % der Zeit liegt. Eine Verdopplung des SCI80-Prozentsatzes ergibt einen Bereich, in dem die tatsächliche Antwort 99 % der Zeit betragen wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors))</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Ein Maß für die höchste Anzahl möglicher Besucher, wie von Insight berichtet. Mathematisch gibt es die höchste Anzahl von Besuchern mit einer 90%igen Wahrscheinlichkeit an. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formel: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Ein Maß für die Konfidenz der Besuchermetrik, wie von Insight berichtet. Mathematisch ist es ein +/- Prozentsatz, der den Bereich angibt, in dem die tatsächliche Antwort 80 % der Zeit liegt. Eine Verdopplung des VCI80-Prozentsatzes ergibt einen Bereich, in dem die tatsächliche Antwort 99 % der Zeit beträgt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher nach Seitenansicht </td> 
   <td colname="col2"> <p>Formel: Besucher <span class="filepath"> nach Seite_Ansicht</span></p> <p>Ebene: Seitenansicht </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher mit Seitenansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher nach Sitzung </td> 
   <td colname="col2"> <p>Formel: Besucher <span class="filepath"> nach Sitzung </span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die eine Sitzung hatten. </td> 
  </tr> 
 </tbody> 
</table>

