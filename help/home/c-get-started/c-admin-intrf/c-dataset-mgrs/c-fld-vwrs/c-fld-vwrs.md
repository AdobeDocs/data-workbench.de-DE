---
description: Ein Feld-Viewer ist eine Tabelle, die die Werte eines oder mehrerer Datenfelder enthält.
title: Feld-Viewer
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Feld-Viewer{#field-viewer}

{{eol}}

Ein Feld-Viewer ist eine Tabelle, die die Werte eines oder mehrerer Datenfelder enthält.

Die Felder, deren Werte angezeigt werden, sind Eingaben oder Ausgaben der Protokollquellen, Transformationen oder erweiterten Dimensionen eines Datensatzes. Der Name des Felds wird in der Spaltenüberschrift angezeigt und jede Zeile enthält den Wert des Felds für eine einzelne Zeile der Quelldaten. Da Feld-Viewer es Ihnen ermöglichen, die Werte eines Felds anzuzeigen, sind sie beim Schreiben und Testen hilfreich [reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

Sie können einen Feld-Viewer als Callout aus einem [!DNL Transformation Dependency] oder als eigenständige Visualisierung aus der [!DNL Admin] Menü:

* Erstellen eines Feld-Viewers aus einem [!DNL Transformation Dependency] map. Wenn Sie einen Feld-Viewer aus einem [!DNL Transformation Dependency] zuordnen, wird der Viewer automatisch basierend auf der Protokollquelle, Transformation oder Dimension, auf die Sie mit der rechten Maustaste klicken, aufgefüllt. Bei einer Protokollquelle oder einer Umwandlung sind die Felder im Viewer Eingabe- oder Ausgabeformate der Protokollquelle oder Transformation. Für eine Dimension sind die Felder Eingaben der Dimension. Sie können Felder nach Bedarf hinzufügen und entfernen.

* Erstellen eines Feld-Viewers als eigenständige Visualisierung. Wenn Sie einen Feld-Viewer als eigenständige Visualisierung öffnen, können Sie eine [!DNL Log Processing Field Viewer] oder [!DNL Transformation Field Viewer]. Der Viewer ist leer und Sie müssen die gewünschten Felder zum Viewer hinzufügen. Für [!DNL Log Processing Field Viewer]können Sie Felder aus dem [!DNL Log Processing.cfg] Datei oder [!DNL Log Processing Dataset Include] -Datei. Für [!DNL Transformation Field Viewer]können Sie Felder aus dem [!DNL Transformation.cfg] Datei oder [!DNL Transformation Dataset Include] -Datei.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Feld-Viewer sind keine Tabellenvisualisierungen. Daher sind ihnen die Eigenschaften nicht mit Tabellen verknüpft.

Informationen zum Hinzufügen und Entfernen von Feldern und Filtern in einem Feld-Viewer finden Sie unter [Verwaltungsschnittstellen](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
