---
description: Abhängigkeitskarten ermöglichen Ihnen die Visualisierung und Verwaltung der Konfiguration der Komponenten Ihres Profils.
title: Abhängigkeitskarten
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Abhängigkeitskarten{#dependency-maps}

Abhängigkeitskarten ermöglichen Ihnen die Visualisierung und Verwaltung der Konfiguration der Komponenten Ihres Profils.

* **Datensatzkomponenten:** Protokollquellen, Filter, Felder, Konvertierungen und erweiterte Dimensionen, die in den  [!DNL Log Processing.cfg],  [!DNL Transformation.cfg]und  [!DNL dataset include] Dateien Ihres Datensatzes definiert sind.

* **Abfrage-Modellkomponenten:** Metriken, Dimensionen und Filter, die in den Ordnern &quot;Dimensionen&quot;, &quot;Metriken&quot;und &quot;Filter&quot;definiert sind.
* **Arbeitsbereiche und Visualisierungen:** Arbeitsbereiche, Berichte, Menüoptionen und globale Ebenen.

Weitere Informationen zum Arbeiten mit Abfrage-Modellkomponenten, Arbeitsbereichen und Visualisierungen in Abhängigkeitskarten finden Sie im *Data Workbench Benutzerhandbuch*.

Profil-Komponenten werden durch farbige Punkte (Nodes) in der Map dargestellt. Die Linien, die die Knoten verbinden, stellen Abhängigkeiten dar, d.h. wie die Komponenten miteinander verbunden sind. Eine Linie zwischen zwei Knoten bedeutet, dass eine Ausgabe des Knotens auf der linken Seite eine Eingabe des Knotens auf der rechten Seite ist, das heißt, der rechte Knoten hängt vom linken Knoten ab.

## Anzeigen von Datenaset-Komponenten {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Klicken Sie mit der rechten Maustaste in die Abhängigkeitszuordnung und klicken Sie auf **[!UICONTROL Display]**.
1. Auswählen **[!UICONTROL Dataset]**. Ein X wird links von [!DNL Dataset] angezeigt.

Weitere Informationen zu den anderen Anzeigeoptionen finden Sie im *Data Workbench Benutzerhandbuch*.

Die folgende Abbildung zeigt eine Abhängigkeitszuordnung, deren Knoten die Protokollquellen, Felder, Transformationen und erweiterten Dimensionen eines Datensatzes darstellen.

![](assets/vis_DependencyMap.png)

* Ein gelb-grüner Knoten stellt eine oder mehrere Protokollquellen oder einen Filter dar, die im Datensatz definiert sind. Ein Knoten für eine Protokollquelle erscheint immer am weitesten links in der Map.
* Eine graue Node stellt ein Feld dar, das im Parameter &quot;Felder&quot;in einer [!DNL Log Processing.cfg]- oder [!DNL Log Processing Include]-Datei aufgeführt ist.

* Eine blaue Node stellt eine Transformation dar.
* Ein grüner Knoten stellt eine erweiterte Dimension dar.

>[!NOTE]
>
>Wenn Ihr Datensatz über eine einzige Protokollquelle verfügt, zeigt die Zuordnung die Protokollquelle an: *Name der Protokollquelle*. Wenn Ihr Datensatz über mehrere Protokollquellen verfügt, zeigt die Zuordnung *number* Protokollquellen an, wobei Nummer die Anzahl der Protokollquellen ist. Wenn Ihr Datensatz beispielsweise drei Protokollquellen enthält, zeigt Ihre Zuordnung 3 Protokollquellen an.

Wenn Sie nicht alle Knoten auf der Karte sehen können, können Sie die Karte verschieben, vergrößern oder verkleinern, um die gesamte Karte anzuzeigen oder sich auf einen bestimmten Abschnitt zu konzentrieren. Weitere Informationen zum Zoomen finden Sie im Kapitel Arbeiten mit Visualisierungen im *Data Workbench Benutzerhandbuch*.

Wenn Sie auf eine Node klicken, werden alle Nodes, die von dieser Node abhängen, sowie alle Nodes, von denen diese Node abhängig ist, hervorgehoben und ihre Namen werden angezeigt.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Ein hervorgehobener Pfad in einer Abhängigkeitszuordnung stellt keine Auswahl dar.

Wenn Sie mit der rechten Maustaste auf eine Node klicken, können Sie Informationen zu den einzelnen Komponenten auf der Map anzeigen und Menüoptionen auswählen, mit denen Sie detailliertere Ansichten zur Komponente oder zur Bearbeitung der Komponente vornehmen können. Darüber hinaus können Sie Textsuchen durchführen und Leistungsinformationen für Transformationen und erweiterte Dimensionen anzeigen.

Weitere Informationen zu diesen Funktionen für Abhängigkeitskarten finden Sie im Kapitel &quot;Administrative Schnittstellen&quot;des *Data Workbench Benutzerhandbuchs*.
