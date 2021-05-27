---
description: Radardiagramme bieten einen schnellen Fokus auf die Bereiche, die am dringendsten beachtet werden müssen, indem sie eine visuelle Sicht auf eine Reihe von Metriken bieten und wie diese sich auf- bzw. unterscheiden.
title: Visualisierung im Netzdiagramm
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Visualisierung im Netzdiagramm{#radar-visualization}

Radardiagramme bieten einen schnellen Fokus auf die Bereiche, die am dringendsten beachtet werden müssen, indem sie eine visuelle Sicht auf eine Reihe von Metriken bieten und wie diese sich auf- bzw. unterscheiden.

Oft benötigen Sie mehr als eine Metrik, um ausgewählte Beobachtungen in einem Arbeitsbereich zu verstehen und auszuwerten.

Diese Visualisierung ist nützlich für Vergleiche oder Benchmarks zwischen den Tabellenauswahlen. Sie können beispielsweise eine Workspace-Tabelle hinzufügen, in der Stores aufgelistet werden, und dann eine Radarvisualisierung mit Metriken wie Umsatz, Besucher und Seitenansichten hinzufügen. (Wie im folgenden Beispiel auf dem Bildschirm gezeigt.) Wenn Sie Store-Auswahlen in der Tabelle vornehmen, verschiebt sich der Radardiagramm-Fußabdruck, wodurch Schwächen oder Stärken in den Metriken für den ausgewählten Store identifiziert werden.

Jeder Radialwert eines Radardiagramms ist eine Metrik, und es sind mindestens drei Metriken erforderlich. Die Metrikdaten werden im Verhältnis zu einer verankerten Metrik dargestellt. Die verankerte Metrik und der Parameter Skalierung bis Anker für jede Metrik bestimmen die Skalierung der Metriken in Bezug auf Benchmarks.

**So erstellen Sie eine Radarvisualisierung**

1. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und klicken Sie dann auf **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Um Metriken hinzuzufügen, klicken Sie mit der rechten Maustaste in die Visualisierung und wählen Sie **[!UICONTROL Add Metric]** aus.
1. Um eine Metrik im Diagramm zu verankern, klicken Sie mit der rechten Maustaste auf eine Metrik und wählen Sie die folgende Option:

   **Anker für diese Metrik:** Verwendet diese Metrik als Benchmark, zu dem andere Metriken gezeichnet werden. Sie können eine Metrik gleichzeitig verankern. Jede Metrik im Diagramm wird durch die aktive Workspace-Auswahl oder durch keinen Filter gefiltert. Das Benchmark-Verhältnis zwischen diesen beiden Werten wird auf der Achse zwischen dem Mittelpunkt des Diagramms und dem Metriknamen auf dem Radar dargestellt. Zero ist in der Mitte gezeichnet.

1. Um eine Metrik mit der verankerten Metrik zu skalieren, klicken Sie mit der rechten Maustaste auf die Metrik und wählen Sie die folgende Option:

   **Mit Anker skalieren:** Wenn diese Metrik aktiviert ist, wird die Achse dieser Metrik so skaliert, dass das Benchmark-Verhältnis für die ausgewählte Ankermetrik im Kreis dargestellt wird, wobei sich die Null in der Mitte befindet. Wenn diese Option nicht ausgewählt ist, stellt der Kreis ein Benchmark-Verhältnis von 1 dar. In der Regel aktivieren Sie &quot;Skalierung mit Anker&quot;für zählbare Metriken wie Besucher oder Seitenansichten und deaktivieren Sie sie für Verhältnismetriken wie Konversion, durchschnittliche Sitzungsdauer oder Seitenansichten pro Sitzung.
