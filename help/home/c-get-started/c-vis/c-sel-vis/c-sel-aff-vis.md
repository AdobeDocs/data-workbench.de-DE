---
description: Innerhalb eines Arbeitsbereichs stellt eine Visualisierung eine Reihe von Abfragen dar.
title: Einfluss einer Auswahl auf andere Visualisierungen
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Einfluss einer Auswahl auf andere Visualisierungen{#understanding-how-a-selection-affects-other-visualizations}

Innerhalb eines Arbeitsbereichs stellt eine Visualisierung eine Reihe von Abfragen dar.

Wenn Sie eine Auswahl treffen, werden bei der Data Workbench die Ergebnisse der Abfragen Filter, mit denen die Visualisierungen im Arbeitsbereich erstellt werden. Der spezifische Filter variiert je nach Visualisierung.

Die folgenden Beispiele zeigen, wie Data Workbench eine Auswahl auf drei verschiedene Visualisierungstypen anwendet. Die Überprüfung dieser Beispiele hilft Ihnen, den Filtereffekt zu verstehen, den Auswahlen auf Visualisierungen haben. Sie helfen Ihnen auch, die Ergebnisse zu interpretieren, die Sie in einer gefilterten Visualisierung sehen.

* [Filtern einer Visualisierung mit einer Sitzungsmetrik](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtern einer Visualisierung mit einer Metrik für Besucher](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtern einer Visualisierung mit einer Metrik &quot;Besucher für Sitzung&quot;](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtern einer Visualisierung mit einer Sitzungsmetrik {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

In diesem Beispiel filtert der URI [!DNL /direct.asp/?ldPage=hme] in der Visualisierung auf der linken Seite die Metrik für Sitzungen, die in der Visualisierung auf der rechten Seite angezeigt werden.

![](assets/client-vis1.png)

* **Der Effekt &quot;Auswahl&quot;auf die Abfrage:** Data Workbench Filter die Sitzungen für den ausgewählten URI. In diesem Beispiel wird die Abfrage, die den Wert für das [!DNL /pops/disclosure_pop.asp]-Element generiert, wie folgt gefiltert:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung stellt die Anzahl der Sitzungen dar, die die in der Visualisierung und  [!DNL /direct.asp/?ldPage=hme]. Dieses Beispiel zeigt, dass es 1.113 Sitzungen gab, bei denen Besucher sowohl die Seite [!DNL /pops/disclosure_pop.asp] als auch die Seite [!DNL /direct.asp/?ldPage=hme] in derselben Sitzung anzeigten.

## Filtern einer Visualisierung mit einer Metrik für Besucher {#section-97d38c7f03e8457189a9c72d69514ed2}

In diesem Beispiel filtert der URI [!DNL /direct.asp/?ldPage=home] in der Visualisierung auf der linken Seite die Metrik für Besucher in der Visualisierung auf der rechten Seite.

![](assets/client-vis2.png)

* **Der Effekt der Auswahl auf die Abfrage:** Data Workbench Filter die Besucher für den ausgewählten URI. In diesem Beispiel wird die Abfrage, die den Wert für den URI [!DNL /pops/disclosure_pop.asp] generiert, wie folgt gefiltert:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Visualisierung interpretieren:** Die gefilterte Visualisierung zeigt die Besucher an, die die in der Visualisierung aufgelisteten URIs angezeigt haben  [!DNL /direct.asp/?ldPage=hme] (allerdings nicht unbedingt während derselben Sitzung). Das obige Beispiel zeigt, dass 2.041 Besucher sowohl [!DNL /pops/disclosure_pop.asp] als auch [!DNL /direct.asp/?ldPage=hme] angezeigt haben.

## Filtern einer Visualisierung mit einer Metrik für Besucher nach Sitzung {#section-f746182311d648dcb98716b0fe846e25}

In diesem Beispiel filtert der URI [!DNL /direct.asp/?ldPage=hme] in der Visualisierung auf der linken Seite die Metrik für jede Besucher-für-Sitzung in der Visualisierung auf der rechten Seite.

![](assets/client-vis3.png)

* **Der Effekt der Auswahl auf die Abfrage:** Data Workbench Filter die Besucher nach Sitzung für den ausgewählten URI. Beispielsweise wird die Abfrage, die den Wert für den URI [!DNL /pops/disclosure_pop.asp] generiert, wie folgt gefiltert:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Visualisierung interpretieren:** Die gefilterte Visualisierung zeigt die Besucher an, die beide in der Visualisierung und  [!DNL /direct.asp/?ldPage=hme] während derselben Sitzung aufgelisteten URIs angezeigt haben. Dieses Beispiel zeigt, dass 1.069 Besucher während einer Sitzung sowohl [!DNL /pops/disclosure_pop.asp] als auch [!DNL /direct.asp/?ldPage=hme] gesehen haben.
