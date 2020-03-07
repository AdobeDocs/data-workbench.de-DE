---
description: Der Cluster Builder enthält jetzt einen KMeans++-Algorithmus (bisher wurde nur der KMeans-Algorithmus unterstützt), der einen schnelleren Ansatz bei der Suche nach Zentren für einen beschleunigten Prozess der Clusterbildung verwendet.
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Clustering 2.0{#clustering}

Der Cluster Builder enthält jetzt einen KMeans++-Algorithmus (bisher wurde nur der KMeans-Algorithmus unterstützt), der einen schnelleren Ansatz bei der Suche nach Zentren für einen beschleunigten Prozess der Clusterbildung verwendet.

## KMeans-Algorithmen {#section-92383a1be1d6402c95a25c902e90b850}

Im [Cluster Builder](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html)können Sie jetzt beim Definieren von Clustern **[!UICONTROL Options]** > wählen, **[!UICONTROL Algorithm]** um Algorithmen auszuwählen.

* **[!UICONTROL KMeans]**. Dieser Algorithmus verwendet Baumkronen-Clustering, um die Zentren des Clusters zu definieren.
* **[!UICONTROL KMeans++]**. Dieser Algorithmus beschleunigt die Clusterbildung, wenn er mit großen Datensätzen ausgeführt wird.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ ist eine verbesserte Implementierung des KMeans-Clustering-Algorithmus, da es eine bessere Initialisierung der anfänglichen k-Zentren ermöglicht. (Der ursprüngliche KMeans-Algorithmus wählt anfängliche Zentren zufällig aus.) KMeans++ wählt das erste Zentrum zufällig aus. Die verbleibenden k-1-Zentren werden je nach Entfernung eines Datenpunkts zum nächstgelegenen vorhandenen Zentrum ausgewählt. Die am weitesten entfernten Datenpunkte haben eine bessere Chance, als nahe gelegene Datenpunkte als neue Zentren gewählt zu werden. Nach der Auswahl des anfänglichen Zentrums wird die Prozedur genau wie das ursprüngliche KMeans-Clustering durchgeführt.

Der Arbeitsablauf für KMeans++ ist mit dem Arbeitsablauf für KMeans-Clustering identisch, allerdings müssen Sie im Cluster-Builder **Optionen** > **Algorithmus** > **KMeans++** auswählen.

>[!NOTE]
>
>Jede DPU führt ihre eigene KMeans++-Prozedur auf ihrem eigenen Datenteil aus. Wenn die DPU über ausreichend verfügbaren Speicher verfügt (das Verhältnis ist in der Datei PAServer.cfg konfigurierbar), werden die Daten der beteiligten Variablen in den Speicher geladen. Die verbleibenden k-1 anfänglichen Mittelauswahlen und konvergierende Iterationen passieren alle im Speicher, was schneller ist als das vorherige KMeans Clustering.

