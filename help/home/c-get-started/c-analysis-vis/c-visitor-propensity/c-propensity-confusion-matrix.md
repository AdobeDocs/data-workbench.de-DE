---
description: Die statistischen Berechnungen für die Tendenzauswertung sind definiert.
title: Berechnen der Tendenzauswertung
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Berechnen der Tendenzauswertung{#calculating-propensity-scoring}

{{eol}}

Die statistischen Berechnungen für die Tendenzauswertung sind definiert.

Das für jeden Besucher berechnete Ergebnis ist eine geschätzte Wahrscheinlichkeit, mit der das angegebene Ereignis (definiert durch den Zielfilter) eintreten kann, was zu einem Ergebniswert von 0 bis 100 Prozent führt. Das Scoring-Verfahren verwendet vorhandene Beispiele als Trainings-Daten, um die Beziehung zwischen der Ereigniswahrscheinlichkeit und den ausgewählten unabhängigen Variablen von Interesse zu ermitteln.

Mathematisch spiegeln sich solche Beziehungen in jedem quantitativen Wert wider, der für jede unabhängige Variable zugeordnet ist. Diese Werte werden als Modellkoeffizienten bezeichnet. ScoreDim verwendet derzeit den IRLS-Algorithmus (Iterativ Regewichtete Least Quadrate), um die Modellkoeffizienten zu schätzen. IRLS durchläuft die Proben mehrmals, bis der Unterschied der Koeffizienten zwischen dem aktuellen Pass und dem vorherigen Pass kleiner als 1,0e-6 ist. An diesem Punkt wird er als **konvertiert**. Je nach den Daten kann IRLS jedoch nicht in der Lage sein, Konvergenz zu erreichen.

In diesem Fall wird die Trainings-Iteration des Modells beendet, wenn

* der Koeffizienten-Unterschied wird größer statt kleiner,
* 1.000 Durchgänge erreicht wurden oder
* ein mathematischer Fehler verhindert die Fortsetzung der Iteration.

Wenn IRLS nicht konvergiert, wird ein Backup-Algorithmus mit dem Namen Stochastic Gradient Decent (SGD) verwendet. SGD wird die Trainings-Proben auch mehrmals durchlaufen. Im Gegensatz zu IRLS werden die SGD-Modellkoeffizienten jedoch so gesteuert, dass der Unterschied zwischen Iteration immer exponentiell abnimmt. Entsprechend endet die SGD, wenn der Koeffizient unter 1,0e-6 fällt oder 100.000 Durchgänge erreicht wurden. Das Versagen von IRLS und das Engagement von SGD wird im Trace Log aufgezeichnet.

Bei beiden Algorithmen werden nicht alle Samples in das Modell-Training eingebunden. Achtzig Prozent werden derzeit zum Trainieren des Modells verwendet. Nach der Schulung des Modells werden die verbleibenden zwanzig Prozent Proben verwendet, um die Modellstärke anhand der aus der Verwirrungsmatrix berechneten Genauigkeit, Rückruf und Genauigkeit zu bewerten. Je näher 100 % liegen, desto besser ist das Scoring-Modell.
