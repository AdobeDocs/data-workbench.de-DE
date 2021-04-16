---
description: Metriken können mit dem Metrik-Editor bearbeitet und im Metrikverzeichnis eines Profils gespeichert werden.
title: Syntax für Ausdrücke zu Metriken
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Syntax für Ausdrücke zu Metriken{#syntax-for-metric-expressions}

Metriken können mit dem Metrik-Editor bearbeitet und im Metrikverzeichnis eines Profils gespeichert werden.

Weitere Informationen finden Sie unter [Erstellen und Bearbeiten von abgeleiteten Metriken](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40). Metrische Ausdruck können auch in Arbeitsblättern verwendet werden. Weitere Informationen finden Sie unter [Arbeitsblätter](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). Die folgende Syntax dient zum Definieren von metrischen Ausdrücken.

Hinweise:

1. Unterstrichene Wörter sollten wörtlich in den Ausdruck eingegeben werden.
1. Das Formular `{TEXT}?` stellt optionalen Text dar.
1. Das Formular `{TEXT}*` stellt Text dar, der null oder mehr Mal auftreten kann.
1. Das Formular `{A | B | C |...}` stellt Text dar, der aus genau einer der angegebenen Optionen besteht, z. B. A oder B oder C....
1. Das Formular `[A,B)` stellt einen Zahlenbereich dar, von A bis B.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Ein Bezeichner verweist auf eine benannte Metrik. Die Regeln für rechtliche Bezeichner finden Sie unter <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntax für Bezeichner </a>. </p> <p>Beispiel: Umsatz = Gesamtpreis </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Metrik) </p> </td> 
   <td colname="col2"> <p>Das Ergebnis von (Metrik) ist dasselbe wie das Ergebnis der Metrik. Klammern geben die Reihenfolge der Vorgänge in einem Ausdruck an. </p> <p>Beispiel: Durchschnitt = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Summe der Ergebnisse der Metrik A und B. </p> <p>Beispiel: Wert = Umsatz + Kosten_Einsparungen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Differenz der Ergebnisse der Metrik A und der Metrik B. </p> <p>Beispiel: Gewinn = Umsatz - Kosten </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Produkt aus den Ergebnissen der Metrik A und B. </p> <p>Beispiel: Dollar = Cent * 0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>Verhältnis der Ergebnisse der Metrik A und der Metrik B. </p> <p>Beispiel: Umsatz_pro_Sitzung = Umsatz/Sitzungen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Ergebnis der Metrik A, die auf die Stärke des Ergebnisses der Metrik B erhöht wurde. </p> <p>Beispiel: Bereich = Breite^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trust(metric) </p> </td> 
   <td colname="col2"> <p>Eine Schätzung der Standardabweichung der Metrik. Dies wird mit einer als Jackkniffing bezeichneten Probenahmemethode berechnet. </p> <p>Diese Metrik ist speicherintensiv und sollte nicht in großen Tabellen verwendet werden. </p> <p>Um diese Syntax zu verwenden, müssen Sie eine Jackmesser-Dimension (namens "Jackmesser") mit den entsprechenden Eigenschaften haben. Weitere Informationen erhalten Sie bei Adobe Consulting Services. </p> <p>Beispiel: trust(Average_Score) </p> <p> <p>Hinweis:  Die Konfidenzmetriktypen, einschließlich Konfidenz(Metrik) und Konfidenz(Metrik, Jacknife), sind besonders bei der Verwendung der kontrollierten Experimentierungsfunktion der Adobe nützlich. Wenn eine Metrik während eines kontrollierten Experiments von 12 % auf 16 % sprang, könnten Sie eine Konfidenzaufschlüsselung verwenden, um die Wahrscheinlichkeit zu berechnen, dass der Sprung auf zufällige Variationen zurückzuführen war. Dies kann Ihnen helfen, die falschen Schlussfolgerungen aus begrenzten Beweisen zu vermeiden und umgekehrt die Sicherheit zu bieten, dass eine fragwürdige Veränderung tatsächlich real ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trust(metric, jackmesser) </p> </td> 
   <td colname="col2"> <p>Eine Schätzung der Standardabweichung der Metrik. Dies wird mit einer als Jackkniffing bezeichneten Probenahmemethode berechnet. Mit dieser Syntax können Sie die Konfidenz einer Metrik mithilfe einer Jackmesser-Dimension bestimmen, die etwas Anderes als "Jackmesser"heißt. </p> <p>Diese Metrik ist speicherintensiv und sollte nicht in großen Tabellen verwendet werden. </p> <p>Um diese Syntax zu verwenden, müssen Sie eine Jackmesser-Dimension (etwas Anderes als "Jackmesser") mit den entsprechenden Eigenschaften haben. Weitere Informationen erhalten Sie bei Adobe Consulting Services. </p> <p>Beispiel: trust(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Behandelt den Zelleninhalt, den Sie referenzieren, als metrischen Ausdruck. Diese Syntax kann nur in einer Arbeitsblattvisualisierung verwendet werden. </p> <p>Beispiel: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>Die mathematische Logarithmfunktion: Metrik X ist der Parameter und Metrik B ist die Basis. </p> <p>Beispiel: dB = 20*log(Amplitude,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik[Filter] </p> </td> 
   <td colname="col2"> <p>"Metrik, wo Filter": Eine neue Metrik, die vom angegebenen Filter gefiltert wird. </p> <p>Beispiel: Jan_sessions = Sitzungen[ Monat="Januar" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik nach Dimension </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die auf der "Ebene"der Dimension ausgewertet wird. Das Ergebnis von (M von X)[F] (das Ergebnis der Metrik "M von X", die mit Filter "F" ausgewertet wird) ist das Ergebnis von M[F von X] (das Ergebnis der Metrik "M", ausgewertet mit Filter "F von X"). </p> <p>Beispiel: AB_Besuchers = </p> <p>(Besucher nach Sitzung)[Page="A" und page="B"] = </p> <p>Besucher[(Page="A" and page="B") by Session] = </p> <p>Die Anzahl der Besucher, die Seite A und Seite B in derselben Sitzung besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl </p> </td> 
   <td colname="col2"> <p>Eine Metrik mit einem festen Wert. </p> <p>Beispiel: Pi = 3.1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metrik) </p> </td> 
   <td colname="col2"> <p>Ignoriert alle Dimensionen, bei denen die Metrik ausgewertet wird. Die Metrik hat für jedes Element dieser Dimension denselben Wert. </p> <p>Beispiel: Pct_of_Besuchers = Besucher / total(Besucher) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignoriert Filter, die auf die Metrik angewendet werden. Die Metrik wird von Auswahlen und anderen Filtern nicht beeinflusst. </p> <p>Beispiel: Benchmark_Sessions = all( Sessions ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignoriert alle Filter und Dimensionen. Sie hat in einem bestimmten Profil den gleichen Wert, unabhängig davon, welche Filter oder Dimensionen angewendet werden. </p> <p>Beispiel: DataSet_Besuchers = total(all(Besucher) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die die Anzahl einer zählbaren Dimension wie Besucher oder Sitzung angibt. </p> <p>Beispiel: Besucher = sum(One,Besucher) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die die Summe einer numerischen Dimension über einer zählbaren Dimension angibt. Die normalen Werte (im Gegensatz zu den formatierten Werten) der Elemente der numerischen Dimension werden verwendet, sodass oft ein Skalierungsfaktor auf das Ergebnis angewendet werden muss. </p> <p>Beispiel: Wert = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>Die geringeren Ergebnisse der Metrik A und B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Die höheren Ergebnisse der Metrik A und B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die mit der Metrik A identisch ist, mit der Ausnahme, dass sie die Formatierungsfunktion der Metrik B verwendet. </p> </td> 
  </tr> 
 </tbody> 
</table>
