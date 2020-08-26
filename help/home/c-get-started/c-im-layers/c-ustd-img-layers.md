---
description: Konzeptbezogene Informationen zu Bildebenen.
solution: Analytics
title: Über Bildebenen
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: f4b37f50b115a1e1d2c9d000897a8fa47b03b233
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---


# Über Bildebenen{#about-imagery-layers}

Konzeptbezogene Informationen zu Bildebenen.

## Arten von Bildebenen {#section-891cbf61e8334690bd203a2bb9761b25}

Folgende Arten von Bildebenen können in der Data Workbench Ansicht werden:

* **[!UICONTROL Terrain image layer]:** Diese Art von Ebene zeigt Bodenbilder der Erde an, über die geografische Daten angezeigt werden können. Die weltweite Visualisierung in ist ein Beispiel für eine Bodenbildschicht. See [Working with Terrain Image Layers](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. See [Working with Element Point Layers](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Diese Art von Ebene zeigt Vektordaten (Strichgrafiken) auf der Welt an. See [Working with Vector Layers](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotationen und Erläuterungen zu Visualisierungen durch eine Präsentationseinblendung. Hinzufügen von Textfeldern, Pfeilen, Bildern und Farbkodierungen, um Daten hervorzuheben und zu verdeutlichen und dann mit anderen zu teilen.

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Analyse-Aufgabe angezeigt werden sollen.

## Geografische Profil-Ebenen {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Das [!DNL Geography] Profil stellt Ihnen eine Reihe von Standardbildebenen zur Verfügung, die im Ordner Profiles\Geography\Maps folder within the Data Workbench server installation directory gespeichert werden:

* **[!UICONTROL Blue Marble 2km]:** Diese Terrain-Bildebene erstellt eine 3-D-Karte der Welt, was angezeigt wird, wenn Sie die globale Visualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die [!DNL Blue Marble 2km.layer] Datei verweist auf die [!DNL Blue Marble 2km.tsi] Datei.

* **[!UICONTROL Zip Points]:** Mit dieser Elementpunktebene können Sie Positionen in Ihrem Dataset mit einem US-Postleitzahl zuordnen. Die [!DNL Zip Points.txt] Lookup-Datei (bereitgestellt von Adobe) enthält eine Liste aller Postleitzahlen der Vereinigten Staaten sowie die Längen- und Breitengrade der Postleitzahlen. Die [!DNL Zip Points.layer] Datei verweist auf die [!DNL Zip Points.txt] Datei und die [!DNL Zipcode.dim] Datei und enthält die Konfigurationsparameter, die zum Anzeigen der Speicherorte auf der Welt erforderlich sind. Jedes Element der ZIP-Code-Dimension ( [!DNL Zipcode.dim]), das Sie in Ihrem Datensatz definieren, wird auf der Welt mit dem Breiten- und Längengrad zugeordnet, der für diesen ZIP-Code in der [!DNL Zip Points.txt] Lookup-Datei aufgelistet ist.

   Weitere Informationen zum Definieren von Dimensionen finden Sie im Handbuch zur *Datensatzkonfiguration*.

* **[!UICONTROL Boundaries]:** Diese Vektorschicht bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen der natürlichen physikalischen Merkmale der Erde, wie Seen und Inseln. Die [!DNL Boundaries.layer] Datei verweist auf eine oder mehrere der Dateien [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]und [!DNL world boundaries.vec] .

* **[!UICONTROL IP Coordinates]:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen zu ermöglichen, Positionen in Ihrem Datensatz mithilfe von IP-Adressen zuzuordnen. Die [!DNL IP Coordinates.layer] Datei verweist auf die Dimension &quot;Koordinaten&quot;( [!DNL Coordinates.dim]) und gibt die Metrik &quot;Besucher&quot;als Metrik an, die zur Bestimmung der Punktgröße auf der Welt für jede Koordinate verwendet werden soll.

Ihr [!UICONTROL NL Geography] Profil oder andere Profil in Ihrer Installation können zusätzliche Bildebenen enthalten, die von der Adobe bereitgestellt oder von Ihrer Firma erstellt wurden.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Ebenentyp, der im [!DNL Geography] Profil enthalten ist, in einen beliebigen Profil kopieren\*Profil-Name*\Maps-Ordner und dann die Datei entsprechend umbenennen und bearbeiten. Alle neuen Ebenen müssen folgende Anforderungen erfüllen:

* Die [!DNL .layer] Datei muss dem Format eines der unterstützten Ebenentypen entsprechen.
* Die [!DNL .layer] Datei muss gegebenenfalls auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Nachschlagedatei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden, und ihr Pfad muss in der [!DNL .layer] Datei genau angegeben werden.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenendateien und die zugehörigen Dateien finden Sie im Abschnitt zum jeweiligen Ebenentyp in diesem Kapitel.
