---
description: Wenn Sie Datensatzkomponenten auf einer Abhängigkeitszuordnung anzeigen, haben Sie die Möglichkeit, die Anzeigeoption "Dateiblöcke einschließen"zu aktivieren.
title: Dateiblöcke
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Dateiblöcke{#file-blocks}

Wenn Sie Datensatzkomponenten auf einer Abhängigkeitszuordnung anzeigen, haben Sie die Möglichkeit, die Anzeigeoption &quot;Dateiblöcke einschließen&quot;zu aktivieren.

Wenn diese Option aktiviert ist, zeigt die Zuordnung einen einzelnen blauen Knoten für alle in einer Datensatzkonfigurationsdatei definierten Transformationen und einen einzigen grünen Knoten für alle in einer Datensatzkonfigurationsdatei definierten erweiterten Dimensionen an. Wenn beispielsweise eine [!DNL log processing dataset include]-Datei die Definitionen von drei Transformationen enthält, zeigt die Zuordnung einen blauen Knoten an, der die drei Transformationen darstellt. Wenn eine [!DNL transformation dataset include]-Datei die Definitionen von zwei erweiterten Dimensionen enthält, zeigt die Map einen grünen Knoten an, der die beiden erweiterten Dimensionen darstellt.

## Transformationsblöcke {#section-c442730394264a0b850792a32eaaa2da}

Jeder blaue Knoten ist ein Transformationsblock und verfügt über die folgenden Optionen:

* Um die Eingabefelder des Transformationsblocks Ansicht, klicken Sie mit der rechten Maustaste auf die Node des Blocks und klicken Sie auf **[!UICONTROL Inputs]**.
* Um die Ausgabefelder des Transformationsblocks Ansicht, klicken Sie mit der rechten Maustaste auf die Node des Blocks und klicken Sie auf **[!UICONTROL Outputs]**.
* Um eine der Transformationen im Block zu bearbeiten, klicken Sie mit der rechten Maustaste auf den Knoten für den Block und klicken Sie auf **[!UICONTROL Edit Configuration]**. Der angezeigte Callout enthält die gesamte Konfigurationsdatei, in der alle Transformationen definiert sind. Anschließend können Sie die Parameter nach Bedarf bearbeiten. Weitere Informationen zu diesen Parametern finden Sie im *Handbuch zur Konfiguration von Datasets*.

* Um alle Transformationen im Block anzuzeigen, klicken Sie mit der rechten Maustaste auf den Knoten für den Transformationsblock und klicken Sie auf **[!UICONTROL Show Details]**. Die angezeigte Callout-Komponente enthält eine weitere Abhängigkeitszuordnung mit Knoten für alle Transformationen im Block.

## Dimension Blöcke {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Jeder grüne Knoten ist ein Dimensionsblock und verfügt über die folgenden Optionen:

* Um die Eingabefelder oder die übergeordnete Dimension des Dimensionsblocks Ansicht, klicken Sie mit der rechten Maustaste auf die Node für den Block und klicken Sie auf **[!UICONTROL Inputs]**.
* Um die Ausgabedimensionen des Dimensionsblocks Ansicht, klicken Sie mit der rechten Maustaste auf die Node des Blocks und klicken Sie auf **[!UICONTROL Outputs]**.
