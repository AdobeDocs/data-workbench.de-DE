---
description: Zur Unterstützung der Statistiken stellt Data Workbench drei statistische Maßnahmen in der Visualisierung der geführten Analyse bereit.
solution: Analytics
title: Statistische Maßnahmen
topic: Data workbench
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Statistische Maßnahmen{#statistical-measures}

Zur Unterstützung der Statistiken stellt Data Workbench drei statistische Maßnahmen in der Visualisierung der geführten Analyse bereit.

>[!NOTE]
>
>Obwohl die Mathematik Ihnen dabei helfen kann, über die Korrelationen in Ihren Daten zu urteilen, muss auch der Kontext, der die Daten umgibt, berücksichtigt werden.

* **Chi Sq p** ist ein Test von statistischer Bedeutung, der das Erscheinungsbild des Kontrollkästchens in der Visualisierung steuert. Mathematisch gesehen ist es wahrscheinlich, dass wir die Null-Hypothese ablehnen können, die besagt, dass die Unterschiede zwischen den beiden Gruppen durch zufällige Variationen erklärt werden können. Wenn der p-Wert des Chi-Sq-Werts kleiner als fast 100 % ist, können wir die Korrelation unabhängig von der gemessenen Stärke ignorieren (wie in den folgenden U-Statistik- und V-Statistikabschnitten beschrieben).
* **Die U-Statistik** ist ein Maß für die Stärke der statistischen Korrelation. Mathematisch stammt sie aus einem Zweig der Mathematik, der Informationstheorie genannt wird, und ist eng mit dem Konzept der gegenseitigen Information zwischen den Verteilungen der beiden Gruppen verwandt. Alternativ kann man es als die Komprimierbarkeit einer Gruppe betrachten, die ein optimales Kodierschema für die andere Gruppe erhält. Praktisch funktioniert diese Messung sehr gut, wenn eine Dimension mit vielen Elementen nur wenige Besucher enthält. Die Maßnahme reicht von 0 (schwach) bis 1 (stark).
* **Die V-Statistik** ist auch ein Maß für die Stärke der statistischen Korrelation. Mathematisch ist es mit der bekannten Cramer V-Statistik verwandt, die sich nur durch einen Normalisierungsschritt unterscheidet, der die Symmetrie der Maßnahme in Bezug auf die Auswahlinversion verbessern soll. Praktisch funktioniert diese Maßnahme bei vielen Arten von Dimensionen recht gut und steht im Zusammenhang mit einer häufig verwendeten statistischen Messgröße. Die Maßnahme reicht von 0 (schwach) bis 1 (stark).

>[!NOTE]
>
>Die U- und V-Statistiken wurden ausgewählt, um sich gegenseitig zu ergänzen. Jede dieser Statistiken wurde so eingestellt, dass Korrelationen erkannt werden, auf die die andere möglicherweise nicht so stark reagiert.

Mithilfe dieser Visualisierung als Anleitung können Sie Ihrem Arbeitsbereich weitere Visualisierungen hinzufügen, um anhand der Auswahl weitere Einblicke in Ihre Daten zu erhalten.

Das folgende [!DNL Site] Beispiel enthält ein Balkendiagramm, das Sitzungen für Tage im Januar, Februar, März und April anzeigt. Beachten Sie, dass ein Tag im Januar ausgewählt ist.

![](assets/vis_GuidedAnalysis_withVis.png)

Die Visualisierung der geführten Analyse in der linken unteren Ecke des Arbeitsbereichs zeigt an, dass die Dimension &quot;Sitzungsnummer&quot;nützliche Informationen zum ausgewählten Tag bietet.

Wenn Sie sich das Sitzungsnummer-Balkendiagramm in der unteren rechten Ecke des Arbeitsbereichs ansehen, können Sie sehen, dass die Daten für Sitzung Nr. 2 viel niedriger sind als die Benchmark. Daher können wir zu dem Schluss kommen, dass am ausgewählten Tag weniger Sitzungen als üblich stattgefunden haben. Um ein Balkendiagramm für eine der in der Visualisierung der geführten Analyse aufgeführten Dimensionen anzuzeigen, wählen Sie einfach die Dimension aus, indem Sie mit der Maus auf die Dimension klicken.
