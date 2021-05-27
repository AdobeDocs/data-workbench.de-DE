---
description: Hierarchieansichten sind nur bei Verwendung der Site- oder HBX-Anwendung verfügbar.
title: Anwenden von Hierarchieansichten
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Anwenden von Hierarchieansichten{#apply-hierarchy-views}

Hierarchieansichten sind nur bei Verwendung der Site- oder HBX-Anwendung verfügbar.

In der Hierarchieansicht werden die Seiten einer Website hierarchisch nach Dateinamen geordnet und alphabetisch sortiert. Die Hierarchieansicht ist zwar für die Analyse selbst nützlich, kann aber auch verwendet werden, um erweiterte Visualisierungen wie Prozesskarten einzurichten. Weitere Informationen zu Prozesskarten finden Sie unter [Prozesskarten](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Wenn Ihr Datensatz für die Ausführung auf mehreren Servern in einem Cluster konfiguriert wurde und diese Funktion ordnungsgemäß ausgeführt werden soll, muss Ihr Systemadministrator angeben, welche Maschine als Central Normalization Server fungiert. Anweisungen dazu finden Sie im Kapitel Konfigurationsdatei für die Protokollverarbeitung im *Handbuch zur Datensatzkonfiguration*.

![](assets/vis_Table_CompareHierarchy.png)

**So aktivieren oder deaktivieren Sie die Hierarchieansicht**

* Klicken Sie in einer beliebigen Seiten- oder URI-Visualisierung mit der rechten Maustaste auf ein Element oder den Titel der Seitendimension und klicken Sie auf **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Neben der Option wird ein X angezeigt, wenn [!DNL hierarchy view] aktiv ist.

   Die Hierarchie ist mithilfe einer Baumstruktur in Website-Abschnitte und Seiten unterteilt. Abschnitte (Knoten) können mit dem Symbol + oder - neben dem Abschnittsnamen erweitert oder gekürzt werden. Einzelne Seiten haben kein &quot;+&quot;- oder &quot;-&quot;-Symbol neben ihnen.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Maskieren von Dimension-Elementen in einer Hierarchieansicht {#section-e477c469934846da8d807f92fc2f3ed1}

Maskieren bezeichnet die Auswahl einer Teilmenge Ihrer Daten oder einer Teilmenge der Elemente in einer Dimension. Sie können Elemente, die nicht in die Analyse aufgenommen werden sollen, maskieren oder ausblenden. Mit den Menüoptionen [!DNL Mask] für Hierarchieansichten wählen Sie den Mindestprozentsatz einer Metrik aus, der für ein Element in der Visualisierung angezeigt werden muss.

**So maskieren Sie Daten mithilfe der  [!DNL Mask] Menüoption**

1. Klicken Sie mit der rechten Maustaste auf ein Element oder den Titel der Dimension und klicken Sie auf **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. Klicken Sie unter Mehr als auf den entsprechenden Prozentsatz und dann auf die Metrik, die Sie maskieren möchten.

Wenn Sie beispielsweise auf 0,1 % klicken und dann auf &quot;Seitenansichten&quot;klicken, maskieren Sie alle Elemente, die weniger als 0,1 % der Gesamtzahl der Seitenansichten aufweisen, und zeigen alle Elemente an, die mehr als 0,1 % der Gesamtzahl der Seitenansichten aufweisen. Wenn Sie auf 0 % klicken, maskieren Sie alle Elemente mit dem Wert 0 (null) für die ausgewählte Metrik.
