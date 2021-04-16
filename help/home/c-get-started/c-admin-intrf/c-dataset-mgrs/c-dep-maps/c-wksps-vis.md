---
description: Konzeptbezogene Informationen zu Arbeitsbereichen und Visualisierungen.
title: Arbeitsbereiche und Visualisierungen
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Arbeitsbereiche und Visualisierungen{#workspaces-and-visualizations}

Konzeptbezogene Informationen zu Arbeitsbereichen und Visualisierungen.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die im Profil definierten Arbeitsbereiche, Berichte, Menüoptionen und globalen Ebenen darstellen. Diese Option funktioniert nur, wenn die Anzeigeoption [!DNL Query Model] aktiviert ist.

>[!NOTE]
>
>Wenn die Anzeigeoption [!DNL Query Model] bei Auswahl der Anzeigeoption [!DNL Workspaces and Visualizations] nicht aktiviert ist, wird eine Fehlermeldung angezeigt.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Eine graue Node stellt eine Arbeitsfläche oder einen Bericht dar.
* Ein gelb-grüner Knoten stellt eine Menüoption dar.
* Eine rote Node stellt eine Arbeitsfläche, einen Bericht, eine Menüoption oder eine globale Ebene mit einer unterbrochenen oder kreisförmigen Abhängigkeit oder einem anderen Fehler dar.

>[!NOTE]
>
>Da die Abhängigkeitszuordnung für acyclische Abhängigkeiten konzipiert ist, werden Knoten, die an zirkulären Abhängigkeiten beteiligt sind, auf der Karte möglicherweise nicht richtig angezeigt. Sie können nach zirkulären Abhängigkeiten suchen, indem Sie &quot;zirkuläre Abhängigkeit&quot;in das Textfeld [!DNL Search] eingeben. Weitere Informationen zur Funktion [!DNL Search] finden Sie unter [Suchen in einer Map](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Beschreibungen anderer Nodes auf der Map finden Sie unter [Abfrage Model Components](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
