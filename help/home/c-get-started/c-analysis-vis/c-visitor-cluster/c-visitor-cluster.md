---
description: Mithilfe des Besucher-Clustering können Sie Kundenmerkmale nutzen, um Besucher dynamisch zu kategorisieren und Cluster-Sets basierend auf ausgewählten Dateneingaben zu generieren. Auf diese Weise identifizieren Sie Gruppen, die ähnliche Interessen und Verhaltensweisen für die Analyse und das Targeting von Kunden haben.
title: Besucher-Clustering
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Besucher-Clustering{#visitor-clustering}

Mithilfe des Besucher-Clustering können Sie Kundenmerkmale nutzen, um Besucher dynamisch zu kategorisieren und Cluster-Sets basierend auf ausgewählten Dateneingaben zu generieren. Auf diese Weise identifizieren Sie Gruppen, die ähnliche Interessen und Verhaltensweisen für die Analyse und das Targeting von Kunden haben.

**Clustering-Prozess**

Beim Clustering müssen Sie Metriken und Dimensionselemente identifizieren, die als Eingaben verwendet werden sollen, und Sie können eine bestimmte Zielgruppe auswählen, um diese Elemente zur Erstellung spezifizierter Cluster anzuwenden. Wenn Sie den Clustering-Prozess ausführen, verwendet das System die Metrik- und Dimensionseingaben, um geeignete Ausgangszentren für die angegebene Anzahl von Clustern zu bestimmen. Diese Zentren werden dann als Ausgangspunkt für die Anwendung des K-Means-Algorithmus verwendet.

![](assets/K_algorithm.png)

* Die anfänglichen Zentren werden über einen Canopy Clustering Pass intelligent ausgewählt.
* Datencluster werden erstellt, indem jeder Datenpunkt der nächstgelegenen Mitte zugeordnet wird.
* Das Mittel jedes K-Clusters wird zum neuen Zentrum.
* Der Algorithmus wird in den Schritten 2 und 3 wiederholt, bis die Konvergenz erreicht ist. Das kann mehrere Pässe dauern.

Mit dem Menü **[!UICONTROL Maximum Iterations]** im Menü **[!UICONTROL Options]** kann der Analyst die maximale Anzahl von Iterationen angeben, die vom Clustering-Algorithmus ausgeführt werden sollen. Die Einstellung dieser Option kann zu einem schnelleren Abschluss des Clustering-Prozesses auf der Grundlage der maximalen Iterationsgrenze auf Kosten der exakten Konvergenz der Clusterzentren führen.

>[!NOTE]
>
>Sobald die Cluster definiert wurden, kann die Cluster-Dimension wie jede andere Dimension gespeichert werden. Es kann auch in den Cluster Explorer geladen werden, um die Trennung von Cluster-Zentren zu untersuchen.

Im Cluster Builder können Sie **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** auswählen, um Algorithmen beim Definieren von Clustern auszuwählen. Derzeit werden 3 Algorithmen unterstützt:

* KMeans
* Kbedeutet`++`
* Maximierung der Erwartungen

Es gibt 2 Möglichkeiten, den Cluster-Prozess auszuführen:

* Methode 1 - Klicken Sie im Fenster &quot;Clustervisualisierung&quot;auf **[!UICONTROL Go]**.
* Methode 2 - Klicken Sie im Fenster für die Clustervisualisierung auf **[!UICONTROL Submit]**, das den Clusterauftrag direkt an den Server sendet. Sie können den Fortschritt über die Option &quot;Detaillierter Status für Abfrage&quot;verfolgen.

![](assets/dwb_visitorclustering.png)

Der Algorithmus unterliegt folgenden Einschränkungen:

1. Wenn Sie Methode 1 verwenden, können Sie einen der unterstützten Clustering-Algorithmen auswählen.
1. Wenn Sie Methode 2 verwenden, können Sie kmittel oder kmittel++ auswählen. Die Option zur Maximierung der Erwartungen ist nicht verfügbar.

>[!NOTE]
>
>In der Datei [!DNL DPU.cfg] ist der Wert für &quot;Abfrage, Speichergrenze&quot;standardmäßig auf 500 MB festgelegt. Dieser Wert muss erhöht werden, während mehrere Clustering-Aufträge ausgeführt werden. Wenn Sie beispielsweise 5 Cluster-Aufträge parallel ausführen, erhöhen Sie diesen Wert auf 1 GB. Es gibt keine Möglichkeit, den Clusterauftrag abzubrechen, ohne den Server neu zu starten.

**Empfehlungen**

Die Anzahl der Iterationen (Häufigkeit, mit der die Daten gescannt werden) und der von Ihnen konfigurierte Konvergenzschwellenwert wirken sich stark auf die Clusterleistung aus. Die folgende Tabelle enthält eine weiter gefasste Richtlinie, die Sie befolgen können:

| Anzahl Cluster | Algorithmus | Iterationen | Konvergenzschwellenwert | Normalisierung |
|---|---|---|---|---|
| 6 | Kbedeutet | 25.50 | 1e-3 | Min.-Max |
| 6 | Kbedeutet | 25.50 | 1e-6 | Min.-Max |
| 6 | KMED+ | 50 | 1e-6 | Min.-Max |
