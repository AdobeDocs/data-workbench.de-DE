---
description: Innerhalb eines Arbeitsbereichs stellt eine Visualisierung einen Satz von Abfrageergebnissen dar.
title: Einfluss einer Auswahl auf andere Visualisierungen
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Einfluss einer Auswahl auf andere Visualisierungen{#understanding-how-a-selection-affects-other-visualizations}

{{eol}}

Innerhalb eines Arbeitsbereichs stellt eine Visualisierung einen Satz von Abfrageergebnissen dar.

Wenn Sie eine Auswahl treffen, filtert Data Workbench die Ergebnisse der Abfragen, mit denen die Visualisierungen im Arbeitsbereich erstellt werden. Der spezifische Filter variiert je nach Visualisierung.

Die folgenden Beispiele veranschaulichen, wie Data Workbench eine Auswahl auf drei verschiedene Visualisierungstypen anwendet. Anhand dieser Beispiele können Sie den Filtereffekt von Auswahlen auf Visualisierungen nachvollziehen. Sie helfen Ihnen auch zu verstehen, wie Sie die Ergebnisse in einer gefilterten Visualisierung interpretieren.

* [Filtern einer Visualisierung mit einer Sitzungsmetrik](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtern einer Visualisierung mit einer Besuchermetrik](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtern einer Visualisierung mit einer Metrik &quot;Besucher nach Sitzung&quot;](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtern einer Visualisierung mit einer Sitzungsmetrik {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

In diesem Beispiel wird die [!DNL /direct.asp/?ldPage=hme] URI in der Visualisierung auf der linken Seite filtert die Metrik für Sitzungen, die in der Visualisierung auf der rechten Seite angezeigt werden.

![](assets/client-vis1.png)

* **Auswirkung der Auswahl auf die Abfrage:** Data Workbench filtert die Sitzungen für den ausgewählten URI. In diesem Beispiel generiert die Abfrage den Wert für [!DNL /pops/disclosure_pop.asp] -Element wie folgt gefiltert:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung stellt die Anzahl der Sitzungen dar, die die in der Visualisierung aufgelisteten URIs enthalten, und [!DNL /direct.asp/?ldPage=hme]. Dieses Beispiel zeigt, dass es 1.113 Sitzungen gab, in denen Besucher beide anzeigten [!DNL /pops/disclosure_pop.asp] und [!DNL /direct.asp/?ldPage=hme] in derselben Sitzung.

## Filtern einer Visualisierung mit einer Besuchermetrik {#section-97d38c7f03e8457189a9c72d69514ed2}

In diesem Beispiel wird die [!DNL /direct.asp/?ldPage=home] URI in der Visualisierung auf der linken Seite filtert die Metrik für Besucher in der Visualisierung auf der rechten Seite.

![](assets/client-vis2.png)

* **Auswirkung der Auswahl auf die Abfrage:** Data Workbench filtert die Besucher für den ausgewählten URI. In diesem Beispiel generiert die Abfrage den Wert für [!DNL /pops/disclosure_pop.asp] URI wird wie folgt gefiltert:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung zeigt die Besucher an, die die in der Visualisierung aufgelisteten URIs angezeigt haben, und [!DNL /direct.asp/?ldPage=hme] (obwohl nicht unbedingt während derselben Sitzung). Das obige Beispiel zeigt, dass 2.041 Besucher beide [!DNL /pops/disclosure_pop.asp] und [!DNL /direct.asp/?ldPage=hme].

## Filtern einer Visualisierung mit einer Metrik &quot;Besucher nach Sitzung&quot; {#section-f746182311d648dcb98716b0fe846e25}

In diesem Beispiel wird die [!DNL /direct.asp/?ldPage=hme] Der URI in der Visualisierung auf der linken Seite filtert die Metrik in der Visualisierung auf der rechten Seite nach Besuchern.

![](assets/client-vis3.png)

* **Auswirkung der Auswahl auf die Abfrage:** Data Workbench filtert die Besucher nach Sitzung für den ausgewählten URI. Beispielsweise die Abfrage, die den Wert für [!DNL /pops/disclosure_pop.asp] URI wird wie folgt gefiltert:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung zeigt die Besucher an, die beide in der Visualisierung aufgelisteten URIs angezeigt haben und [!DNL /direct.asp/?ldPage=hme] während derselben Sitzung. Dieses Beispiel zeigt, dass 1.069 Besucher beide [!DNL /pops/disclosure_pop.asp] und [!DNL /direct.asp/?ldPage=hme] während einer einzelnen Sitzung.
