---
description: Konzeptinformationen zu Abfragemodellkomponenten.
title: Komponenten des Abfragemodells
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Komponenten des Abfragemodells{#query-model-components}

{{eol}}

Konzeptinformationen zu Abfragemodellkomponenten.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Metriken, abgeleiteten Dimensionen und Filter eines Abfragemodells darstellen, die in den Profilordnern Dimensionen, Metriken und Filter definiert sind, sowie die im Datensatz definierten erweiterten Dimensionen, die sich auf sie beziehen.

![](assets/vis_DependencyMap_QueryModel.png)

* Ein gelb-grüner Knoten stellt einen Filter dar.
* Ein violetter Knoten stellt eine Metrik dar.
* Ein blau-grüner Knoten stellt eine abgeleitete Dimension dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar (definiert im Datensatz).
* Ein roter Knoten stellt eine Metrik, eine abgeleitete Dimension oder einen Filter mit einer unterbrochenen oder zirkulären Abhängigkeit oder einem anderen Fehler dar.

>[!NOTE]
>
>Da die Abhängigkeitskarte für acyclische Abhängigkeiten entwickelt wurde, werden Knoten, die an zirkulären Abhängigkeiten beteiligt sind, möglicherweise nicht richtig auf der Karte angezeigt. Sie können nach zirkulären Abhängigkeiten suchen, indem Sie &quot;zirkuläre Abhängigkeit&quot;in die [!DNL Search] Textfeld. Weitere Informationen zum [!DNL Search] -Funktion, siehe [Suchen in einer Zuordnung](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
