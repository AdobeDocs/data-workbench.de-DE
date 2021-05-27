---
description: Ein Feld-Viewer ist eine Tabelle, die die Werte eines oder mehrerer Datenfelder enthält.
title: Feld-Viewer
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Feld-Viewer{#field-viewer}

Ein Feld-Viewer ist eine Tabelle, die die Werte eines oder mehrerer Datenfelder enthält.

Die Felder, deren Werte angezeigt werden, sind Eingaben oder Ausgaben der Protokollquellen, Transformationen oder erweiterten Dimensionen eines Datensatzes. Der Name des Felds wird in der Spaltenüberschrift angezeigt und jede Zeile enthält den Wert des Felds für eine einzelne Zeile der Quelldaten. Da mit Feld-Viewern die Werte eines Felds angezeigt werden können, sind sie beim Schreiben und Testen von [regulären Ausdrücken](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c) hilfreich.

Sie können einen Feld-Viewer als Callout über eine [!DNL Transformation Dependency]-Zuordnung oder als eigenständige Visualisierung über das Menü [!DNL Admin] öffnen:

* Erstellen eines Feld-Viewers aus einer [!DNL Transformation Dependency]-Zuordnung. Wenn Sie einen Feld-Viewer über eine [!DNL Transformation Dependency]-Zuordnung öffnen, wird der Viewer automatisch basierend auf der Protokollquelle, der Transformation oder der Dimension, auf die Sie mit der rechten Maustaste klicken, aufgefüllt. Bei einer Protokollquelle oder einer Umwandlung sind die Felder im Viewer Eingabe- oder Ausgabeformate der Protokollquelle oder Transformation. Für eine Dimension sind die Felder Eingaben der Dimension. Sie können Felder nach Bedarf hinzufügen und entfernen.

* Erstellen eines Feld-Viewers als eigenständige Visualisierung. Wenn Sie einen Feld-Viewer als eigenständige Visualisierung öffnen, können Sie einen [!DNL Log Processing Field Viewer] oder einen [!DNL Transformation Field Viewer] erstellen. Der Viewer ist leer und Sie müssen die gewünschten Felder zum Viewer hinzufügen. Für [!DNL Log Processing Field Viewer] können Sie Felder aus der [!DNL Log Processing.cfg]-Datei oder aus einer beliebigen [!DNL Log Processing Dataset Include]-Datei hinzufügen. Für [!DNL Transformation Field Viewer] können Sie Felder aus der [!DNL Transformation.cfg]-Datei oder aus einer beliebigen [!DNL Transformation Dataset Include]-Datei hinzufügen.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Feld-Viewer sind keine Tabellenvisualisierungen. Daher sind ihnen die Eigenschaften nicht mit Tabellen verknüpft.

Informationen zum Hinzufügen und Entfernen von Feldern und Filtern in einem Feld-Viewer finden Sie unter [Administrative Schnittstellen](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
