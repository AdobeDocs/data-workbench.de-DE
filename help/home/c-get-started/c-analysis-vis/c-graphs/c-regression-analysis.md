---
description: Das Balkendiagramm in der Data Workbench umfasst jetzt einen Regressionsvergleich für mehrere Metriken über mehrere Diagramme hinweg.
title: Diagramm zur Regressionsanalyse
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
exl-id: bfc76c4a-edd5-41fe-b875-c199ea3beab5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---

# Diagramm zur Regressionsanalyse{#regression-analysis-graph}

{{eol}}

Das Balkendiagramm in der Data Workbench umfasst jetzt einen Regressionsvergleich für mehrere Metriken über mehrere Diagramme hinweg.

[Balkendiagramme](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) in der Data Workbench können Sie Metriken in einem Diagramm zu Metriken in einem anderen Diagramm rückgängig machen. Wenn Sie mehrere Diagramme haben, können Sie eine Metrik (als unabhängige Variable) mit einem Diagramm vergleichen, das andere Metriken auswertet (als abhängige Variablen). Auf diese Weise können Sie die Stärke der Beziehung zwischen einer abhängigen Variablen (der zuerst eingerichteten Metrik) und einer Reihe anderer sich ändernder Metriken (Regressionen mit der festgelegten abhängigen Metrik) bestimmen.

Die Regressionsanalyse für eine Diagrammvisualisierung ermöglicht es Analysten, &quot;Was-wenn&quot;-Szenarien auszuführen. Wenn beispielsweise die Besuche auf dieses Niveau steigen, welche Auswirkungen hat dieser Anstieg auf den Umsatz?

**Einrichten einer Regressionsanalyse**

1. Wählen Sie ein Diagramm als abhängige Metrik für einen Regressionsvergleich aus.

   Klicken Sie mit der rechten Maustaste auf das Diagramm und wählen Sie **Als Basismetrik für Regression festlegen**.

   ![](assets/c_graph_regression_1.png)

1. Legen Sie andere Metrikdiagramme als unabhängige Variablen fest.

   Klicken Sie mit der rechten Maustaste auf eine Metrik und wählen Sie **[!UICONTROL Regress with `<base metric name>`]** für andere Metriken.

   ![](assets/c_graph_regression.png)

1. Zeigen Sie die Regression an, indem Sie mit der rechten Maustaste auf das Diagramm klicken, um den Balken nach oben und unten zu verschieben.

   Wenn Sie mit der rechten Maustaste auf das Diagramm für einen bestimmten Wert klicken, können Sie dann die Regressionsverhältnisse für jede Metrik basierend auf Aufwärts- oder Abwärtswerten sehen.

   ![](assets/c_graph_regression_2.png)

   Wenn beispielsweise meine Seitenansichten auf 86.041 reduziert werden, haben die anderen Metriken die folgenden Werte: Besuche bei 12.183 und Besucher nach Besuch bei 12.028.

   ![](assets/c_graph_regression_3.png)

   Wenn der Wert &quot;Besucher nach Besuchen&quot;auf 26.141 erhöht wird, sind die anderen Metriken &quot;Besuche bei 26.560&quot;und &quot;Seitenansichten&quot;auf 189.091.
