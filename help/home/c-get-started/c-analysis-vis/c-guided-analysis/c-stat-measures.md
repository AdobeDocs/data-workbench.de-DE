---
description: Zur Unterstützung der Statistiken bietet Data Workbench drei statistische Kennzahlen in der Visualisierung der geführten Analyse.
title: Statistische Messgrößen
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
exl-id: 166ff98b-d531-4b31-897e-0c7fedbd2f4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Statistische Messgrößen{#statistical-measures}

{{eol}}

Zur Unterstützung der Statistiken bietet Data Workbench drei statistische Kennzahlen in der Visualisierung der geführten Analyse.

>[!NOTE]
>
>Obwohl Ihnen die Mathematik dabei helfen kann, über die Korrelationen in Ihren Daten zu urteilen, muss auch der Kontext, der die Daten umgibt, berücksichtigt werden.

* **Chi Sq p** ist ein Test von statistischer Bedeutung, der das Erscheinungsbild des Kontrollkästchens in der Visualisierung steuert. Mathematisch ist es eine Wahrscheinlichkeit, dass wir die Null-Hypothese ablehnen, die besagt, dass die Unterschiede zwischen den beiden Gruppen durch zufällige Variationen erklärt werden können. Wenn der Chi Sq p-Wert kleiner als fast 100 % ist, können wir die Korrelation unabhängig von der gemessenen Stärke ignorieren (wie in den folgenden U-Statistik- und V-Statistik-Abschnitten beschrieben).
* **U-Statistik** ist ein Maß für die Stärke der statistischen Korrelation. Mathematisch kommt es aus einem Zweig der Mathematik, der Informationstheorie genannt wird, und ist eng mit dem Konzept der gegenseitigen Information zwischen den Verteilungen der beiden Gruppen verbunden. Alternativ kann man davon ausgehen, dass es sich um die Komprimierbarkeit einer Gruppe mit einem optimalen Kodierungsschema für die andere Gruppe handelt. Praktisch funktioniert diese Kennzahl sehr gut im allgemeinen Fall einer Dimension mit vielen Elementen, die nur wenige Besucher enthalten. Die Maßnahme reicht von 0 (schwach) bis 1 (stark).
* **V Statistik** ist auch ein Maß für die Stärke der statistischen Korrelation. Mathematisch betrachtet, ist es mit der bekannten Cramer V-Statistik verwandt, die sich nur durch einen Normalisierungsschritt unterscheidet, der dazu dient, die Symmetrie der Maßnahme in Bezug auf die Selektionsumkehrung zu verbessern. Praktisch funktioniert diese Maßnahme bei vielen Arten von Dimensionen recht gut und steht im Zusammenhang mit einer häufig verwendeten statistischen Kennzahl. Die Maßnahme reicht von 0 (schwach) bis 1 (stark).

>[!NOTE]
>
>Die U- und V-Statistiken wurden ausgewählt, um einander zu ergänzen. Jede davon wurde so optimiert, dass Korrelationen erkannt werden, auf die die andere nicht so stark reagiert.

Mithilfe dieser Visualisierung als Leitfaden können Sie Ihrem Arbeitsbereich weitere Visualisierungen hinzufügen, um basierend auf der Auswahl mehr Einblicke in Ihre Daten zu erhalten.

Folgendes [!DNL Site] Beispiel enthält ein Balkendiagramm, das Sitzungen für Tage im Januar, Februar, März und April anzeigt. Beachten Sie, dass ein Tag im Januar ausgewählt ist.

![](assets/vis_GuidedAnalysis_withVis.png)

Die Visualisierung der geführten Analyse in der linken unteren Ecke des Arbeitsbereichs zeigt an, dass die Dimension Sitzungsnummer nützliche Informationen zum ausgewählten Tag bietet.

Wenn Sie sich das Balkendiagramm für die Sitzungsnummer in der rechten unteren Ecke des Arbeitsbereichs ansehen, können Sie feststellen, dass die Daten für Sitzungsnummer 2 viel niedriger sind als der Benchmark. Daher können wir zu dem Schluss kommen, dass am ausgewählten Tag weniger Sitzungen als üblich stattgefunden haben. Um ein Balkendiagramm für eine der Dimensionen anzuzeigen, die in der Visualisierung der geführten Analyse aufgeführt sind, wählen Sie einfach die Dimension aus, indem Sie mit der Maus auf die Dimension klicken.
