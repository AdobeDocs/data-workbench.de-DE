---
description: Radardiagramme bieten eine schnelle Fokussierung auf die Bereiche, die am dringendsten beachtet werden müssen, indem sie eine visuelle Ansicht der Metriken sowie deren Beziehung und Unterschiede bieten.
solution: Analytics
title: Radarvisualisierung
topic: Data workbench
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Radarvisualisierung{#radar-visualization}

Radardiagramme bieten eine schnelle Fokussierung auf die Bereiche, die am dringendsten beachtet werden müssen, indem sie eine visuelle Ansicht der Metriken sowie deren Beziehung und Unterschiede bieten.

Häufig benötigen Sie mehr als eine Metrik, um ausgewählte Beobachtungen in einem Arbeitsbereich zu verstehen und zu bewerten.

Diese Visualisierung ist nützlich für Vergleiche oder Benchmarks zwischen den Tabellenauswahlen. Sie können beispielsweise eine Tabelle &quot;Arbeitsbereich&quot;hinzufügen, in der die Stores aufgelistet sind, und dann eine Radarvisualisierung mit Metriken wie Umsatz, Besucher und Seitenansichten hinzufügen. (Wie im folgenden Verfahren im Bildschirm dargestellt.) Wenn Sie eine Speicherauswahl in der Tabelle vornehmen, ändert sich der Fußabdruck des Radardiagramms, wodurch Schwächen oder Stärken in den Metriken für den ausgewählten Store identifiziert werden.

Jeder Radial eines Radardiagramms ist eine Metrik, und es sind mindestens drei Metriken erforderlich. Die Metrikdaten werden im Verhältnis zu einer verankerten Metrik dargestellt. Die verankerte Metrik und der Parameter &quot;Maßstab bis Anker&quot;für jede Metrik bestimmen die Skalierung der Metriken in Bezug auf Benchmarks.

**So erstellen Sie eine Radarvisualisierung**

1. Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und klicken Sie dann auf **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Klicken Sie zum Hinzufügen von Metriken mit der rechten Maustaste in die Visualisierung und wählen Sie **[!UICONTROL Add Metric]**.
1. Um eine Metrik im Diagramm zu verankern, klicken Sie mit der rechten Maustaste auf eine Metrik und wählen Sie die folgende Option:

   **Diese Metrik verankern:** Verwendet diese Metrik als Benchmark, zu dem andere Metriken gezogen werden. Sie können eine Metrik gleichzeitig verankern. Jede Metrik im Diagramm wird durch die aktive Arbeitsflächenauswahl oder durch keinen Filter gefiltert. Das Vergleichsverhältnis zwischen diesen beiden Werten wird auf der Achse zwischen dem Mittelpunkt des Diagramms und dem Metriknamen auf dem Radar dargestellt. Null wird in der Mitte dargestellt.

1. Um eine Metrik mit der verankerten Metrik zu skalieren, klicken Sie mit der rechten Maustaste auf die Metrik und wählen Sie die folgende Option:

   **Mit Anker skalieren:** Bei Aktivierung wird die Achse dieser Metrik so skaliert, dass das Benchmark-Verhältnis für die ausgewählte Ankermetrik im Kreis dargestellt wird, wobei sich die Null in der Mitte befindet. Wenn diese Option nicht ausgewählt ist, stellt der Kreis ein Benchmark-Verhältnis von 1 dar. In der Regel aktivieren Sie die Option &quot;Skalierung mit Anker&quot;für zählbare Metriken wie Besucher oder Seitenansichten und deaktivieren Sie sie für Verhältnismetriken wie Umrechnung, durchschnittliche Sitzungsdauer oder Seitenansichten pro Sitzung.

