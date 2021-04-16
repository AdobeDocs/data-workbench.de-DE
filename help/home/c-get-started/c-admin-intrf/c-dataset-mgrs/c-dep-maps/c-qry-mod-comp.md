---
description: Grundlegende Informationen zu Abfrage-Modellkomponenten.
title: Komponenten des Abfragemodells
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Komponenten des Abfragemodells{#query-model-components}

Grundlegende Informationen zu Abfrage-Modellkomponenten.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Metriken, abgeleiteten Dimensionen und Filter eines Abfrage-Modells darstellen, die in den Ordnern &quot;Dimensionen&quot;, &quot;Metriken&quot;und &quot;Filter&quot;des Profils definiert sind, sowie die erweiterten Dimensionen, die im Datensatz definiert sind und die sich auf diese beziehen.

![](assets/vis_DependencyMap_QueryModel.png)

* Ein gelb-grüner Knoten stellt einen Filter dar.
* Eine violette Node stellt eine Metrik dar.
* Eine blau-grüne Node stellt eine abgeleitete Dimension dar.
* Eine grüne Node stellt eine erweiterte Dimension dar (definiert im Datensatz).
* Eine rote Node stellt eine Metrik, eine abgeleitete Dimension oder einen Filter mit einer unterbrochenen oder kreisförmigen Abhängigkeit oder einem anderen Fehler dar.

>[!NOTE]
>
>Da die Abhängigkeitszuordnung für acyclische Abhängigkeiten konzipiert ist, werden Knoten, die an zirkulären Abhängigkeiten beteiligt sind, auf der Karte möglicherweise nicht richtig angezeigt. Sie können nach zirkulären Abhängigkeiten suchen, indem Sie &quot;zirkuläre Abhängigkeit&quot;in das Textfeld [!DNL Search] eingeben. Weitere Informationen zur Funktion [!DNL Search] finden Sie unter [Suchen in einer Map](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
