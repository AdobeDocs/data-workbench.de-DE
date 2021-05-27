---
description: Mit dem Besucher-Clustering können Sie Kundenmerkmale nutzen, um Besucher dynamisch zu kategorisieren und basierend auf ausgewählten Dateneingaben Cluster-Sets zu generieren, um Gruppen zu identifizieren, die ähnliche Interessen und Verhaltensweisen für die Kundenanalyse und das Targeting haben.
title: Besucher-Clustering
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Besucher-Clustering{#visitor-clustering}

Mit dem Besucher-Clustering können Sie Kundenmerkmale nutzen, um Besucher dynamisch zu kategorisieren und basierend auf ausgewählten Dateneingaben Cluster-Sets zu generieren, um Gruppen zu identifizieren, die ähnliche Interessen und Verhaltensweisen für die Kundenanalyse und das Targeting haben.

**Clustering-Prozess**

Der Clustering-Prozess erfordert, dass Sie Metriken und Dimensionselemente identifizieren, die als Eingaben verwendet werden sollen, und Sie können eine bestimmte Zielpopulation auswählen, um diese Elemente auf die Erstellung spezifizierter Cluster anzuwenden. Wenn Sie den Clustering-Prozess ausführen, verwendet das System die Eingabe von Metriken und Dimensionen, um geeignete Anfangszentren für die angegebene Anzahl von Clustern zu bestimmen. Diese Zentren werden dann als Ausgangspunkt für die Anwendung des K-Means-Algorithmus verwendet.

![](assets/K_algorithm.png)

* Die ersten Zentren werden mithilfe eines Canopy-Clustering-Passes intelligent ausgewählt.
* Datencluster werden erstellt, indem jeder Datenpunkt dem nächstgelegenen Zentrum zugeordnet wird.
* Der Mittelwert jedes K-Clusters wird zum neuen Zentrum.
* Der Algorithmus wird in den Schritten 2 und 3 wiederholt, bis die Konvergenz erreicht ist. Das kann mehrere Durchgänge dauern.

Mit dem Menü **[!UICONTROL Maximum Iterations]** im Menü **[!UICONTROL Options]** können Analysten die maximale Anzahl von Iterationen angeben, die vom Clustering-Algorithmus ausgeführt werden sollen. Die Festlegung dieser Option kann zu einer schnelleren Fertigstellung des Clustering-Prozesses auf der Grundlage der maximalen Iterationsbegrenzung auf Kosten der exakten Konvergenz der Cluster-Zentren führen.

>[!NOTE]
>
>Sobald die Cluster definiert wurden, kann die Cluster-Dimension wie jede andere Dimension zur Verwendung gespeichert werden. Es kann auch in den Cluster Explorer geladen werden, um die Trennung von Cluster-Zentren zu untersuchen.

Im Cluster Builder können Sie **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** auswählen, um beim Definieren von Clustern Algorithmen auszuwählen. Derzeit werden drei Algorithmen unterstützt:

* KMeans
* Kmittel`++`
* Maximierung der Erwartungen

Es gibt 2 Möglichkeiten, den Clustering-Prozess auszuführen:

* Methode 1 - Klicken Sie im Fenster zur Clustervisualisierung auf **[!UICONTROL Go]** .
* Methode 2 - Klicken Sie im Fenster zur Clustervisualisierung auf **[!UICONTROL Submit]**, wodurch der Clustering-Auftrag direkt an den Server gesendet wird. Sie können den Fortschritt über die Option &quot;Detaillierter Status für Abfrage&quot;verfolgen.

![](assets/dwb_visitorclustering.png)

Der Algorithmus weist die folgenden Einschränkungen auf:

1. Wenn Sie Methode 1 verwenden, können Sie einen der unterstützten Clustering-Algorithmen auswählen.
1. Wenn Sie Methode 2 verwenden, können Sie kmittel oder kmittel++ auswählen. Die Option zur Maximierung der Erwartungen ist nicht verfügbar.

>[!NOTE]
>
>In der Datei [!DNL DPU.cfg] ist der Wert für &quot;Abfrage, Speicherbegrenzung&quot;standardmäßig auf 500 MB festgelegt. Dieser Wert muss erhöht werden, während mehrere Clustering-Aufträge ausgeführt werden. Wenn Sie beispielsweise 5 Clustering-Aufträge parallel ausführen, erhöhen Sie diesen Wert auf 1 GB. Es gibt keine Möglichkeit, den Clustering-Auftrag abzubrechen, ohne den Server neu zu starten.

**Empfehlungen**

Die Anzahl der Iterationen (Häufigkeit, mit der die Daten gescannt werden) und die Konvergenzschwelle, die Sie konfigurieren, wirken sich grob auf die Clustering-Performance aus. Die folgende Tabelle enthält eine umfassendere Richtlinie, die Sie befolgen können:

| Anzahl der Cluster | Algorithmus | Iterationen | Konvergenzschwellenwert | Normalisierung |
|---|---|---|---|---|
| 6 | Kbedeutet | 25,50 | 1e-3 | Min.-Max |
| 6 | Kbedeutet | 25,50 | 1e-6 | Min.-Max |
| 6 | Kbedeutet+ | 50 | 1e-6 | Min.-Max |
