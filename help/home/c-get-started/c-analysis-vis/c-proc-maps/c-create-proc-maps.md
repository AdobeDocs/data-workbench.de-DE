---
description: Sie können 2D- und 3D-Prozesszuordnungen erstellen, indem Sie Elemente aus Balkendiagrammen, Tabellen und Hierarchie-Ansichten auf eine leere Map ziehen und dort ablegen.
title: Erstellen von Prozesskarten
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
exl-id: 2e417a8e-5b1c-4dce-9e4e-ac7ed044564c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Erstellen von Prozesskarten{#create-a-process-map}

Sie können 2D- und 3D-Prozesszuordnungen erstellen, indem Sie Elemente aus Balkendiagrammen, Tabellen und Hierarchie-Ansichten auf eine leere Map ziehen und dort ablegen.

Die Elemente, die Sie hinzufügen können, müssen Elemente der Basisdimension der Prozesszuordnung sein. Sie können Knoten auch von einer Prozesszuordnung zu einer anderen ziehen und ablegen, solange die Maps dieselbe Basisdimension verwenden. Darüber hinaus kann die gesamte Map gezoomt oder verschoben werden, um sich auf einen bestimmten Knoten zu konzentrieren, oder sie kann in andere Visualisierungstypen geändert werden. Siehe [Zoomen in Visualisierungen](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**So fügen Sie einer Prozesszuordnung Elemente mithilfe eines Tabellen- oder Balkendiagramms hinzu**

* Drücken Sie bei jedem Tabellen- oder Balkendiagramm mit derselben Basisdimension wie die Prozesszuordnung Strg+Alt, während Sie auf einzelne Elemente klicken und sie in die Prozesszuordnung ziehen. Ihr Mauszeiger zeigt das Wort &quot;Nein&quot;an, bis die Maus die Prozesskarte erreicht.

   >[!NOTE]
   >
   >Die Elemente, die Sie hinzufügen können, müssen Elemente der Basisdimension der Prozesszuordnung sein.

   ![](assets/vis_2DProcessMap_addPages.png)

**So fügen Sie einer Zuordnung Elemente mithilfe einer Hierarchie-Ansicht hinzu**

>[!NOTE]
>
>Adobe empfiehlt, Knoten der höchsten Ebene der Hierarchie, die Sie analysieren, hinzuzufügen.

1. Klicken Sie in einer Tabelle oder einem Balkendiagramm mit derselben Basisdimension wie die Prozesskarte mit der rechten Maustaste auf ein Element oder die Beschriftung der Basisdimension und klicken Sie auf **[!UICONTROL Hierarchy View]**.
1. Drücken Sie Strg+Alt, während Sie auf Elemente klicken und sie in die Prozesszuordnung ziehen. Ihr Mauszeiger zeigt das Wort &quot;Nein&quot; an, bis die Maus auf die Karte gelangt.

   >[!NOTE]
   >
   >Die Elemente, die Sie hinzufügen können, müssen Elemente der Basisdimension der Prozesszuordnung sein.

   Wenn Sie ein einzelnes Element auf eine Prozesszuordnung ziehen, wird nur für dieses Element ein Zuordnungsknoten erstellt. Wenn Sie jedoch mehrere Elemente (eine Gruppe) oder einen Ordner mit mehreren Elementen auswählen, wird durch Ziehen aus der Hierarchie ein einzelner Knoten für diese Gruppe oder diesen Ordner erstellt. Wenn Sie beispielsweise mit Website-Daten arbeiten, wird durch Ziehen eines Ordners mit dem Namen [!DNL site.com/cgi-bin] auf eine Map ein Knoten mit dem Namen [!DNL site.com/cgi-bin/*] erstellt, der alle Seiten und Ordner darstellt, die dem Ordner untergeordnet sind.

Weitere Informationen zu Ansichten der Seitenhierarchie finden Sie unter [Anwenden von HierarchieAnsichten](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**So fügen Sie Knoten einer Prozesszuordnung aus einer anderen Prozesszuordnung hinzu**

>[!NOTE]
>
>Die Prozesszuordnungen müssen die gleiche Basisdimension haben.

* Kopieren Sie eine Node aus der ersten in die zweite Prozesszuordnung mit den folgenden Methoden:

   * Um einzelne Knoten zu kopieren, klicken Sie auf die einzelnen Knoten und ziehen Sie sie in die zweite Prozesszuordnung.
   * Um mehrere Knoten zu kopieren, klicken Sie bei gedrückter Strg-Taste und ziehen Sie, um ein Feld um die zu kopierenden Nodes zu erstellen. Klicken Sie anschließend auf die markierten Nodes und ziehen Sie sie in die zweite Prozesszuordnung. Alle hervorgehobenen Knoten werden in die zweite Prozesszuordnung kopiert.
