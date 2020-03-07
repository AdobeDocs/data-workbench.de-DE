---
description: Sie können 2D- und 3D-Prozesszuordnungen erstellen, indem Sie Elemente aus Balkendiagrammen, Tabellen und Hierarchieansichten auf eine leere Map ziehen und dort ablegen.
solution: Analytics
title: Erstellen einer Prozesszuordnung
topic: Data workbench
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen einer Prozesszuordnung{#create-a-process-map}

Sie können 2D- und 3D-Prozesszuordnungen erstellen, indem Sie Elemente aus Balkendiagrammen, Tabellen und Hierarchieansichten auf eine leere Map ziehen und dort ablegen.

Die Elemente, die Sie hinzufügen können, müssen Elemente der Basisdimension der Prozesszuordnung sein. Sie können Knoten auch von einer Prozesszuordnung zu einer anderen ziehen und ablegen, solange die Maps dieselbe Basisdimension verwenden. Darüber hinaus kann die gesamte Map gezoomt oder verschoben werden, um sich auf einen bestimmten Knoten zu konzentrieren, oder sie kann in andere Visualisierungstypen geändert werden. Siehe [Zoomen in Visualisierungen](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**So fügen Sie einer Prozesszuordnung Elemente mithilfe eines Tabellen- oder Balkendiagramms hinzu**

* Drücken Sie bei jedem Tabellen- oder Balkendiagramm mit derselben Basisdimension wie die Prozesszuordnung Strg+Alt, während Sie auf einzelne Elemente klicken und sie in die Prozesszuordnung ziehen. Ihr Mauszeiger zeigt das Wort &quot;Nein&quot;an, bis die Maus die Prozesskarte erreicht.

   >[!NOTE]
   >
   >Die Elemente, die Sie hinzufügen können, müssen Elemente der Basisdimension der Prozesszuordnung sein.

   ![](assets/vis_2DProcessMap_addPages.png)

**So fügen Sie einer Prozesszuordnung Elemente mithilfe einer Hierarchieansicht hinzu**

>[!NOTE]
>
>Adobe empfiehlt, Knoten der höchsten Ebene der Hierarchie, die Sie analysieren, hinzuzufügen.

1. Klicken Sie in einer Tabelle oder einem Balkendiagramm mit derselben Basisdimension wie die Prozesszuordnung mit der rechten Maustaste auf ein Element oder die Beschriftung der Basisdimension und klicken Sie auf **[!UICONTROL Hierarchy View]**.
1. Drücken Sie Strg+Alt, während Sie auf Elemente klicken und sie in die Prozesszuordnung ziehen. Ihr Mauszeiger zeigt das Wort &quot;Nein&quot; an, bis die Maus die Karte erreicht.

   >[!NOTE]
   >
   >Die Elemente, die Sie hinzufügen können, müssen Elemente der Basisdimension der Prozesszuordnung sein.

   Wenn Sie ein einzelnes Element auf eine Prozesszuordnung ziehen, wird nur für dieses Element ein Zuordnungsknoten erstellt. Wenn Sie jedoch mehrere Elemente (eine Gruppe) oder einen Ordner mit mehreren Elementen auswählen, wird durch Ziehen aus der Hierarchie ein einzelner Knoten für diese Gruppe oder diesen Ordner erstellt. Wenn Sie z. B. mit Website-Daten arbeiten, wird durch Ziehen eines Ordners mit dem Namen [!DNL site.com/cgi-bin] &quot;map&quot;ein Knoten mit dem Namen &quot; [!DNL site.com/cgi-bin/*]Dies stellt alle Seiten und Ordner dar, die dem Ordner untergeordnet sind.

Weitere Informationen zu Seitenhierarchieansichten finden Sie unter [Anwenden von Hierarchieansichten](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**So fügen Sie Knoten einer Prozesszuordnung aus einer anderen Prozesszuordnung hinzu**

>[!NOTE]
>
>Die Prozesszuordnungen müssen dieselbe Basisdimension haben.

* Kopieren Sie eine Node aus der ersten in die zweite Prozesszuordnung mit den folgenden Methoden:

   * Um einzelne Knoten zu kopieren, klicken Sie auf die einzelnen Knoten und ziehen Sie sie in die zweite Prozesszuordnung.
   * Um mehrere Knoten zu kopieren, klicken Sie bei gedrückter Strg-Taste und ziehen Sie, um ein Feld um die zu kopierenden Nodes zu erstellen. Klicken Sie anschließend auf die markierten Nodes und ziehen Sie sie in die zweite Prozesszuordnung. Alle hervorgehobenen Knoten werden in die zweite Prozesszuordnung kopiert.

