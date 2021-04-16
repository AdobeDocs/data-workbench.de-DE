---
description: Konzeptbezogene Informationen zu Bildebenen.
title: Über Bildebenen
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# Über Bildebenen{#about-imagery-layers}

Konzeptbezogene Informationen zu Bildebenen.

## Arten von Bildebenen {#section-891cbf61e8334690bd203a2bb9761b25}

Folgende Arten von Bildebenen können in der Data Workbench Ansicht werden:

* **[!UICONTROL Terrain image layer]:** Diese Art von Ebene zeigt Bodenbilder der Erde an, über die geografische Daten angezeigt werden können. Die weltweite Visualisierung in ist ein Beispiel für eine Bodenbildschicht. Siehe [Arbeiten mit Terrain-Bildebenen](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. Siehe [Arbeiten mit Elementpunktebenen](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Dieser Ebenentyp zeigt Vektordaten (Strichgrafiken) auf der Welt an. Siehe [Arbeiten mit Vektorebenen](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotationen und Erläuterungen zu Visualisierungen durch eine Präsentationseinblendung. Hinzufügen von Textfeldern, Pfeilen, Bildern und Farbkodierungen, um Daten hervorzuheben und zu verdeutlichen und dann mit anderen zu teilen.

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Analyse-Aufgabe angezeigt werden sollen.

## Geografische Profil-Ebenen {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Das [!DNL Geography]-Profil stellt Ihnen eine Reihe von Standardbildebenen zur Verfügung, die im Ordner Profiles\Geography\Maps folder within the Data Workbench server installation directory gespeichert sind:

* **[!UICONTROL Blue Marble 2km]:** Diese Terrain-Bildebene erstellt eine 3D-Weltkarte, was angezeigt wird, wenn Sie die Globalvisualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die Datei [!DNL Blue Marble 2km.layer] verweist auf die Datei [!DNL Blue Marble 2km.tsi].

* **[!UICONTROL Zip Points]:** Diese Elementpunktebene ermöglicht die Zuordnung von Positionen in Ihrem Datensatz mithilfe eines US-Postleitzahlcodes. Die Lookup-Datei [!DNL Zip Points.txt] (bereitgestellt von Adobe) enthält eine Liste aller Postleitzahlen der Vereinigten Staaten sowie die Längen- und Breitengrade der Postleitzahlen. Die Datei [!DNL Zip Points.layer] verweist auf die Datei [!DNL Zip Points.txt] und die Datei [!DNL Zipcode.dim] und enthält die Konfigurationsparameter, die zum Anzeigen der Speicherorte auf der Welt erforderlich sind. Jedes Element der ZIP-Code-Dimension ( [!DNL Zipcode.dim]), das Sie in Ihrem Dataset definieren, wird auf der Welt mit dem Breiten- und Längengrad zugeordnet, der für diesen Postleitzahl in der [!DNL Zip Points.txt]-Nachschlagedatei aufgelistet ist.

   Weitere Informationen zum Definieren von Dimensionen finden Sie im Handbuch *Konfiguration von Datasets*.

* **[!UICONTROL Boundaries]:** Diese Vektorschicht bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen der natürlichen physikalischen Eigenschaften der Erde, wie Seen und Inseln. Die Datei [!DNL Boundaries.layer] verweist auf eine oder mehrere der Dateien [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] und [!DNL world boundaries.vec].

* **[!UICONTROL IP Coordinates]:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen zu ermöglichen, Positionen in Ihrem Datensatz mithilfe von IP-Adressen zuzuordnen. Die [!DNL IP Coordinates.layer]-Datei verweist auf die Dimension &quot;Koordinaten&quot;( [!DNL Coordinates.dim]) und gibt die Metrik &quot;Besucher&quot;als Metrik an, die zur Bestimmung der Punktgröße auf der Welt für jede Koordinate verwendet werden soll.

Ihr [!UICONTROL NL Geography]-Profil oder andere Profil in Ihrer Installation können zusätzliche Bildebenen enthalten, die die Adobe bereitgestellt oder Ihre Firma erstellt hat.

## Neue Ebene {#section-b5313773316c4e0fa748f7376a8e7f0b} erstellen

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Typ der im Profil [!DNL Geography] enthaltenen Ebenendatei in einen beliebigen Profils\*Profil*\Maps-Ordner kopieren und dann die Datei entsprechend umbenennen und bearbeiten. Alle neuen Ebenen müssen folgende Anforderungen erfüllen:

* Die Datei [!DNL .layer] muss dem Format eines der unterstützten Ebenentypen entsprechen.
* Die [!DNL .layer]-Datei muss bei Bedarf auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Lookup-Datei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden, und ihr Pfad muss in der Datei [!DNL .layer] genau angegeben werden.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenendateien und die zugehörigen Dateien finden Sie im Abschnitt zum jeweiligen Ebenentyp in diesem Kapitel.
