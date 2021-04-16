---
description: Das Traffic-Profil enthält die folgenden Metriken zur Identifizierung des Besucher-Traffics.
title: Traffic-Profil-Metriken
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
translation-type: tm+mt
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
   <td colname="col2">Formel: <span class="filepath"> page_Ansichten[no shift(None,page_Ansicht, Session,-1)]</span><p>Ebene: Ansicht der Seite </p></td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die auf jeder Seite die Site aufriefen. Diese Metrik wird nur über die Seitendimension ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausstiegsrate </td> 
   <td colname="col2">Formel: <span class="filepath"> Ausstiege/Page_Ansichten </span><p>Ebene: Ansicht der Seite </p></td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen, die die Site von jeder Seite verlassen haben. Die Metrik "Ausstiegsrate"kann nur über die Seitendimension ausgewertet werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausstiege </td> 
   <td colname="col2">Formel:<span class="filepath"> Page_Ansichten[no shift(None,Page_Ansicht, Session,1)] </span><p>Ebene: Ansicht der Seite </p></td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die die Site von jeder Seite verlassen haben. Diese Metrik wird nur über die Seitendimension ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI 90 </td> 
   <td colname="col2">Formel: <span class="filepath"> (raw(Besuchers) - ((raw(Besucher) + .69)^0.5 * 1.281551 - 1.2269))*(Besucher/raw(Besucher))</span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Ein Maß für die niedrigste Anzahl möglicher Besucher, wie von Insight berichtet. Mathematisch wird die niedrigste Anzahl von Besuchern mit einer Wahrscheinlichkeit von 90 % angegeben. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dauer der Ansicht der Seite </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sum (exact_page_duration, page_Ansicht)*0.1/page_Ansichten[any exact_page_duration]</span></p> <p>Ebene: Ansicht der Seite </p> </td> 
   <td colname="col3"> Die durchschnittliche Dauer (MM:SS), die auf einer bestimmten Seite oder Seitengruppe verbracht wurde. Diese Metrik wird nur über die Seitendimension ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ansichten pro Sitzung </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Page_Ansichten/ (Sitzungen nach Page_Ansicht) </span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die durchschnittliche Anzahl der Seitensitzungen mit Ansichten pro Ansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seitenansichten </td> 
   <td colname="col2">Formel: <span class="filepath"> sum(One, Page_Ansicht)</span><p>Ebene: Ansicht der Seite </p></td> 
   <td colname="col3"> Die Anzahl der Ansichten. Eine Ansicht ist eine Anforderung für eine definierte Seite (der Zugriff auf Bilder und andere Arten gefilterter Inhalte wird nicht gezählt). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ansichten für Seitenteile </td> 
   <td colname="col2">Formel: <span class="filepath"> Page_Ansichten/total(Page_Ansichten) </span><p>Ebene: Ansicht der Seite </p></td> 
   <td colname="col3"> Der Prozentsatz der Ansichten der Seite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Teil der Sitzungen </td> 
   <td colname="col2">Formel: <span class="filepath"> Sitzungen/total(Sitzungen)</span><p>Ebene: Sitzung </p></td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher </td> 
   <td colname="col2">Formel: <span class="filepath"> Besucher/total(Besucher) </span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Der Prozentsatz der Besucher. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct Referrer-Besucher </td> 
   <td colname="col2"> <p>Formel: Referred_Besuchers/Besucher </p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Der Prozentsatz der Besucher, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer Sitzungen </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen[Werber&lt;&gt; 'Keine' und Werber&lt;&gt;'Lesezeichen']</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Sitzungen, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer-Besucher </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besuchers[Besucher_ Werber&lt;&gt;'Keine' und Besucher_Werber&lt;&gt;'Lesezeichen']</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die von einer anderen Site auf diese Site verwiesen wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Treue </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen[Umschalt(Keine,Sitzung,Besucher,1) = ""]/Sitzungen</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Der Prozentsatz der Sitzungen, bei denen es sich nicht um die letzten Sitzungen des Besuchers handelt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungsdauer </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> (Summe (Exakt_Seitendauer, Sitzung)*.1/Sitzungen)[Sitzung_ Dauer &lt;= '01:00:00']</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3">Die durchschnittliche Dauer (MM:SS), die ein Besucher in einer Sitzung verbringt. <p><p>Hinweis: Sie können diese Metrik mit der Funktion <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Segmentexport</a> verwenden. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungen nach Ansicht der Seite </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sitzungen nach Page_Ansicht</span></p> <p> Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Sitzungen mit einer Ansicht der Seite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungen </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sum(One, Session)</span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Anzahl der Besucher-Sitzungen. Eine Sitzung ist ein Zeitraum der Aktivität für einen Besucher einer Website. Einzelne Sitzungen für jeden Besucher werden mithilfe von Cookies, Timeouts und anderen Heuristiken identifiziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI 80 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> trust(Sessions) * 1.281551 / Sitzungen</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Ein Maß für die Konfidenz der Sessions-Metrik, wie von Data Workbench gemeldet. Mathematisch ist es ein +/- Prozentsatz, der den Bereich angibt, in dem die tatsächliche Antwort 80 % der Zeit liegt. Eine Verdopplung des SCI80-Prozentsatzes ergibt einen Bereich, in dem die tatsächliche Antwort 99 % der Zeit betragen wird. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI 90 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> (((raw(Besucher) + .68)^0.5 * 1.281551 + 1.2269) + raw(Besucher))*( Besucher/raw(Besucher))</span></p> <p>Ebene: Besucher </p> </td> 
   <td colname="col3"> Ein Maß für die höchste Anzahl möglicher Besucher, wie von Insight berichtet. Mathematisch wird die höchste Anzahl von Besuchern mit einer 90%igen Wahrscheinlichkeit angegeben. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI 80 </td> 
   <td colname="col2">Formel: <span class="filepath"> ((raw(Besucher) + .68)^0.5 * 1.281551 + 1.2269) / raw(Besucher)</span><p>Ebene: Besucher </p></td> 
   <td colname="col3"> Ein Maß für die Konfidenz der Metrik "Besucher", wie von Insight berichtet. Mathematisch ist es ein +/- Prozentsatz, der den Bereich angibt, in dem die tatsächliche Antwort 80 % der Zeit liegt. Eine Verdopplung des VCI80-Prozentsatzes ergibt einen Bereich, in dem die tatsächliche Antwort 99 % der Zeit beträgt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher nach Ansicht der Seite </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besucher nach Page_Ansicht</span></p> <p>Ebene: Ansicht der Seite </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher mit einer Ansicht. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucher nach Sitzung </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besucher nach Sitzung </span></p> <p>Ebene: Sitzung </p> </td> 
   <td colname="col3"> Die Anzahl der Besucher, die eine Sitzung hatten. </td> 
  </tr> 
 </tbody> 
</table>
