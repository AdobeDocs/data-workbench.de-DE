---
description: Dimension-Ausdrücke werden nie allein verwendet, können jedoch überall dort verwendet werden, wo eine Dimension in einer Metrik oder einem Filterausdruck benötigt wird.
title: Syntax für Ausdrücke zu Dimensionen
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Syntax für Ausdrücke zu Dimensionen{#syntax-for-dimension-expressions}

Dimension-Ausdrücke werden nie allein verwendet, können jedoch überall dort verwendet werden, wo eine Dimension in einer Metrik oder einem Filterausdruck benötigt wird.

1. Unterstrichene Wörter sollten wörtlich in den Ausdruckstext eingegeben werden.
1. Das Formular `{TEXT}?` stellt optionalen Text dar.
1. Das Formular `{TEXT}*` stellt Text dar, der null oder öfter vorkommen kann.
1. Das Formular `{A | B | C |...}` stellt Text dar, der aus genau einer der angegebenen Optionen besteht, z. B. A, B oder C...
1. Das Formular `[A,B)` stellt einen Zahlenbereich dar, von A bis B, jedoch nicht B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Eine Kennung verweist auf eine benannte Dimension. Die Regeln für rechtliche Kennungen finden Sie unter <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntax für Kennungen </a>. </p> <p>Beispiel: Sitzungen[ Sitzungsnummer = "1" ] ist die Anzahl der Sitzungen mit der Sitzungsnummer "1". Sitzungsnummer ist eine benannte Dimension, auf die durch die Kennung verwiesen wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimension) </p> </td> 
   <td colname="col2"> <p>Das Ergebnis von (Dimension) ist dasselbe wie das Ergebnis der Dimension. In Klammern wird die Reihenfolge der Vorgänge in einem Ausdruck angegeben. </p> <p>Beispiel: Sitzungen[ (Seite) = "/home" ] ist die Anzahl der Sitzungen, die die Seite "/home"besuchen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Festlegen nach Ebene </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, die dieselben Elemente wie die Dimension Dim hat, sich jedoch über die Dimensionsebene auf andere Dimensionen bezieht. </p> <p>Insbesondere bezieht sich ein Element der neuen Dimension auf dieselben Elemente der Ebene wie dasselbe Element von Dim und bezieht sich auf die Elemente jeder anderen Dimension, die sich auf eines dieser Elemente der Ebene beziehen. </p> <p>Beispiel: Sitzungen[ (Seite nach Besucher)="/home" ] ist die Anzahl der Sitzungen von Besuchern, die die Seite "/home"besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, die dieselben Elemente wie die Dimension Dim hat. Das zehnte Element der Dimensionsebene bezieht sich auf dasselbe Element der neuen Dimension wie das Element des Dim, auf das sich das Element e+n auf Ebene bezieht, sofern die Elemente der Stufe eth und e+n dasselbe Element der Dimensionengruppe betreffen. </p> <p>Beispiel: Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] ist die Anzahl der Seitenansichten, für die die nächste in derselben Sitzung angezeigte Seite "/home"ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Ähnlich wie shift(Dim,Level,Group,N), mit der Ausnahme, dass bei leeren Werten in der Dimension diese übersprungen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Definiert eine Dimension, die Elemente der Ebene anhand einer Liste von Filtern klassifiziert. Die Elemente der neuen Dimension sind die Zeichenfolgen, die als Argumente angegeben werden. Jedes Element von Level bezieht sich auf das erste Element der Segmentdimension, dessen Filter das Element Level zulässt. Dies ähnelt der Segmentvisualisierung. </p> <p>Beispiel: segment(Visitor, "Einmalige Besucher"-&gt; Visitor_Sessions = 1, "Sehr treue Besucher"-&gt; Visitor_Sessions &gt; 10, "Alle anderen"-&gt; true) erstellt eine Dimension, die Besucher in drei Gruppen einteilt. Einmalige Besucher sind diejenigen mit nur einer Sitzung, Sehr treue Besucher sind diejenigen mit mehr als zehn Sitzungen und alle anderen Besucher haben den Wert "Sehr treue Besucher". Alle anderen." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Größe}? }?) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, deren Elemente Bereiche von Zahlen sind (mit fester Größe, z. B. [0-9], [10-19],...). Elemente der Ebene beziehen sich auf das Element des Behälterdiagramms, dessen Bereich den Wert der Metrik für dieses Element der Ebene enthält. Format ist die Zeichenfolge im Druckformat, die zum Formatieren der Elemente der Metrik verwendet wird. </p> <p>Beispiel: Wenn "Page_Duration_Minutes"eine Dimension auf Seitenansichtsebene ist, die die Anzahl der auf jeder Seite verbrachten Minuten darstellt, ist "bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) eine Dimension auf Sitzungsebene, die die Anzahl der in jeder Sitzung verbrachten Minuten darstellt. Ihre Elemente sind 5-minütige Intervalle <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start ist der Startwert des ersten Intervalls (Standard: 0) und Größe ist die Größe des Intervalls (Standard: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, deren Elemente die angegebenen ElementName-Zeichenfolgen sind und die mit den entsprechenden Sätzen von Präfix-Zeichenfolgen verknüpft sind. Elemente der Ebene beziehen sich auf das Element des Präfixes dim, das mit dem längsten Präfix verknüpft ist, das mit dem Namen des angegebenen Elements der Ebene übereinstimmt. Präfixe, die mit dem Sonderzeichen '$' enden, müssen exakt übereinstimmen. </p> <p>Beispielsweise erstellt prefix(URI, "Products"-&gt; ("/products/"), "Services"-&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Alles andere" -&gt; ("/")) eine Dimension, die URIs in die vier aufgelisteten Kategorien klassifiziert. Der Effekt auf verschiedene Seiten sieht wie folgt aus: </p> <p>/products/warranty.html geht in die Garantie, da es genau mit dem Präfix /products/warranty.html$ übereinstimmt. </p> <p>/products/cars/specialcar.html Wechselt zu "Products", da es mit dem Präfix /products/ und nicht mehr mit dem Präfix übereinstimmt </p> <p>/products/service/something.html geht in Dienste über, da es mit dem Präfix /products/service/ übereinstimmt, das länger als das Präfix /products/ ist. </p> <p>/companyinfo/aboutus.html Wechselt in die Kategorie "Alles andere", da das einzige Präfix, das damit übereinstimmt, "/"ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Erstellen von Dimensionen mit Latenzzeit </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, deren Elemente alle Kombinationen (das "kartesische Produkt") der Elemente der angegebenen Dimensionen sind. Der Name jedes Elements besteht aus der Verkettung der entsprechenden Elemente in den Eingabedimensionen, getrennt durch die angegebene Trennzeichenfolge. </p> <p>Wenn die Dimension D1 beispielsweise die Elemente {"a", "b"} und die Dimension D2 die Elemente {"x", "y"} aufweist, hat das kartesische Produkt("-", D1, D2) die Elemente {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Beachten Sie, dass intern jede der Eingabedimensionen so behandelt wird, als wäre die Anzahl der zugehörigen Elemente die nächsthöhere Leistung von zwei. Dies führt dazu, dass das kartesische Produkt einige Platzhalterelemente aufweist. Bei Verwendung der Data Workbench-API können diese Elemente je nach Ausgabeformat entweder leer gelassen oder als "#nnn" angezeigt werden, wobei nn die Ordinalität des Elements ist (und vom Client ignoriert werden sollte). </p> <p>Wenn beispielsweise im obigen Beispiel D2 die drei Elemente {"x", "y", "z"} hätte, würde es so behandelt, als hätte es vier Elemente, und das kartesische Produkt hätte die Elemente {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Wenn keine Dimensionen angegeben werden, ist das Ergebnis eine Dimension mit einem Element, "#0", das der Dimension "Keine"entspricht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Bezieht sich auf eine bereits vorhandene Dimension: der nächstzählbare Vorgänger von Dim im Schema. Beispielsweise ist "nächstgelegene zählbare(URI)"identisch mit "Page_View". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(im,count) </p> </td> 
   <td colname="col2"> <p>Definiert eine normalisierte Dimension aus der denormalen Dimension Dim mit bis zu Count -Elementen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension mit einer Teilmenge der Elemente der Dimension Dim, deren Elemente Zeitscheiben darstellen, z. B. Tage, Wochen oder Jahre. </p> <p>Die Untergruppe ist ein Bereich um einen bestimmten Zeitraum, den Wert der konstanten Metrik TimeMetric, die als Zeitwert in Sekunden seit Mitternacht UTC des 1. Januar 1970 interpretiert wird. Der Bereich enthält Count -Elemente, von denen das letzte Offset -Elemente nach dem Element des angegebenen Dim ist, dessen Name das Ergebnis der Formatierung des Metrikwerts mit der angegebenen FormatString-Zeichenfolge ist. FormatString verwendet dieselben "%"-Escapes wie die standardmäßige C-Bibliotheksfunktion strftime. </p> <p>Wenn trimToData auf "true"gesetzt ist, werden alle Elemente am Anfang der resultierenden Dimension entfernt, die vor dem Anfang von Dim liegen würden. Wenn der Wert "false"ist, wird immer die genaue Anzahl der von "Count"angegebenen Elemente angegeben. Beachten Sie, dass es immer Elemente am Ende der resultierenden Dimension geben kann, die sich nicht in Dim befinden. </p> <p>Der optionale WeekStart, sofern angegeben, muss einer von { "Sun", "Mon", "Tue", "Med", "Thu", "Fri", "Sat" } sein. Er ändert TimeMetric, indem er es auf das neueste Vorkommen dieses Wochentags zurückverschiebt. </p> <p>Beispiel: Wenn die Woche die Elemente { "10/03/10", "10/10/10", ..., "12/12/10" } und die integrierte As-Of-Metrik den Wert 1292348109 hat (entspricht einer Zeit in der Mitte des 14. Dezember, 2 010), dann letzte n(Woche, As_Of, "%m/%d/%y", 4, 0, false, "Sun") definiert die Dimension mit den Elementen { "12/12/10", "12/19/10", "23/10", "12/30/10" } </p> <p>Beispiel 2: Wenn die Dimension "Woche"nur die Elemente {"19.12.10", "12/26/10", ..., "30.11.11"} enthält und die Metrik Ausführungsdatum wie oben lautet, dann gibt last n(Week, As_Of, "%m/%d/%y", 4, 0, true, "Sun") a) Dimension mit Elementen {"19.12.10", "23.12.10", "30.12.10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension mit einer Teilmenge der Elemente von Dim, deren Elemente Tage darstellen. Die Untergruppe ist ein Bereich um einen bestimmten Zeitraum, den Wert der konstanten Metrik TimeMetric, die als Zeitwert in Sekunden seit Mitternacht UTC des 1. Januar 1970 interpretiert wird. Der Bereich enthält die Elemente, die den einzelnen Tagen in den nMonaten vor der angegebenen Zeit entsprechen. Wenn includeThisMonth auf "true"gesetzt ist, enthält der Bereich auch jeden Tag des Monats, der die angegebene Uhrzeit enthält. </p> <p>FormatString gibt die Formatierung der Elemente von Dim an, wobei "%"wie in der standardmäßigen C-Bibliotheksfunktion strftime als Escape-Zeichen verwendet wird. </p> <p>Wenn trimToData auf "true"gesetzt ist, werden alle Elemente am Anfang der resultierenden Dimension entfernt, die vor dem Anfang von Dim liegen würden. Wenn der Wert "false"ist, wird immer die genaue Anzahl der von "Count"angegebenen Elemente angegeben. Beachten Sie, dass es immer Elemente am Ende der resultierenden Dimension geben kann, die sich nicht in Dim befinden. </p> <p>Beispiel: Wenn Day die Elemente { "01/01/10", "01/02/10", ..., "12/31/10" } aufweist und die integrierte As-Of-Metrik den Wert 1292348109 hat (entspricht einer Zeit in der Mitte des 14. Dezember 20 10), dann haben Tage der vorherigen Monate(Tag, As_Of, "%m/%d/%y", 2, false, false) die Elemente { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Ähnlich wie Tage der vorherigen Monate, mit der Ausnahme, dass die Elemente nur den Tagen des gleichen Monats entsprechen, der durch die TimeMetric angegeben wurde. Wenn "allMonth"wahr ist, gibt es ein Element für jeden Tag des entsprechenden Monats. Andernfalls werden nur Tage vom ersten des entsprechenden Monats bis zum Tag mit der angegebenen Uhrzeit Teil der Dimension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Ähnlich wie Tage der vorherigen Monate, mit dem Unterschied, dass die Elemente den Tagen der Monate nach dem Monat und nicht vor dem Monat entsprechen, der die durch die TimeMetric angegebene Uhrzeit enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, DaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension mit einer Teilmenge der Elemente von Dim, deren Elemente Stunden darstellen. Die Untergruppe ist ein Bereich um einen bestimmten Zeitraum, den Wert der konstanten Metrik TimeMetric, die als Zeitwert in Sekunden seit Mitternacht UTC des 1. Januar 1970 interpretiert wird. Der Bereich enthält die Elemente, die jeder Stunde des Tages nDaysForward nach dem Tag entsprechen, der die durch die TimeMetric festgelegte Zeit enthält. </p> <p>FormatString gibt die Formatierung der Elemente von Dim an, wobei "%"wie in der standardmäßigen C-Bibliotheksfunktion strftime als Escape-Zeichen verwendet wird. Die Formatzeichenfolge sollte immer eine Zeichenfolge ausgeben, die Mitternacht am Anfang des Tages der übergebenen Zeit darstellt. </p> <p>Wenn trimToData auf "true"gesetzt ist, werden alle Elemente am Anfang der resultierenden Dimension entfernt, die vor dem Anfang von Dim liegen würden. Wenn der Wert "false"ist, wird immer die genaue Anzahl der von "Count"angegebenen Elemente angegeben. Beachten Sie, dass es immer Elemente am Ende der resultierenden Dimension geben kann, die sich nicht in Dim befinden. </p> <p>Beispiel: Wenn "Stunde"die Elemente { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" } hat und die integrierte As-Of-Metrik den Wert 1292348 hat. 109 (entspricht einer Zeit in der Mitte des 14. Dezember 2010), dann hat Stunden des Tages(Hour, As_Of, "%x 00:00", 0, false) Elemente { "12/12/10 00:00", "12/12/10 01:0", ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
