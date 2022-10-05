---
description: Metriken können mit dem Metrik-Editor bearbeitet und im Verzeichnis "Metriken"eines Profils gespeichert werden.
title: Syntax für Ausdrücke zu Metriken
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Syntax für Ausdrücke zu Metriken{#syntax-for-metric-expressions}

{{eol}}

Metriken können mit dem Metrik-Editor bearbeitet und im Verzeichnis &quot;Metriken&quot;eines Profils gespeichert werden.

Weitere Informationen finden Sie unter [Erstellen und Bearbeiten abgeleiteter Metriken](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40). Metrikausdrücke können auch in Arbeitsblättern verwendet werden. Weitere Informationen finden Sie unter [Arbeitsblätter](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). Die folgende Syntax wird verwendet, um Metrikausdrücke zu definieren.

Hinweise:

1. Unterstrichene Wörter sollten wörtlich in den Ausdruckstext eingegeben werden.
1. Das Formular `{TEXT}?` stellt optionalen Text dar.
1. Das Formular `{TEXT}*` stellt Text dar, der null oder mehrmals vorkommen kann.
1. Das Formular `{A | B | C |...}` stellt Text dar, der aus genau einer der angegebenen Optionen besteht, z. B. A, B oder C...
1. Das Formular `[A,B)` stellt einen Zahlenbereich dar, von A bis B, jedoch nicht B.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Kennung </p> </td> 
   <td colname="col2"> <p>Eine Kennung verweist auf eine benannte Metrik. Die Vorschriften für die Kennungen von Rechtspersonen finden Sie unter <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntax für Kennungen </a>. </p> <p>Beispiel: Umsatz = Gesamtpreis </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Metrik) </p> </td> 
   <td colname="col2"> <p>Das Ergebnis von (Metrik) entspricht dem Ergebnis der Metrik. In Klammern wird die Reihenfolge der Vorgänge in einem Ausdruck angegeben. </p> <p>Beispiel: Durchschnitt = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Summe der Ergebnisse der Metriken A und B. </p> <p>Beispiel: Wert = Umsatz + Kosten_Einsparungen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Differenz der Ergebnisse von Metrik A und Metrik B. </p> <p>Beispiel: Gewinn = Umsatz - Kosten </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Produkt der Ergebnisse der Metrik A und B. </p> <p>Beispiel: Dollar = Cent * 0,01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>Verhältnis der Ergebnisse von Metrik A und Metrik B. </p> <p>Beispiel: Umsatz_pro_Sitzung = Umsatz/Sitzungen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Ergebnis der Metrik A, die auf die Stärke des Ergebnisses von Metrik B erhöht wurde. </p> <p>Beispiel: Bereich = Breite^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric) </p> </td> 
   <td colname="col2"> <p>Eine Schätzung der Standardabweichung der Metrik. Dies wird mithilfe einer als Jackmesser bekannten Sampling-Technik berechnet. </p> <p>Diese Metrik ist speicherintensiv und sollte nicht in großen Tabellen verwendet werden. </p> <p>Um diese Syntax verwenden zu können, müssen Sie über eine Jackmesser-Dimension (namens "Jackmesser") mit den entsprechenden Eigenschaften verfügen. Weitere Informationen erhalten Sie von Adobe Consulting Services. </p> <p>Beispiel: confidence(Average_Score) </p> <p> <p>Hinweis: Die Konfidenzmetriktypen, einschließlich Konfidenz(Metrik) und Konfidenz(Metrik, Jacknife), sind besonders bei der Verwendung der kontrollierten Experimentierungsfunktion von Adobe nützlich. Wenn eine Metrik während eines kontrollierten Experiments von 12 % auf 16 % sprunghaft war, können Sie mithilfe eines Konfidenzberechnens die Wahrscheinlichkeit berechnen, dass der Sprung auf zufällige Variationen zurückzuführen war. Dies kann Ihnen helfen, die falschen Schlüsse aus begrenzten Beweisen zu vermeiden und umgekehrt zu garantieren, dass eine fragwürdige Veränderung tatsächlich real ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric, jackmesser) </p> </td> 
   <td colname="col2"> <p>Eine Schätzung der Standardabweichung der Metrik. Dies wird mithilfe einer als Jackmesser bekannten Sampling-Technik berechnet. Diese Syntax ermöglicht es Ihnen, die Konfidenz einer Metrik mithilfe einer Messer-Dimension mit dem Namen "Jackmesser"zu bestimmen. </p> <p>Diese Metrik ist speicherintensiv und sollte nicht in großen Tabellen verwendet werden. </p> <p>Um diese Syntax verwenden zu können, müssen Sie über eine Jackmesser-Dimension (mit dem Namen etwas Anderes als "Jackmesser") mit den entsprechenden Eigenschaften verfügen. Weitere Informationen erhalten Sie von Adobe Consulting Services. </p> <p>Beispiel: confidence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Behandelt den Inhalt der Zelle, auf die Sie verweisen, als Metrikausdruck. Diese Syntax kann nur in einer Arbeitsblattvisualisierung verwendet werden. </p> <p>Beispiel: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>Die mathematische Logarithmusfunktion: Metrik X ist der Parameter und Metrik B ist die Basis. </p> <p>Beispiel: dB = 20*log(Amplitude,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik[Filter] </p> </td> 
   <td colname="col2"> <p>"Metrik, bei der Filter: Eine neue Metrik, die nach dem angegebenen Filter gefiltert wird. </p> <p>Beispiel: Jan_sessions = sessions[ month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrik nach Dimension </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die auf der "Ebene"der Dimension ausgewertet wird. Das Ergebnis von (M von X)[F] (das Ergebnis der Metrik "M von X"wird mit Filter "F"ausgewertet) ist das Ergebnis von M[F von X] (das Ergebnis der Metrik "M"ausgewertet mit Filter "F von X"). </p> <p>Beispiel: AB_Visitors = </p> <p>(Besucher nach Sitzung)[Page="A" und Page="B"] = </p> <p>Visitors[(Page="A" and Page="B") by Session] = </p> <p>Die Anzahl der Besucher, die Seite A und Seite B in derselben Sitzung besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl </p> </td> 
   <td colname="col2"> <p>Eine Metrik mit einem festen Wert. </p> <p>Beispiel: Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metrik) </p> </td> 
   <td colname="col2"> <p>Ignoriert alle Dimensionen, für die die Metrik ausgewertet wird. Die Metrik hat für jedes Element dieser Dimension denselben Wert. </p> <p>Beispiel: Pct_of_Visitors = Besucher/total(Visitors) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metrik) </p> </td> 
   <td colname="col2"> <p>Ignoriert Filter, die auf die Metrik angewendet werden. Die Metrik wird von Auswahlen und anderen Filtern nicht beeinflusst. </p> <p>Beispiel: Benchmark_Sessions = all( Sitzungen ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric)) </p> </td> 
   <td colname="col2"> <p>Ignoriert alle Filter und Dimensionen. Sie hat für ein bestimmtes Profil denselben Wert, unabhängig davon, welche Filter oder Dimensionen angewendet werden. </p> <p>Beispiel: Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die die Anzahl einer zählbaren Dimension wie Besucher oder Sitzung angibt. </p> <p>Beispiel: Besucher = sum(One,Visitor) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_Dimension, Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die die Summe einer numerischen Dimension über eine zählbare Dimension liefert. Die Ordinalwerte (im Gegensatz zu den formatierten Werten) der Elemente der numerischen Dimension werden verwendet, sodass häufig ein Skalierungsfaktor auf das Ergebnis angewendet werden muss. </p> <p>Beispiel: Wert = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>Die geringeren Ergebnisse der Metriken A und B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Die größeren Ergebnisse der Metriken A und B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Eine Metrik, die mit Metrik A identisch ist, mit der Ausnahme, dass sie die Formatierungsfunktion der Metrik B verwendet. </p> </td> 
  </tr> 
 </tbody> 
</table>
