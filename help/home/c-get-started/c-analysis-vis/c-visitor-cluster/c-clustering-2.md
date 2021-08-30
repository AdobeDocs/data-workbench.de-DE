---
description: Der Cluster Builder enthält jetzt einen KMeans++-Algorithmus (bisher wurde nur der KMeans-Algorithmus unterstützt), der einen schnelleren Ansatz bei der Suche nach Zentren für einen beschleunigten Cluster-Generierungsprozess nutzt.
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Clustering 2.0{#clustering}

Der Cluster Builder enthält jetzt einen KMeans++-Algorithmus (bisher wurde nur der KMeans-Algorithmus unterstützt), der einen schnelleren Ansatz bei der Suche nach Zentren für einen beschleunigten Cluster-Generierungsprozess nutzt.

## KMeans-Algorithmen {#section-92383a1be1d6402c95a25c902e90b850}

Im [Cluster Builder](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en) können Sie jetzt **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** auswählen, um Algorithmen beim Definieren von Clustern auszuwählen.

* **[!UICONTROL KMeans]**. Dieser Algorithmus verwendet Canopy-Clustering, um die Zentren des Clusters zu definieren.
* **[!UICONTROL KMeans++]**. Dieser Algorithmus beschleunigt die Clusterbildung bei der Ausführung mit großen Datensätzen.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ ist eine verbesserte Implementierung des KMeans-Clustering-Algorithmus, da es eine bessere Initialisierung der anfänglichen k-Zentren ermöglicht. (Der ursprüngliche KMeans-Algorithmus wählt anfängliche Zentren zufällig aus.) KMeans++ wählt das erste Zentrum zufällig aus. Die verbleibenden k-1-Zentren werden einzeln ausgewählt, je nachdem, wie weit ein Datenpunkt vom nächstgelegenen Rechenzentrum entfernt ist. Die am weitesten entfernten Datenpunkte haben eine bessere Chance, als ein neues Zentrum ausgewählt zu werden als nahe gelegene Datenpunkte. Nach der Auswahl des ersten Zentrums wird das Verfahren genau so durchgeführt wie das ursprüngliche KMeans-Clustering.

Der Workflow für KMeans++ ist mit dem Workflow für KMeans-Clustering identisch, allerdings müssen Sie im Cluster-Builder **Optionen** > **Algorithm** > **KMeans+** auswählen.

>[!NOTE]
>
>Jede DPU führt ihr eigenes KMeans++-Verfahren für ihren eigenen Datenbereich aus. Wenn die DPU über ausreichend verfügbaren Speicher verfügt (das Verhältnis ist in der Datei PAServer.cfg konfigurierbar), werden die Daten der beteiligten Variablen in den Speicher gebracht. Die verbleibenden k-1 anfänglichen Mittelauswahl und konvergierenden Iterationen erfolgen alle im Speicher, was schneller ist als das vorherige KMeans Clustering.
