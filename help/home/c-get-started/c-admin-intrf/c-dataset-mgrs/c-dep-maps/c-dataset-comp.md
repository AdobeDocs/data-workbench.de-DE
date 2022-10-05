---
description: Konzeptinformationen zu Datensatzkomponenten.
title: Komponenten von Datensätzen
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Komponenten von Datensätzen{#dataset-components}

{{eol}}

Konzeptinformationen zu Datensatzkomponenten.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Protokollquellen, Felder, Umwandlungen und erweiterten Dimensionen eines Datensatzes darstellen.

![](assets/vis_DependencyMap.png)

* Ein gelb-grüner Knoten stellt eine oder mehrere Protokollquellen oder einen Filter dar (z. B. eine Protokolleintragsbedingung), die im Datensatz definiert sind.

   * Ein Knoten für eine Protokollquelle wird immer am weitesten links in der Karte angezeigt. Wenn Ihr Datensatz über eine einzelne Protokollquelle verfügt, zeigt die Zuordnung die Protokollquelle an: *Protokollquellenname*. Wenn Ihr Datensatz mehrere Protokollquellen enthält, wird die Zuordnung angezeigt *number* Protokollquellen, wobei number die Anzahl der Protokollquellen ist. Wenn Ihr Datensatz beispielsweise drei Protokollquellen enthält, zeigt Ihre Zuordnung drei Protokollquellen an.

   * Die Zuordnung zeigt einen Knoten Protokolleintragsbedingung für jeden [!DNL log processing dataset include] Datei, aber nur ein Knoten Protokolleintragsbedingung für die Umwandlung (sofern in der Variablen [!DNL Transformation.cfg] -Datei). Wenn die Protokolleintragsbedingung leer ist, wird sie nicht auf der Karte angezeigt.

* Ein grauer Knoten stellt ein Feld dar, das im Parameter Felder in einer [!DNL Log Processing.cfg] oder [!DNL Log Processing include] -Datei.

* Ein blauer Knoten stellt eine Umwandlung dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar.

>[!NOTE]
>
>Wenn der Ordner Datensatz Ihres Profils die Datei enthält [!DNL Insight Transform.cfg], zeigt die Abhängigkeitszuordnung die Protokollquellen, Umwandlungen und Exporteure an, die für die Verwendung mit Transform definiert sind. Weitere Informationen zu Transform finden Sie in der *Anleitung zur Datensatzkonfiguration*.

Wenn Sie die Option Einschließen aktivieren [!DNL File Blocks] -Anzeigeoption, zeigt die Zuordnung einen einzelnen blauen Knoten für alle in einer Datensatzkonfigurationsdatei definierten Umwandlungen und einen einzigen grünen Knoten für alle erweiterten Dimensionen an, die in einer Datensatzkonfigurationsdatei definiert sind. Weitere Informationen zu dieser Anzeigeoption finden Sie unter [Arbeiten mit Dateiblöcken](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
