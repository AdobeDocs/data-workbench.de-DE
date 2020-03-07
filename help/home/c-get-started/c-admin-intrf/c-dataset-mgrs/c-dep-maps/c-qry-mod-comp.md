---
description: Grundlegende Informationen zu Abfragemodellkomponenten.
solution: Analytics
title: Komponenten des Abfragemodells
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Komponenten des Abfragemodells{#query-model-components}

Grundlegende Informationen zu Abfragemodellkomponenten.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Metriken, abgeleiteten Dimensionen und Filter eines Abfragemodells darstellen, die in den Ordnern Dimensionen, Metriken und Filter innerhalb des Profils definiert sind, sowie die erweiterten Dimensionen, die im Datensatz definiert sind und die in irgendeiner Weise mit ihnen in Beziehung stehen.

![](assets/vis_DependencyMap_QueryModel.png)

* Ein gelb-grüner Knoten stellt einen Filter dar.
* Eine violette Node stellt eine Metrik dar.
* Eine blau-grüne Node stellt eine abgeleitete Dimension dar.
* Eine grüne Node stellt eine erweiterte Dimension dar (definiert im Datensatz).
* Eine rote Node stellt eine Metrik, eine abgeleitete Dimension oder einen Filter mit einer unterbrochenen oder kreisförmigen Abhängigkeit oder einem anderen Fehler dar.

>[!NOTE]
>
>Da die Abhängigkeitszuordnung für acyclische Abhängigkeiten konzipiert ist, werden Knoten, die an zirkulären Abhängigkeiten beteiligt sind, auf der Karte möglicherweise nicht richtig angezeigt. Sie können nach zirkulären Abhängigkeiten suchen, indem Sie &quot;zirkuläre Abhängigkeit&quot;in das [!DNL Search] Textfeld eingeben. Weitere Informationen zur [!DNL Search] Funktion finden Sie unter [Suchen in einer Map](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

