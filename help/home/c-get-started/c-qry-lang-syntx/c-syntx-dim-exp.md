---
description: Dimension-Ausdruck werden nie allein verwendet, können aber überall dort verwendet werden, wo eine Dimension in einem Metrik- oder Filter-Ausdruck benötigt wird.
title: Syntax für Ausdrücke zu Dimensionen
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Syntax für Ausdrücke zu Dimensionen{#syntax-for-dimension-expressions}

Dimension-Ausdruck werden nie allein verwendet, können aber überall dort verwendet werden, wo eine Dimension in einem Metrik- oder Filter-Ausdruck benötigt wird.

1. Unterstrichene Wörter sollten wörtlich in den Ausdruck eingegeben werden.
1. Das Formular `{TEXT}?` stellt optionalen Text dar.
1. Das Formular `{TEXT}*` stellt Text dar, der null oder mehr Mal auftreten kann.
1. Das Formular `{A | B | C |...}` stellt Text dar, der aus genau einer der angegebenen Optionen besteht, z. B. A oder B oder C....
1. Das Formular `[A,B)` stellt einen Zahlenbereich dar, von A bis B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Ein Bezeichner verweist auf eine benannte Dimension. Die Regeln für rechtliche Bezeichner finden Sie unter <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntax für Bezeichner </a>. </p> <p>Beispiel: Sitzungen[ Sitzung_Nummer = "1" ] ist die Anzahl der Sitzungen mit der Sitzungsnummer "1". Session Number ist eine benannte Dimension, auf die durch den Bezeichner verwiesen wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimension) </p> </td> 
   <td colname="col2"> <p>Das Ergebnis von (Dimension) ist dasselbe wie das Ergebnis der Dimension. Klammern geben die Reihenfolge der Vorgänge in einem Ausdruck an. </p> <p>Beispiel: Sessions[ (Seite) = "/home" ] ist die Anzahl der Sitzungen, die die Seite "/home"besuchen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim nach Ebene </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, die dieselben Elemente wie die Dimension Dim hat, sich jedoch auf andere Dimensionen über die Dimensionsebene bezieht. </p> <p>Insbesondere bezieht sich ein Element der neuen Dimension auf dieselben Elemente der Ebene wie das gleiche Element von Dim und bezieht sich auf die Elemente jeder anderen Dimension, die sich auf eines dieser Elemente der Ebene beziehen. </p> <p>Beispiel: Sessions[ (Seite nach Besucher)="/home" ] ist die Anzahl der Sitzungen von Besuchern, die die Seite "/home"besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,group,N) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension mit denselben Elementen wie die Dimension Dim. Das zehnte Element der Dimensionsebene bezieht sich auf dasselbe Element der neuen Dimension wie das Element des Dim, das sich auf das e+n-Element des Levels bezieht, sofern sich die eth- und e+N-Elemente der Ebene auf dasselbe Element der Dimensionengruppe beziehen. </p> <p>Beispiel: Page_Ansichten[ shift(Page, Page_Ansicht, Session, 1)="/home" ] ist die Anzahl der Ansichten, für die die nächste in derselben Sitzung angezeigte Seite "/home"ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,group,N) </p> </td> 
   <td colname="col2"> <p>Ähnlich wie shift(Dim,Level,Group,N), mit der Ausnahme, dass bei leeren Werten in der Dimension diese übersprungen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Definiert eine Dimension, die Elemente der Ebene basierend auf einer Liste von Filtern klassifiziert. Die Elemente der neuen Dimension sind die Zeichenfolgen, die als Argumente angegeben werden. Jedes Element der Ebene bezieht sich auf das erste Element der Segmentdimension, deren Filter das Element der Ebene zulässt. Dies ähnelt der Segmentvisualisierung. </p> <p>Beispiel: segment(Besucher, "Einmalige Besucher" -&gt; Besucher_Sitzungen = 1, "Sehr loyale Besucher" -&gt; Besucher_Sitzungen &gt; 10, "Alle anderen" -&gt; True) erstellt eine Dimension, die Besucher in drei Gruppen einteilt. Einmalige Besucher sind nur mit einer Sitzung, sehr loyale Besucher mit mehr als zehn Sitzungen und alle anderen Besucher haben den Wert "Sehr treue"und Alle anderen." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Beginn {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, deren Elemente Zahlenbereiche sind (von fester Größe, z. B. [0-9], [10-19],...). Elemente der Ebene beziehen sich auf das Element des Behälterdims, dessen Bereich den Wert der Metrik für das Element der Ebene enthält. Format ist die Zeichenfolge im Druckformat, die zum Formatieren der Elemente der Metrik verwendet wird. </p> <p>Beispiel: Wenn Page_Duration_Minutes eine Dimension auf Seitenebene ist, die die Anzahl der auf jeder Ansicht verbrachten Minuten darstellt, dann ist bucket(Session, sum(Page_Duration_Minutes, Page_Ansicht), 100, "%0.0f minutes", 0, 5) eine Dimension auf Sitzungsebene, die die Anzahl der in jeder Sitzung verbrachten Minuten darstellt. seine Elemente sind 5-minütige Intervalle <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Beginn ist der Startwert des ersten Intervalls (Standard: 0) und Größe ist die Größe des Intervalls (Standard: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}*)}*) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, deren Elemente die angegebenen ElementName-Zeichenfolgen sind und die mit den entsprechenden Sätzen von Präfix-Zeichenfolgen verknüpft sind. Elemente der Ebene beziehen sich auf das Element des Präfix dim, das mit dem längsten Präfix verknüpft ist, das mit dem Namen des angegebenen Elements der Ebene übereinstimmt. Präfixe, die mit dem Sonderzeichen '$' enden, müssen exakt übereinstimmen. </p> <p>Beispielsweise erstellen prefix(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Alles andere" -&gt; ("/")) eine Dimension, die URIs in die vier aufgelisteten Kategorien klassifiziert. Die Auswirkungen auf verschiedene Seiten sind wie folgt: </p> <p>/products/warranty.html geht in die Gewährleistung, da es genau mit dem Präfix /products/warranty.html$ übereinstimmt. </p> <p>/products/cars/specialcar.html geht in Produkte über, da es mit dem Präfix "/products/"und nicht mehr mit dem Präfix "prefix"übereinstimmt </p> <p>/products/service/something.html Wechselt in Dienste, da es mit dem Präfix "/products/service/"übereinstimmt, das länger als das Präfix "/products/"ist. </p> <p>/companyinfo/aboutus.html gelangt in die Kategorie "Alles andere", da das einzige Präfix, das ihm zugeordnet ist, "/"ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Erstellen von Dimensionen mit Latenz </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, deren Elemente alle Kombinationen (das kartesische Produkt) der Elemente der angegebenen Dimensionen sind. Der Name jedes Elements wird aus der Verkettung der entsprechenden Elemente in den Eingabedimensionen, getrennt durch die angegebene Trennzeichenfolge, gebildet. </p> <p>Wenn beispielsweise die Dimension D1 Elemente {"a", "b"} und die Dimension D2 die Elemente {"x", "y"} enthält, hat das kartesische Produkt("-", D1, D2) die Elemente {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Beachten Sie, dass intern jede der Eingabedimensionen so behandelt wird, als ob die Anzahl der zugehörigen Elemente die nächsthöhere Potenz von zwei ist. Dies führt dazu, dass das kartesische Produkt einige Dummy-Elemente enthält. Bei Verwendung der Data Workbenchs-API können diese Elemente abhängig vom Ausgabeformat gebunden werden oder als "#nnn"angezeigt werden, wobei nn die Ordinalform des -Elements ist (und vom Client ignoriert werden sollte). </p> <p>Beispiel: Wenn D2 die drei Elemente {"x", "y", "z"} hätte, würde es so behandelt, als hätte es vier Elemente, und das kartesische Produkt hätte die Elemente {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7". </p> <p>Wenn keine Dimensionen angegeben werden, ist das Ergebnis eine Dimension mit einem Element, "#0", das der Dimension "Keine"entspricht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Bezieht sich auf eine bereits vorhandene Dimension: der nächste zählbare Vorfahren von Dim im Schema. Beispielsweise ist der nächste zählbare(URI) identisch mit page_Ansicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Definiert eine normalisierte Dimension aus der denormalen Dimension Dim mit bis zu zählenden Elementen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, die eine Untergruppe der Elemente der Dimension Dim hat, deren Elemente Zeitscheiben darstellen, z. B. Tage, Wochen oder Jahre. </p> <p>Die Untergruppe ist ein Bereich um eine angegebene Zeit, der Wert der konstanten Metrik TimeMetric, die als Zeitwert in Sekunden seit dem 1. Januar 1970 (UTC) um Mitternacht interpretiert wird. Der Bereich verfügt über Count-Elemente, von denen das letzte Offset-Elemente nach dem angegebenen Dim-Element ist, dessen Name das Ergebnis der Formatierung des Werts der Metrik mit der angegebenen FormatString-Zeichenfolge ist. FormatString verwendet die gleichen % Escapes wie die standardmäßige C-Bibliotheksfunktion strftime. </p> <p>Wenn trimToData den Wert "true"hat, werden alle Elemente am Anfang der resultierenden Dimension, die vor dem Anfang von Dim liegen, entfernt. Wenn der Wert "false"ist, gibt es immer die exakte Anzahl von Elementen, die von "Count"angegeben werden. Beachten Sie, dass es immer Elemente am Ende der resultierenden Dimension geben kann, die sich nicht wirklich in Dim befinden. </p> <p>Die optionale Option WeekStart, sofern angegeben, muss einer der folgenden sein: { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. Es ändert TimeMetric, indem es nach hinten zum letzten Vorkommen dieses Wochentags verschoben wird. </p> <p>Beispiel: Wenn die Metrik "Woche"die Elemente { "10/03/10", "10/10/10", ..., "12/12/10" } aufweist und die integrierte Ausführungsmethode den Wert 1292348109 hat (was eine Zeit in der Mitte des 14. Dezember 20200002000000000000000000000000000000000000000000000000000000000000000000000 010), dann last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") definiert die Dimension mit den Elementen { "12/12/10", "19/10", "12/23/10", "12/30/10" }. </p> <p>Beispiel 2: Wenn die Dimension "Woche"nur die Elemente {"19.12.10", "12.26.10", ..., "01/30/11"} enthält und die Metrik "Ausführungsdatum"wie oben lautet, dann gibt last n(Week, As_Of, "%m/%d/%y", 4, 0, true, "Sun") a Dimension mit Elementen {"19.12.10", "23.12.10", "12.30.10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, die eine Untergruppe der Elemente von Dim enthält, deren Elemente Tage darstellen. Die Untergruppe ist ein Bereich um eine angegebene Zeit, der Wert der konstanten Metrik TimeMetric, die als Zeitwert in Sekunden seit dem 1. Januar 1970 (UTC) um Mitternacht interpretiert wird. Der Bereich enthält die Elemente, die den einzelnen Tagen in den nMonats vor der angegebenen Zeit entsprechen. Wenn includeThisMonth true ist, enthält der Bereich auch jeden Tag des Monats, der die angegebene Zeit enthält. </p> <p>FormatString gibt die Formatierung der Dim-Elemente an, wobei "%"-Escapes wie in der Standard-C-Bibliotheksfunktion strftime verwendet werden. </p> <p>Wenn trimToData den Wert "true"hat, werden alle Elemente am Anfang der resultierenden Dimension, die vor dem Anfang von Dim liegen, entfernt. Wenn der Wert "false"ist, gibt es immer die exakte Anzahl von Elementen, die von "Count"angegeben werden. Beachten Sie, dass es immer Elemente am Ende der resultierenden Dimension geben kann, die sich nicht wirklich in Dim befinden. </p> <p>Beispiel: Wenn Day die Elemente { "01/01/10", "01/02/10", ..., "12/31/10" } und die integrierte Ausführungsmethode zum Ausführungszeitpunkt den Wert 1292348109 (was eine Zeit in der Mitte des 14. Dezember 20 darstellt) 10), dann haben die Tage der vorherigen Monate(Tag, As_Of, "%m/%d/%y", 2, false, false) die Elemente { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Ähnlich wie Tage der vorherigen Monate, mit der Ausnahme, dass die Elemente nur den Tagen desselben Monats entsprechen, die von der TimeMetric angegeben wurden. Wenn allMonth true ist, wird für jeden Tag des entsprechenden Monats ein Element angezeigt. Andernfalls werden nur Tage vom ersten des entsprechenden Monats bis zum Tag mit der angegebenen Zeit Teil der Dimension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Ähnlich wie Tage der vorherigen Monate, allerdings entsprechen die Elemente den Tagen nach dem Monat, der die von der TimeMetric angegebene Zeit enthält, und nicht vorher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hour_of_day(Dim, Metric, TimeFormatString, DaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Definiert eine Dimension, die eine Untergruppe der Elemente von Dim enthält, deren Elemente Stunden darstellen. Die Untergruppe ist ein Bereich um eine angegebene Zeit, der Wert der konstanten Metrik TimeMetric, die als Zeitwert in Sekunden seit dem 1. Januar 1970 (UTC) um Mitternacht interpretiert wird. Der Bereich umfasst die Elemente, die jeder Stunde des Tages Tag Vorwärts nach dem Tag entsprechen, der die von der TimeMetric angegebene Zeit enthält. </p> <p>FormatString gibt die Formatierung der Dim-Elemente an, wobei "%"-Escapes wie in der Standard-C-Bibliotheksfunktion strftime verwendet werden. Die Formatzeichenfolge sollte immer eine Zeichenfolge ausgeben, die Mitternacht am Anfang des angegebenen Zeitraums darstellt. </p> <p>Wenn trimToData den Wert "true"hat, werden alle Elemente am Anfang der resultierenden Dimension, die vor dem Anfang von Dim liegen, entfernt. Wenn der Wert "false"ist, gibt es immer die exakte Anzahl von Elementen, die von "Count"angegeben werden. Beachten Sie, dass es immer Elemente am Ende der resultierenden Dimension geben kann, die sich nicht wirklich in Dim befinden. </p> <p>Beispiel: Wenn die Metrik "Stunde"die Elemente { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" } enthält und die integrierte Ausführungsmethode den Wert 1292348 hat 109 (entspricht einer Zeit in der Mitte des 14. Dezember 2010), dann haben Stunden am Tag(Stunde, Wie_Von, "%x 00:00", 0, false) Elemente { "12/12/10 00:00", "12/12/10 01:00 ", ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
