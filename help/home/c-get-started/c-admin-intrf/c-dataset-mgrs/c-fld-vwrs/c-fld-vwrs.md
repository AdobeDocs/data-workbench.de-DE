---
description: Ein Feld-Viewer ist eine Tabelle mit den Werten eines oder mehrerer Datenfelder.
title: Feld-Viewer
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Feld-Viewer{#field-viewer}

Ein Feld-Viewer ist eine Tabelle mit den Werten eines oder mehrerer Datenfelder.

Die Felder, deren Werte angezeigt werden, sind Eingaben oder Ausgaben der Protokollquellen, Transformationen oder erweiterten Dimensionen eines Datensatzes. Der Name des Felds wird in der Spaltenüberschrift angezeigt, und jede Zeile enthält den Wert des Felds für eine einzelne Zeile mit Quelldaten. Da field-Viewer Ihnen die Anzeige der Feldwerte ermöglichen, sind sie beim Schreiben und Testen von [normalen Ausdrücken](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c) hilfreich.

Sie können einen field Viewer als Callout aus einer [!DNL Transformation Dependency]-Map oder als Standalone-Visualisierung aus dem Menü [!DNL Admin] öffnen:

* Erstellen eines field Viewers aus einer [!DNL Transformation Dependency]-Map. Wenn Sie einen field Viewer aus einer [!DNL Transformation Dependency]-Map öffnen, wird der Viewer automatisch basierend auf der Protokollquelle, Transformation oder Dimension gefüllt, auf die Sie mit der rechten Maustaste klicken. Bei einer Protokollquelle oder einer Transformation sind die Felder im Viewer Eingaben oder Ausgaben der Protokollquelle oder Transformation. Bei einer Dimension sind die Felder Eingaben der Dimension. Sie können Felder nach Bedarf hinzufügen und entfernen.

* Erstellen eines field Viewers als Standalone-Visualisierung. Wenn Sie einen field-Viewer als Standalone-Visualisierung öffnen, können Sie ein [!DNL Log Processing Field Viewer] oder ein [!DNL Transformation Field Viewer] erstellen. Der Viewer ist leer und Sie müssen die gewünschten Felder zum Viewer hinzufügen. Bei einem [!DNL Log Processing Field Viewer] können Sie Felder aus der [!DNL Log Processing.cfg]-Datei oder einer [!DNL Log Processing Dataset Include]-Datei hinzufügen. Bei einem [!DNL Transformation Field Viewer] können Sie Felder aus der [!DNL Transformation.cfg]-Datei oder einer [!DNL Transformation Dataset Include]-Datei hinzufügen.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Feld-Viewer sind keine Tabellenvisualisierungen; Sie haben daher nicht die Eigenschaften, die mit Tabellen verknüpft sind.

Weitere Informationen zum Hinzufügen und Entfernen von Feldern und zum Filtern in einem Feld-Viewer finden Sie unter [Administrative Schnittstellen](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
