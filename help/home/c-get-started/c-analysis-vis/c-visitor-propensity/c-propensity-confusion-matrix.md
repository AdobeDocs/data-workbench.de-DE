---
description: Die statistischen Berechnungen für die Tendenzauswertung werden definiert.
solution: Analytics
title: Berechnen der Tendenzauswertung
topic: Data workbench
uuid: 67270864-0468-4cc9-b48b-0e880f813555
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Berechnen der Tendenzauswertung{#calculating-propensity-scoring}

Die statistischen Berechnungen für die Tendenzauswertung werden definiert.

Das für jeden Besucher berechnete Ergebnis ist eine geschätzte Wahrscheinlichkeit, dass das angegebene Ereignis (vom Zielfilter definiert) eintritt, was zu einem Ergebniswert von 0 bis 100 Prozent führt. Das Bewertungsverfahren verwendet vorhandene Beispiele als Schulungsdaten, um die Beziehung zwischen der Ereigniswahrscheinlichkeit und den ausgewählten unabhängigen Variablen von Interesse zu ermitteln.

Mathematisch gesehen werden solche Beziehungen in jedem quantitativen Wert widergespiegelt, der für jede unabhängige Variable zugeordnet ist. Diese Werte werden als Modellkoeffizienten bezeichnet. ScoreDim verwendet derzeit den IRLS-Algorithmus (Iterativ Regewichtete wenigsten Quadrate), um die Modellkoeffizienten zu schätzen. IRLS durchläuft die Proben mehrmals, bis der Unterschied der Koeffizienten zwischen dem aktuellen Pass und dem vorherigen Pass kleiner als 1.0e-6 ist. An diesem Punkt wird es als **konvertiert** bezeichnet. Je nach Datenlage ist das IRLS jedoch möglicherweise nicht in der Lage, Konvergenz zu erreichen.

In diesem Fall wird die Modellschulung beendet, wenn

* der Koeffizienten größer wird statt kleiner,
* 1.000 Pässe erreicht wurden oder
* ein mathematischer Fehler verhindert eine weitere Iteration.

Wenn IRLS nicht konvertiert wird, wird ein Reservealgorithmus mit dem Namen Stochastic Gradient Decent (SGD) verwendet. SGD wird die Schulungsmuster auch mehrmals durchlaufen. Im Gegensatz zu IRLS werden die SGD-Modellkoeffizienten jedoch so gesteuert, dass der Unterschied zwischen Iteration immer exponentiell abnimmt. Gleichermaßen endet die SGD, wenn der Koeffizient unter 1.0e-6 fällt oder 100.000 Durchgänge erreicht wurden. Der Ausfall von IRLS und die Einbindung von SGD werden im Ablaufverfolgungsprotokoll aufgezeichnet.

Bei beiden Algorithmen werden nicht alle Beispiele in Modellschulungen umgewandelt. Achtzig Prozent werden derzeit zur Ausbildung des Modells verwendet. Nach der Schulung des Modells werden die verbleibenden 20 Prozent der Proben verwendet, um die Modellstärke anhand der aus der Verwirrungsmatrix errechneten Genauigkeit, Rückruf und Genauigkeit zu bewerten. Je näher 100 % liegen, desto besser ist das Bewertungsmodell.
