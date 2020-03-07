---
description: Grundlegende Informationen zu den DataSet-Komponenten.
solution: Analytics
title: Dataset-Komponenten
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dataset-Komponenten{#dataset-components}

Grundlegende Informationen zu den DataSet-Komponenten.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Protokollquellen, Felder, Transformationen und erweiterten Dimensionen eines Datensatzes darstellen.

![](assets/vis_DependencyMap.png)

* Ein gelb-grüner Knoten stellt eine oder mehrere Protokollquellen oder einen Filter dar (z. B. eine Protokolleinstiegsbedingung), die im Datensatz definiert sind.

   * Ein Knoten für eine Protokollquelle erscheint immer am weitesten links in der Map. Wenn Ihr Datensatz über eine einzige Protokollquelle verfügt, zeigt die Zuordnung die Protokollquelle an: Name der *Protokollquelle*. Wenn Ihr Datensatz über mehrere Protokollquellen verfügt, zeigt die Zuordnung die *Anzahl* der Protokollquellen an, wobei Zahl die Anzahl der Protokollquellen ist. Wenn Ihr Datensatz beispielsweise drei Protokollquellen enthält, zeigt Ihre Zuordnung 3 Protokollquellen an.

   * Die Zuordnung zeigt für jede [!DNL log processing dataset include] Datei einen Knoten für die Protokolleintragsbedingung an, für die Konvertierung jedoch nur einen Knoten für die Protokolleintragsbedingung (sofern in der [!DNL Transformation.cfg] Datei definiert). Wenn die Protokolleingabebedingung leer ist, wird sie nicht auf der Karte angezeigt.

* Eine graue Node stellt ein Feld dar, das im Parameter &quot;Felder&quot;in einer [!DNL Log Processing.cfg] oder einer [!DNL Log Processing include] Datei aufgeführt ist.

* Eine blaue Node stellt eine Transformation dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar.

>[!NOTE]
>
>Wenn der Dataset-Ordner Ihres Profils die Datei enthält [!DNL Insight Transform.cfg], zeigt die Abhängigkeitszuordnung die Protokollquellen, Transformationen und Exporteure an, die für Transform definiert wurden. Weitere Informationen zu Transform finden Sie im Handbuch zur Konfiguration von *Datasets*.

Wenn Sie die Option [!DNL File Blocks] &quot;Anzeige einschließen&quot;aktivieren, zeigt die Zuordnung einen einzelnen blauen Knoten für alle in einer Datensatzkonfigurationsdatei definierten Transformationen und einen einzigen grünen Knoten für alle in einer Datensatzkonfigurationsdatei definierten erweiterten Dimensionen an. Weitere Informationen zu dieser Anzeigeoption finden Sie unter [Arbeiten mit Dateiblöcken](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
