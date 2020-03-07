---
description: Eine Visualisierung einer geführten Analyse bietet Hinweise für eine weitere Analyse, die auf den Auswahlen basieren, die Sie in einem Arbeitsbereich vornehmen.
solution: Analytics
title: Geführte Analyse
topic: Data workbench
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Geführte Analyse{#guided-analysis}

Eine Visualisierung einer geführten Analyse bietet Hinweise für eine weitere Analyse, die auf den Auswahlen basieren, die Sie in einem Arbeitsbereich vornehmen.

Diese Visualisierung hilft Ihnen dabei herauszufinden, welche Dimensionen Ihnen weitere Informationen liefern können, d. h. welche Dimensionen am stärksten mit Ihrer Auswahl korrelieren. Die Visualisierung der geführten Analyse in Ihrer Adobe-Anwendung zeigt die für Ihr Dataset relevanten Dimensionen an, wie in der folgenden Visualisierung der [!DNL Site] geführten Analyse dargestellt.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Wenn ein Dimensionsname rot angezeigt wird, wird er nicht in Ihrem Datensatz definiert.

Wenn Sie eine Auswahl innerhalb eines Arbeitsbereichs vornehmen, zeigt die Visualisierung der geführten Analyse Häkchen links und Punkte rechts neben den Dimensionen an, um zu zeigen, welche die relevantesten Informationen bereitstellen:

* **Prüfzeichen** identifizieren die Dimensionen, deren Werte sich statistisch signifikant von der Benchmark unterscheiden (d. h. der Unterschied zwischen Auswahl und Benchmark ist nicht auf zufällige Zufälle zurückzuführen).
* **Punkte** geben an, in welchem Maße sich die Auswahl von der Benchmark unterscheidet. Der erste Punkt stellt die U-Statistik dar, der zweite Punkt die V-Statistik. Siehe [Die statistischen Maßnahmen](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Je heller und größer die Punkte, desto größer der Unterschied und desto relevanter die Informationen für die Dimension je nach Ihrer Auswahl (d. h., hellere, größere Punkte stellen nützlichere Informationen dar).

