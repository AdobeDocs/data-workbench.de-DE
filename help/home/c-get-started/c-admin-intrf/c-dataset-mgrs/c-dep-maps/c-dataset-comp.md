---
description: Konzeptinformationen zu Datensatzkomponenten.
title: Komponenten von Datensätzen
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Komponenten von Datensätzen{#dataset-components}

Konzeptinformationen zu Datensatzkomponenten.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Protokollquellen, Felder, Umwandlungen und erweiterten Dimensionen eines Datensatzes darstellen.

![](assets/vis_DependencyMap.png)

* Ein gelb-grüner Knoten stellt eine oder mehrere Protokollquellen oder einen Filter dar (z. B. eine Protokolleintragsbedingung), die im Datensatz definiert sind.

   * Ein Knoten für eine Protokollquelle wird immer am weitesten links in der Karte angezeigt. Wenn Ihr Datensatz über eine einzelne Protokollquelle verfügt, zeigt die Zuordnung die Protokollquelle an: *log source name*. Wenn Ihr Datensatz mehrere Protokollquellen enthält, zeigt die Zuordnung *number* Protokollquellen an, wobei number die Anzahl der Protokollquellen ist. Wenn Ihr Datensatz beispielsweise drei Protokollquellen enthält, zeigt Ihre Zuordnung drei Protokollquellen an.

   * Die Zuordnung zeigt einen Knoten Protokolleintragsbedingung für jede [!DNL log processing dataset include]-Datei an, jedoch nur einen Knoten Protokolleintragsbedingung für die Transformation (sofern in der Datei [!DNL Transformation.cfg] definiert). Wenn die Protokolleintragsbedingung leer ist, wird sie nicht auf der Karte angezeigt.

* Ein grauer Knoten stellt ein Feld dar, das im Parameter Felder in einer Datei [!DNL Log Processing.cfg] oder [!DNL Log Processing include] aufgeführt ist.

* Ein blauer Knoten stellt eine Umwandlung dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar.

>[!NOTE]
>
>Wenn der Datensatzordner Ihres Profils die Datei [!DNL Insight Transform.cfg] enthält, zeigt die Abhängigkeitszuordnung die Protokollquellen, Transformationen und Exporteure an, die für die Verwendung mit Transform definiert sind. Weitere Informationen zu Transform finden Sie im *Handbuch zur Datensatzkonfiguration*.

Wenn Sie die Anzeigeoption [!DNL File Blocks] einschließen aktivieren, zeigt die Zuordnung einen einzelnen blauen Knoten für alle in einer Datensatzkonfigurationsdatei definierten Umwandlungen und einen einzigen grünen Knoten für alle in einer Datensatzkonfigurationsdatei definierten erweiterten Dimensionen an. Weitere Informationen zu dieser Anzeigeoption finden Sie unter [Arbeiten mit Dateiblöcken](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
