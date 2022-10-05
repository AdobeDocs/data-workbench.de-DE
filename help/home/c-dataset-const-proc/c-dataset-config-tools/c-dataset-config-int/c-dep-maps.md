---
description: Mit Abhängigkeitskarten können Sie die Konfiguration der Komponenten Ihres Profils visualisieren und verwalten.
title: Abhängigkeitskarten
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Abhängigkeitskarten{#dependency-maps}

{{eol}}

Mit Abhängigkeitskarten können Sie die Konfiguration der Komponenten Ihres Profils visualisieren und verwalten.

* **Datensatzkomponenten:** Protokollquellen, Filter, Felder, Umwandlungen und erweiterte Dimensionen, die in den [!DNL Log Processing.cfg], [!DNL Transformation.cfg]und [!DNL dataset include] Dateien.

* **Komponenten des Abfragemodells:** Metriken, Dimensionen und Filter, die in den Ordnern Dimensionen, Metriken und Filter definiert sind.
* **Arbeitsbereiche und Visualisierungen:** Arbeitsbereiche, Berichte, Menüoptionen und globale Ebenen.

Weitere Informationen zum Arbeiten mit Abfragemodellkomponenten, Arbeitsbereichen und Visualisierungen in Abhängigkeitskarten finden Sie in der *Data Workbench-Benutzerhandbuch*.

Profilkomponenten werden durch farbige Punkte (Knoten) in der Zuordnung dargestellt. Die Linien, die die Knoten verbinden, zeigen Abhängigkeiten an, d. h. wie die Komponenten miteinander verbunden sind. Eine Linie zwischen zwei Knoten bedeutet, dass eine Ausgabe des Knotens auf der linken Seite eine Eingabe des Knotens auf der rechten Seite ist, d. h. der rechte Knoten hängt vom linken Knoten ab.

## Anzeigen von Datensatzkomponenten {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Klicken Sie mit der rechten Maustaste in die Abhängigkeitskarte und klicken Sie auf **[!UICONTROL Display]**.
1. Auswählen **[!UICONTROL Dataset]**. Ein X wird links neben [!DNL Dataset].

Weitere Informationen zu den anderen Anzeigeoptionen finden Sie unter *Data Workbench-Benutzerhandbuch*.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Protokollquellen, Felder, Umwandlungen und erweiterten Dimensionen eines Datensatzes darstellen.

![](assets/vis_DependencyMap.png)

* Ein gelb-grüner Knoten stellt eine oder mehrere Protokollquellen oder einen im Datensatz definierten Filter dar. Ein Knoten für eine Protokollquelle wird immer am weitesten links in der Karte angezeigt.
* Ein grauer Knoten stellt ein Feld dar, das im Parameter Felder in einer [!DNL Log Processing.cfg] oder [!DNL Log Processing Include]-Datei.

* Ein blauer Knoten stellt eine Umwandlung dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar.

>[!NOTE]
>
>Wenn Ihr Datensatz über eine einzelne Protokollquelle verfügt, zeigt die Zuordnung die Protokollquelle an: *Protokollquellenname*. Wenn Ihr Datensatz mehrere Protokollquellen enthält, wird die Zuordnung angezeigt *number* Protokollquellen, wobei number die Anzahl der Protokollquellen ist. Wenn Ihr Datensatz beispielsweise drei Protokollquellen enthält, zeigt Ihre Zuordnung drei Protokollquellen an.

Wenn Sie nicht alle Knoten auf der Karte sehen können, können Sie die Karte verschieben, vergrößern oder verkleinern, um die gesamte Karte anzuzeigen oder sich auf einen bestimmten Bereich zu konzentrieren. Weitere Informationen zum Zoomen finden Sie im Kapitel Arbeiten mit Visualisierungen im Abschnitt *Data Workbench-Benutzerhandbuch*.

Wenn Sie auf einen Knoten klicken, werden alle Knoten, die von diesem Knoten abhängen, und alle Knoten, von denen dieser Knoten abhängt, hervorgehoben und ihre Namen angezeigt.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Ein hervorgehobener Pfad in einer Abhängigkeitszuordnung stellt keine Auswahl dar.

Wenn Sie mit der rechten Maustaste auf einen Knoten klicken, können Sie auf der Karte angezeigte Informationen zu den einzelnen Komponenten anzeigen und Menüoptionen auswählen, mit denen Sie weitere Details zur Komponente anzeigen oder die Komponente bearbeiten können. Darüber hinaus können Sie Textsuchen durchführen und Leistungsinformationen für Umwandlungen und erweiterte Dimensionen anzeigen.

Weitere Informationen zu diesen Funktionen für Abhängigkeitskarten finden Sie im Kapitel Verwaltungsschnittstellen des *Data Workbench-Benutzerhandbuch*.
