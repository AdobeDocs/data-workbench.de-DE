---
description: Wenn Sie Datensatzkomponenten auf einer Abhängigkeitszuordnung anzeigen, haben Sie die Möglichkeit, die Anzeigeoption Dateiblöcke einschließen zu aktivieren.
title: Dateiblöcke
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Dateiblöcke{#file-blocks}

{{eol}}

Wenn Sie Datensatzkomponenten auf einer Abhängigkeitszuordnung anzeigen, haben Sie die Möglichkeit, die Anzeigeoption Dateiblöcke einschließen zu aktivieren.

Wenn diese Option aktiviert ist, zeigt die Zuordnung einen einzelnen blauen Knoten für alle in einer Datensatzkonfigurationsdatei definierten Umwandlungen und einen einzigen grünen Knoten für alle erweiterten Dimensionen an, die in einer Datensatzkonfigurationsdatei definiert sind. Wenn beispielsweise eine [!DNL log processing dataset include] enthält die Definitionen der drei Umwandlungen. Die Zuordnung zeigt einen blauen Knoten an, der die drei Umwandlungen darstellt. Gleichermaßen gilt, wenn ein [!DNL transformation dataset include] -Datei enthält die Definitionen von zwei erweiterten Dimensionen. Die Karte zeigt einen grünen Knoten an, der die beiden erweiterten Dimensionen darstellt.

## Umwandlungsblöcke {#section-c442730394264a0b850792a32eaaa2da}

Jeder blaue Knoten ist ein Transformationsbaustein und verfügt über die folgenden Optionen:

* Um die Eingabefelder des Umwandlungsblocks anzuzeigen, klicken Sie mit der rechten Maustaste auf den Knoten des Bausteins und klicken Sie auf **[!UICONTROL Inputs]**.
* Um die Ausgabefelder des Umwandlungsblocks anzuzeigen, klicken Sie mit der rechten Maustaste auf den Knoten des Bausteins und klicken Sie auf **[!UICONTROL Outputs]**.
* Klicken Sie mit der rechten Maustaste auf den Knoten des Bausteins und klicken Sie auf die Schaltfläche **[!UICONTROL Edit Configuration]**. Der angezeigte Callout enthält die gesamte Konfigurationsdatei, in der alle Umwandlungen definiert sind. Anschließend können Sie die Parameter nach Bedarf bearbeiten. Weitere Informationen zu diesen Parametern finden Sie im Abschnitt *Anleitung zur Datensatzkonfiguration*.

* Um alle Umwandlungen im Baustein anzuzeigen, klicken Sie mit der rechten Maustaste auf den Knoten des Umwandlungsblocks und klicken Sie auf **[!UICONTROL Show Details]**. Der angezeigte Callout enthält eine weitere Abhängigkeitszuordnung, die Knoten für alle Transformationen im Block anzeigt.

## Dimensionen {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Jeder grüne Knoten ist ein Dimensionsblock mit den folgenden Optionen:

* Um die Eingabefelder oder die übergeordnete Dimension des Dimensionsblocks anzuzeigen, klicken Sie mit der rechten Maustaste auf den Knoten für den Block und klicken Sie auf **[!UICONTROL Inputs]**.
* Um die Ausgabedimensionen des Dimensionsblocks anzuzeigen, klicken Sie mit der rechten Maustaste auf den Knoten für den Block und klicken Sie auf **[!UICONTROL Outputs]**.
