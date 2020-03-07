---
description: Ein Filter ist ein Ausdruck, der eine Untergruppe der Daten in einem Datensatz definiert.
solution: Analytics
title: Syntax für Filterausdrücke
topic: Data workbench
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax für Filterausdrücke{#syntax-for-filter-expressions}

Ein Filter ist ein Ausdruck, der eine Untergruppe der Daten in einem Datensatz definiert.

Ein Filter erlaubt oder lehnt jedes Element jeder Dimension entsprechend den Beziehungen zwischen Dimensionen ab.

Filter können mit der [!DNL Filter Editor]Option bearbeitet werden. Siehe [Filter-Editoren](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

In der folgenden Tabelle enthält jede Syntaxbeschreibung ein Beispiel für einen Metrikausdruck, der diesen Filter verwendet. Beispielsweise ist[SessionsTrue] eine Metrik, die mit dem Filter &quot;True&quot;definiert wird. Die Metrik[SessionsTrue] ist identisch mit der Metrik Sitzungen, da der Filter True jedes Element der Dimension Sitzung zulässt.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Konstantenfilter. Ermöglicht die Zuweisung jedes Elements jeder Dimension </p> <p>Beispiel: Sessions[ True ] ist mit Sessions identisch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Konstantenfilter. lehnt jedes Element jeder Dimension ab. </p> <p>Beispiel: Sitzungen[ false ] ist immer null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nicht filtern </p> </td> 
   <td colname="col2"> <p>Ermöglicht Elemente, die von Filter abgelehnt werden. </p> <p>Beispiel: Sitzungen[ nicht Seite="A" ] ist die Anzahl der Sitzungen, die Seite A nicht besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA und FilterB </p> </td> 
   <td colname="col2"> <p>Ermöglicht Elemente, die FilterA und FilterB zugeben. </p> <p>Beispiel: Sitzungen[ Seite="A" und Seite="B" ] ist die Anzahl der Sitzungen, die sowohl Seite A als auch Seite B besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA oder FilterB </p> </td> 
   <td colname="col2"> <p>Ermöglicht Elemente, die FilterA oder FilterB zugeben. </p> <p>Beispiel: Sitzungen[ Seite="A" oder Seite="B" ] ist die Anzahl der Sitzungen, die Seite A, Seite B oder beide besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nach Dim filtern </p> </td> 
   <td colname="col2"> <p>Ermöglicht den Satz von Elementen der Dimension Dim, die von Filter zugelassen werden. </p> <p>Beispiel: Sitzungen[ Seite="/Startseite" von Besucher ] ist die Anzahl der Sitzungen eines Besuchers, bei denen die Seite "/home"angezeigt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Referenzfilter, die im Profil anders definiert sind. </p> <p>Beispiel: Sessions[ Broken_Sitzung_Filter ] ist die Anzahl der Sitzungen, die vom Filter für ungültige Sitzungen zugelassen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Gibt das angegebene Element der Dimension Dim zu. </p> <p>Beispiel: Sitzungen[ Seite="A" ] ist die Anzahl der Sitzungen, die Seite A besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim!= “Wert” </p> </td> 
   <td colname="col2"> <p>Gibt jedes andere Element der Dimension Dim zu. </p> <p>Beispiel: Sessions[ Seite&lt;&gt;"A" ] ist die Anzahl der Sitzungen, die eine andere Seite als A besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Gibt das Element der Dimension Dim mit dem angegebenen Ordnungswert zu. </p> <p>Beispiel: Sitzungen[ Monat=#0 ] ist die Anzahl der Sitzungen im ersten Monat des Datensatzes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Gibt jedes andere Element der Dimension Dim zu. </p> <p>Beispiel: Sitzungen[ Sitzungswert &lt;&gt; #0 ] ist die Anzahl der Sitzungen mit einem Sitzungswert ungleich null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim stimmt mit "Expr"überein </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Dim, die mit dem angegebenen regulären Ausdruck übereinstimmen, werden zugelassen. Dim darf keine denormale oder zählbare Dimension sein. </p> <p>Beispiel: Sitzung[ URI stimmt überein mit ".*/Produkt/.*" ] ist die Anzahl der Sitzungen, die eine Seite in einem Produktverzeichnis besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim entspricht nicht "Expr" </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Dim stimmen nicht mit dem angegebenen regulären Ausdruck überein. Dim darf keine denormale oder zählbare Dimension sein. </p> <p>Beispiel: Sitzungen[ URI stimmt nicht überein mit ".*\.jsp" ] ist die Anzahl der Sitzungen, die eine Seite besucht haben, die keine JSP-Seite war. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Dim werden mit Ordinalwerten kleiner als der Ordinalwert des Elements "Value"zugelassen. Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Monat &lt; "Juli 2004" ] ist die Anzahl der Sitzungen, die vor Juli 2004 stattgefunden haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Die Elemente der Dimension Dim mit Ordinalwerten größer als der Ordinalwert des Elements "Value". Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Monat &gt; Juli 2004 ] ist die Anzahl der Sitzungen, die nach Juli 2004 stattgefunden haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Elemente der Dimension Dim mit Ordinalwerten kleiner als oder gleich dem Ordinalwert des Elements "Value". Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Sitzung_Nummer &lt;= "2" ] ist die Anzahl der Sitzungen, die die erste oder zweite Sitzung eines Besuchers waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Ermöglicht die Elemente der Dimension Dim mit Ordinalwerten größer oder gleich dem Ordinalwert des Elements "Value". Wenn "Wert"kein Dimensionselement ist, wird angenommen, dass er größer ist als jedes aktuelle Element der Dimension. </p> <p>Beispiel: Sitzungen[ Sitzungsnummer &gt;= "5" ] ist die Anzahl der Sitzungen, die die fünfte oder größere Sitzung eines Besuchers waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>beliebige Dim </p> </td> 
   <td colname="col2"> <p>Lässt alle Elemente der Dimension Dim zu. </p> <p>Beispiel: Sitzungen[ beliebige Seitenansichten ] ist die Anzahl der Sitzungen mit mindestens einer Seitenansicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nein Dim </p> </td> 
   <td colname="col2"> <p>Lässt Elemente zu, die von Dim abgelehnt werden. </p> <p>Beispiel: Sitzungen[ keine Seitenansicht ] ist die Anzahl der Sitzungen ohne Seitenansicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTER) </p> </td> 
   <td colname="col2"> <p>Dasselbe wie FILTER; zum Gruppieren eines Teils eines Filterausdrucks verwendet. </p> </td> 
  </tr> 
 </tbody> 
</table>

