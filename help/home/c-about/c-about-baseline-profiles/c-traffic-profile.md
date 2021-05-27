---
description: Das Traffic-Profil enthält die folgenden Metriken zur Identifizierung des Besucher-Traffics.
title: Traffic-Profil-Metriken
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# Traffic-Profil-Metriken{#traffic-profile-metrics}

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
   <td colname="col1"> Einstiege </td> 
   <td colname="col2">Formel: <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die auf jeder Seite auf die Site gelangten. Diese Metrik wird nur über die Dimension Seite ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausstiegsrate </td> 
   <td colname="col2">Formel: <span class="filepath"> Ausstiege/Seitenansichten </span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen, die die Site von jeder Seite verlassen haben. Die Metrik Ausstiegsrate kann nur über die Seitendimension ausgewertet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausstiege </td> 
   <td colname="col2">Formel:<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die die Site von jeder Seite verlassen haben. Diese Metrik wird nur über die Dimension Seite ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI 90 </td> 
   <td colname="col2">Formel: <span class="filepath"> (raw(Visitors) - ((raw(Visitors) + .69)^0.5 * 1.281551 - 1.2269)*(Visitors/raw(Visitors))</span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Ein Maß für die niedrigste Anzahl möglicher Besucher, wie von Insight gemeldet. Mathematisch wird die niedrigste Anzahl von Besuchern mit einer 90-%-Wahrscheinlichkeit angegeben. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichtsdauer </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sum (exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Ebene: Seitenansicht </p> </td> 
   <td colname="col3"> Die durchschnittliche Dauer (MM:SS), die auf einer bestimmten Seite oder Gruppe von Seiten verbracht wurde. Diese Metrik wird nur über die Dimension Seite ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten pro Sitzung </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Page_Views/ (Sitzungen nach Page_View) </span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die durchschnittliche Anzahl der Seitenansichten in jeder Sitzung mit Seitenansichten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten </td> 
   <td colname="col2">Formel: <span class="filepath"> sum(One, Page_View)</span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Die Anzahl der Seitenansichten. Eine Seitenansicht ist eine Anforderung für eine definierte Seite (der Zugriff auf Bilder und andere Arten gefilterter Inhalte werden nicht gezählt). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Teil der Seitenansichten </td> 
   <td colname="col2">Formel: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Ebene: Seitenansicht </p></td> 
   <td colname="col3"> Der Prozentsatz der Seitenansichten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsprozentsatz </td> 
   <td colname="col2">Formel: <span class="filepath"> Sitzungen/total(Sitzungen)</span><p>Ebene: Sitzung </p></td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucheranteil </td> 
   <td colname="col2">Formel: <span class="filepath"> Besucher/total(Visitors) </span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Der Prozentsatz der Besucher. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer Besucher </td> 
   <td colname="col2"> <p>Formel: Referred_Visitors/Visitors </p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Der Prozentsatz der Besucher, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrersitzungen </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen[Referrer&lt;&gt; 'None' und Referrer&lt;&gt;'bookmarks']</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer-Besucher </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besucher[Visitor_ Referrer&lt;&gt;'None' und Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Treue </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen[shift(None,Ses sion,Visitor,1) = ""] / Sitzungen</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen, die nicht die Besucher der letzten Sitzungen sind. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsdauer </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> (Summe (Exact_Page_Duration, Sitzung)*.1/Sitzungen)[Sitzung_ Dauer &lt;= '01:00:00']</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3">Die durchschnittliche Dauer (MM:SS), die ein Besucher in einer Sitzung verbringt. <p><p>Hinweis: Sie können diese Metrik mit der Funktion <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Segmentexport</a> verwenden. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungen nach Seitenansicht </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen nach Page_View</span></p> <p> Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Sitzungen mit Seitenansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungen </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sum(One, Session)</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Zählung der Besuchersitzungen. Eine Sitzung ist ein Aktivitätszeitraum für einen Besucher einer Website. Einzelne Sitzungen für jeden Besucher werden mithilfe von Cookies, Timeouts und anderen Heuristiken identifiziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> confidence(sitzungen) * 1.281551 / sitzungen</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Ein Maß für die Konfidenz der Sitzungsmetrik, wie von Data Workbench gemeldet. Mathematisch ist dies ein +/- Prozentsatz, der den Bereich angibt, in dem die tatsächliche Antwort 80 % der Zeit liegt. Als Faustregel gilt, dass die Verdoppelung des SCI80-Prozentsatzes einen Bereich ergibt, in dem die tatsächliche Antwort 99 % der Zeit beträgt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI 90 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors))</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Ein Maß für die höchste Anzahl möglicher Besucher, wie von Insight gemeldet. Mathematisch wird die höchste Anzahl von Besuchern mit einer 90-%-Wahrscheinlichkeit angegeben. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI 80 </td> 
   <td colname="col2">Formel: <span class="filepath"> (raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Ein Maß für die Konfidenz der Besuchermetrik, wie in Insight angegeben. Mathematisch ist dies ein +/- Prozentsatz, der den Bereich angibt, in dem die tatsächliche Antwort 80 % der Zeit liegt. Als Faustregel gilt, dass die Verdoppelung des VCI80-Prozentsatzes einen Bereich ergibt, in dem die tatsächliche Antwort 99 % der Zeit beträgt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher nach Seitenansicht </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besucher nach Seitenansicht</span></p> <p>Ebene: Seitenansicht </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die einen Seitenaufruf hatten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher nach Sitzung </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besucher nach Sitzung </span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die eine Sitzung hatten. </td> 
  </tr> 
 </tbody> 
</table>
