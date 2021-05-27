---
description: Mit Abhängigkeitskarten können Sie die Konfiguration der Komponenten Ihres Profils visualisieren und verwalten.
title: Abhängigkeitskarten
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Abhängigkeitskarten{#dependency-maps}

Mit Abhängigkeitskarten können Sie die Konfiguration der Komponenten Ihres Profils visualisieren und verwalten.

* **Datensatzkomponenten:** Protokollquellen, Filter, Felder, Umwandlungen und erweiterte Dimensionen, die in den  [!DNL Log Processing.cfg],  [!DNL Transformation.cfg] und  [!DNL dataset include] Dateien Ihres Datensatzes definiert sind.

* **Komponenten des Abfragemodells:** Metriken, Dimensionen und Filter, die in den Ordnern &quot;Dimensionen&quot;, &quot;Metriken&quot;und &quot;Filter&quot;definiert sind.
* **Arbeitsbereiche und Visualisierungen:** Arbeitsbereiche, Berichte, Menüoptionen und globale Ebenen.

Weitere Informationen zum Arbeiten mit Abfragemodellkomponenten, Arbeitsbereichen und Visualisierungen in Abhängigkeitskarten finden Sie im *Data Workbench-Benutzerhandbuch*.

Profilkomponenten werden durch farbige Punkte (Knoten) in der Zuordnung dargestellt. Die Linien, die die Knoten verbinden, zeigen Abhängigkeiten an, d. h. wie die Komponenten miteinander verbunden sind. Eine Linie zwischen zwei Knoten bedeutet, dass eine Ausgabe des Knotens auf der linken Seite eine Eingabe des Knotens auf der rechten Seite ist, d. h. der rechte Knoten hängt vom linken Knoten ab.

## Anzeigen von Datensatzkomponenten {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Klicken Sie mit der rechten Maustaste in die Abhängigkeitskarte und klicken Sie auf **[!UICONTROL Display]**.
1. Auswählen **[!UICONTROL Dataset]**. Links von [!DNL Dataset] wird ein X angezeigt.

Weitere Informationen zu den anderen Anzeigeoptionen finden Sie im *Data Workbench-Benutzerhandbuch*.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Protokollquellen, Felder, Umwandlungen und erweiterten Dimensionen eines Datensatzes darstellen.

![](assets/vis_DependencyMap.png)

* Ein gelb-grüner Knoten stellt eine oder mehrere Protokollquellen oder einen im Datensatz definierten Filter dar. Ein Knoten für eine Protokollquelle wird immer am weitesten links in der Karte angezeigt.
* Ein grauer Knoten stellt ein Feld dar, das im Parameter Felder in einer Datei [!DNL Log Processing.cfg] oder [!DNL Log Processing Include]aufgeführt ist.

* Ein blauer Knoten stellt eine Umwandlung dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar.

>[!NOTE]
>
>Wenn Ihr Datensatz über eine einzelne Protokollquelle verfügt, zeigt die Zuordnung die Protokollquelle an: *log source name*. Wenn Ihr Datensatz mehrere Protokollquellen enthält, zeigt die Zuordnung *number* Protokollquellen an, wobei number die Anzahl der Protokollquellen ist. Wenn Ihr Datensatz beispielsweise drei Protokollquellen enthält, zeigt Ihre Zuordnung drei Protokollquellen an.

Wenn Sie nicht alle Knoten auf der Karte sehen können, können Sie die Karte verschieben, vergrößern oder verkleinern, um die gesamte Karte anzuzeigen oder sich auf einen bestimmten Bereich zu konzentrieren. Weitere Informationen zum Zoomen finden Sie im Kapitel Arbeiten mit Visualisierungen des *Data Workbench-Benutzerhandbuchs*.

Wenn Sie auf einen Knoten klicken, werden alle Knoten, die von diesem Knoten abhängen, und alle Knoten, von denen dieser Knoten abhängt, hervorgehoben und ihre Namen angezeigt.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Ein hervorgehobener Pfad in einer Abhängigkeitszuordnung stellt keine Auswahl dar.

Wenn Sie mit der rechten Maustaste auf einen Knoten klicken, können Sie auf der Karte angezeigte Informationen zu den einzelnen Komponenten anzeigen und Menüoptionen auswählen, mit denen Sie weitere Details zur Komponente anzeigen oder die Komponente bearbeiten können. Darüber hinaus können Sie Textsuchen durchführen und Leistungsinformationen für Umwandlungen und erweiterte Dimensionen anzeigen.

Weitere Informationen zu diesen Funktionen für Abhängigkeitskarten finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.
