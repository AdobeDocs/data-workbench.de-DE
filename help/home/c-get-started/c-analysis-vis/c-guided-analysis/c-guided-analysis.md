---
description: Eine Visualisierung einer geführten Analyse bietet Hinweise für eine weitere Analyse basierend auf den Auswahlen, die Sie in einem Arbeitsbereich treffen.
title: Geführte Analyse
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Geführte Analyse{#guided-analysis}

{{eol}}

Eine Visualisierung einer geführten Analyse bietet Hinweise für eine weitere Analyse basierend auf den Auswahlen, die Sie in einem Arbeitsbereich treffen.

Diese Visualisierung hilft Ihnen dabei herauszufinden, welche Dimensionen Ihnen mehr Informationen liefern können, d. h. diejenigen, die am stärksten mit Ihrer Auswahl korreliert werden. Die Visualisierung der geführten Analyse in Ihrer Adobe App zeigt die Dimensionen an, die für Ihren Datensatz relevant sind, wie im folgenden Beispiel: [!DNL Site] Visualisierung der geführten Analyse.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Wenn ein Dimensionsname in Rot angezeigt wird, ist er in Ihrem Datensatz nicht definiert.

Wenn Sie eine Auswahl in einem Arbeitsbereich treffen, zeigt die Visualisierung der geführten Analyse Häkchen links und Punkte rechts von den Dimensionen an, um anzuzeigen, welche die relevantesten Informationen liefern:

* **Häkchen** die Dimensionen zu identifizieren, deren Werte sich statistisch signifikant vom Benchmark unterscheiden (d. h. der Unterschied zwischen Auswahl und Benchmark ist nicht auf zufällige Zufälle zurückzuführen).
* **Punkte** geben an, in welchem Maße sich die Auswahl vom Benchmark unterscheidet. Der erste Punkt steht für die U-Statistik, der zweite für die V-Statistik. Siehe [Grundlagen zu den statistischen Kennzahlen](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Je heller und größer die Punkte, desto größer der Unterschied und desto relevanter die Informationen für die Dimension basierend auf Ihrer Auswahl (d. h. hellere, größere Punkte stellen nützlichere Informationen dar).
