---
description: Ein Filter ist ein Ausdruck, der eine Teilmenge der Daten in einem Datensatz definiert.
title: Syntax für Ausdrücke zu Filtern
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# Syntax für Ausdrücke zu Filtern{#syntax-for-filter-expressions}

Ein Filter ist ein Ausdruck, der eine Teilmenge der Daten in einem Datensatz definiert.

Ein Filter lässt jedes Element jeder Dimension je nach den Beziehungen zwischen Dimensionen zu oder lehnt es ab.

Filter können mit [!DNL Filter Editor] bearbeitet werden. Siehe [Filter Editors](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

In der folgenden Tabelle enthält jede Syntaxbeschreibung ein Beispiel für einen Metrikausdruck, der diesen Filter verwendet. Beispielsweise ist Sessions[True] eine Metrik, die mithilfe des Filters &quot;True&quot;definiert wird. Die Metrik Sitzungen[True] ist mit der Metrik Sitzungen identisch, da der Filter Wahr jedes Element der Sitzungsdimension zulässt.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Konstanter Filter. Erlaubt jedes Element jeder Dimension </p> <p>Beispiel: Sitzungen[ True ] ist mit Sitzungen identisch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Konstanter Filter. lehnt jedes Element jeder Dimension ab. </p> <p>Beispiel: Sitzungen[ False ] ist immer null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nicht filtern </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Zurückweisung von Elementen durch den Filter. </p> <p>Beispiel: Sitzungen[ nicht Seite="A" ] ist die Anzahl der Sitzungen, die Seite A nicht besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA und FilterB </p> </td> 
   <td colname="col2"> <p>Fügt Elemente zu, die FilterA und FilterB zugeben. </p> <p>Beispiel: Sitzungen[ Seite="A" und Seite="B" ] ist die Anzahl der Sitzungen, die sowohl Seite A als auch Seite B besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA oder FilterB </p> </td> 
   <td colname="col2"> <p>Fügt Elemente zu, die FilterA oder FilterB zugeben. </p> <p>Beispiel: Sitzungen[ Seite="A" oder Seite="B" ] ist die Anzahl der Sitzungen, die Seite A, Seite B oder beide besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtern nach Dim </p> </td> 
   <td colname="col2"> <p>Fügt die Elemente der Dimension Dim hinzu, die durch Filter zugelassen werden. </p> <p>Beispiel: Sitzungen[ Seite="/home" by Visitor ] ist die Anzahl der Sitzungen eines Besuchers, der die Seite "/home"gesehen hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Referenzfilter, die im Profil anders definiert sind. </p> <p>Beispiel: Sitzungen[ Broken_Session_Filter ] ist die Anzahl der Sitzungen, die vom Filter "Beschädigte Sitzung"zugelassen wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Wert" </p> </td> 
   <td colname="col2"> <p>Gibt das angegebene Element der Dimension Dim zu. </p> <p>Beispiel: Sitzungen[ Seite="A" ] ist die Anzahl der Sitzungen, die Seite A besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim!= “Wert” </p> </td> 
   <td colname="col2"> <p>Gibt jedes andere Element der Dimension Dim zu. </p> <p>Beispiel: Sitzungen[ Seite&lt;&gt;"A" ] ist die Anzahl der Sitzungen, die eine andere Seite als A besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Weist das Element der Dimension Dim mit dem angegebenen Ordinalwert zu. </p> <p>Beispiel: Sitzungen[ Monat=#0 ] ist die Anzahl der Sitzungen im ersten Monat des Datensatzes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Gibt jedes andere Element der Dimension Dim zu. </p> <p>Beispiel: Sitzungen[ Sitzungswert &lt;&gt; #0 ] ist die Anzahl der Sitzungen mit einem Sitzungswert ungleich null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim stimmt mit "Expr"überein </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Dim, die mit dem angegebenen regulären Ausdruck übereinstimmen, werden zugelassen. Dim darf keine denormale oder zählbare Dimension sein. </p> <p>Beispiel: Session[ URI stimmt überein mit ".*/product/.*" ] ist die Anzahl der Sitzungen, die eine beliebige Seite in einem Produktverzeichnis besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim stimmt nicht mit "Expr"überein </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Entspricht nicht dem angegebenen regulären Ausdruck. Dim darf keine denormale oder zählbare Dimension sein. </p> <p>Beispiel: Session[ URI stimmt nicht mit "überein.*\.jsp" ] ist die Anzahl der Sitzungen, die eine Seite besucht haben, die keine JSP-Seite war. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Weist die Elemente der Dimension Dim mit Ordinalwerten unterhalb des Ordinalwerts des Elements "Wert"zu. Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Monat &lt; "Juli "04" ] ist die Anzahl der Sitzungen, die vor Juli 2004 stattgefunden haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Weist die Elemente der Dimension Dim mit Ordinalwerten zu, die größer sind als der Ordinalwert des Elements "Wert". Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Monat &gt; "Juli "04" ] ist die Anzahl der Sitzungen, die nach Juli 2004 stattgefunden haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Dim mit Ordinalwerten kleiner oder gleich dem ordentlichen Wert des Elements "Wert". Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Sitzungsnummer &lt;= "2" ] ist die Anzahl der Sitzungen, die die erste oder zweite Sitzung eines Besuchers waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Weist die Elemente der Dimension Dim mit Ordinalwerten zu, die größer oder gleich dem ordentlichen Wert des Elements "Wert"sind. Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Sitzungsnummer &gt;= "5" ] ist die Anzahl der Sitzungen, die die fünfte oder größere Sitzung eines Besuchers waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>beliebiger Dim </p> </td> 
   <td colname="col2"> <p>Alle Elemente der Dimension Dim werden zugelassen. </p> <p>Beispiel: Sitzungen[ beliebige Seitenansicht ] ist die Anzahl der Sitzungen mit mindestens einer Seitenansicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim </p> </td> 
   <td colname="col2"> <p>Gibt Elemente zu, die von Dim zurückgewiesen werden. </p> <p>Beispiel: Sitzungen[ keine Seitenansicht ] ist die Anzahl der Sitzungen ohne Seitenansicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTER) </p> </td> 
   <td colname="col2"> <p>Dasselbe wie FILTER; wird verwendet, um einen Teil eines Filterausdrucks zu gruppieren. </p> </td> 
  </tr> 
 </tbody> 
</table>
