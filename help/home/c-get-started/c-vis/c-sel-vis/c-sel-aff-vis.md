---
description: Innerhalb eines Arbeitsbereichs stellt eine Visualisierung einen Satz von Abfrageergebnissen dar.
solution: Analytics
title: Einfluss einer Auswahl auf andere Visualisierungen
topic: Data workbench
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Einfluss einer Auswahl auf andere Visualisierungen{#understanding-how-a-selection-affects-other-visualizations}

Innerhalb eines Arbeitsbereichs stellt eine Visualisierung einen Satz von Abfrageergebnissen dar.

Wenn Sie eine Auswahl treffen, filtert Data Workbench die Ergebnisse der Abfragen, die zur Erstellung der Visualisierungen im Arbeitsbereich verwendet werden. Der spezifische Filter variiert je nach Visualisierung.

Die folgenden Beispiele zeigen, wie Data Workbench eine Auswahl auf drei verschiedene Arten von Visualisierungen anwendet. Die Überprüfung dieser Beispiele hilft Ihnen, den Filtereffekt zu verstehen, den Auswahlen auf Visualisierungen haben. Sie helfen Ihnen auch, die Ergebnisse zu interpretieren, die Sie in einer gefilterten Visualisierung sehen.

* [Filtern einer Visualisierung mit einer Sitzungsmetrik](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtern einer Visualisierung mit einer Besuchermetrik](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtern einer Visualisierung mit einer Metrik &quot;Besucher nach Sitzung&quot;](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtern einer Visualisierung mit einer Sitzungsmetrik {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

In diesem Beispiel filtert der [!DNL /direct.asp/?ldPage=hme] URI in der Visualisierung auf der linken Seite die Metrik für Sitzungen, die in der Visualisierung auf der rechten Seite angezeigt werden.

![](assets/client-vis1.png)

* **Auswirkung der Auswahl auf die Abfrage:** Data Workbench filtert die Sitzungen für den ausgewählten URI. In diesem Beispiel wird die Abfrage, die den Wert für das [!DNL /pops/disclosure_pop.asp] Element generiert, wie folgt gefiltert:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung stellt die Anzahl der Sitzungen dar, die die in der Visualisierung und in der [!DNL /direct.asp/?ldPage=hme]Darstellung aufgelisteten URIs enthalten. Dieses Beispiel zeigt, dass es 1.113 Sitzungen gab, in denen Besucher sowohl die [!DNL /pops/disclosure_pop.asp] Seite als auch [!DNL /direct.asp/?ldPage=hme] die Sitzung aufriefen.

## Filtern einer Visualisierung mit einer Besuchermetrik {#section-97d38c7f03e8457189a9c72d69514ed2}

In diesem Beispiel filtert der [!DNL /direct.asp/?ldPage=home] URI in der Visualisierung auf der linken Seite die Metrik für Besucher in der Visualisierung auf der rechten Seite.

![](assets/client-vis2.png)

* **Auswirkung der Auswahl auf die Abfrage:** Data Workbench filtert die Besucher für den ausgewählten URI. In diesem Beispiel wird die Abfrage, die den Wert für den [!DNL /pops/disclosure_pop.asp] URI generiert, wie folgt gefiltert:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung zeigt die Besucher an, die die in der Visualisierung aufgelisteten URIs angezeigt haben [!DNL /direct.asp/?ldPage=hme] (allerdings nicht unbedingt während derselben Sitzung). Das obige Beispiel zeigt, dass 2.041 Besucher sowohl [!DNL /pops/disclosure_pop.asp] als auch [!DNL /direct.asp/?ldPage=hme]angezeigt haben.

## Filtern einer Visualisierung mit einer Metrik &quot;Besucher nach Sitzung&quot; {#section-f746182311d648dcb98716b0fe846e25}

In diesem Beispiel filtert der [!DNL /direct.asp/?ldPage=hme] URI in der Visualisierung auf der linken Seite die Metrik für jede einzelne Sitzung in der Visualisierung auf der rechten Seite.

![](assets/client-vis3.png)

* **Auswirkung der Auswahl auf die Abfrage:** Data Workbench filtert die Besucher nach Sitzung für den ausgewählten URI. Beispielsweise wird die Abfrage, die den Wert für den [!DNL /pops/disclosure_pop.asp] URI generiert, wie folgt gefiltert:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interpretieren der Visualisierung:** Die gefilterte Visualisierung zeigt die Besucher an, die beide in der Visualisierung und [!DNL /direct.asp/?ldPage=hme] während derselben Sitzung aufgelisteten URIs angezeigt haben. Dieses Beispiel zeigt, dass 1.069 Besucher sowohl während [!DNL /pops/disclosure_pop.asp] als auch während einer einzelnen Sitzung [!DNL /direct.asp/?ldPage=hme] gesehen haben.

