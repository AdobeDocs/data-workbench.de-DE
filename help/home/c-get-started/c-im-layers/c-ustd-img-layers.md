---
description: Konzeptinformationen zu Bildebenen.
title: Über Bildebenen
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# Über Bildebenen{#about-imagery-layers}

{{eol}}

Konzeptinformationen zu Bildebenen.

## Arten von Bildebenen {#section-891cbf61e8334690bd203a2bb9761b25}

Sie können die folgenden Arten von Bildebenen in Data Workbench anzeigen:

* **[!UICONTROL Terrain image layer]:** Diese Art von Ebene zeigt Topografiebilder der Erde, über welche geografischen Daten angezeigt werden können. Die weltweite Visualisierung in ist ein Beispiel für eine Topografiebildebene. Siehe [Arbeiten mit Topografiebildebenen](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. Siehe [Arbeiten mit Elementpunktebenen](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Diese Art von Ebene zeigt Vektordaten (Liniengrafiken) auf der Welt an. Siehe [Arbeiten mit Vektorebenen](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotationen und Erläuterungen zu Visualisierungen durch eine Präsentationseinblendung. Hinzufügen von Textfeldern, Pfeilen, Bildern und Farbkodierungen, um Daten hervorzuheben und zu verdeutlichen und dann mit anderen zu teilen.

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Analyseaufgabe angezeigt werden soll.

## Geografische Profilebenen {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Die [!DNL Geography] profile bietet eine Reihe von Standardbildebenen, die im Ordner Profile\Geografie\Maps im Installationsordner des Data Workbench-Servers gespeichert sind:

* **[!UICONTROL Blue Marble 2km]:** Diese Topografiebildebene erstellt eine 3D-Weltkarte, die angezeigt wird, wenn Sie die Globalvisualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die [!DNL Blue Marble 2km.layer] -Datei referenziert die [!DNL Blue Marble 2km.tsi] -Datei.

* **[!UICONTROL Zip Points]:** Mit dieser Elementpunktebene können Sie Positionen in Ihrem Datensatz mithilfe einer US-Postleitzahl zuordnen. Die [!DNL Zip Points.txt] Die Lookup-Datei (bereitgestellt von Adobe) enthält eine Liste aller US-Postleitzahlen sowie den Längen- und Breitengrad jeder Postleitzahl. Die [!DNL Zip Points.layer] -Datei referenziert die [!DNL Zip Points.txt] und [!DNL Zipcode.dim] und enthält die Konfigurationsparameter, die zur Anzeige der Orte auf der Welt erforderlich sind. Jedes Element der Dimension Postleitzahl ( [!DNL Zipcode.dim]), die Sie in Ihrem Datensatz definieren, auf der Welt mithilfe des Breiten- und Längengrads zugeordnet wird, der für diese Postleitzahl in der [!DNL Zip Points.txt] Suchdatei.

   Informationen zum Definieren von Dimensionen finden Sie unter *Anleitung zur Datensatzkonfiguration*.

* **[!UICONTROL Boundaries]:** Diese Vektorebene bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen der natürlichen physischen Merkmale der Erde, wie Seen und Inseln. Die [!DNL Boundaries.layer] -Datei referenziert eine oder mehrere der [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]und [!DNL world boundaries.vec] Dateien.

* **[!UICONTROL IP Coordinates]:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen zu ermöglichen, Positionen in Ihrem Datensatz mithilfe von IP-Adressen zuzuordnen. Die [!DNL IP Coordinates.layer] -Datei referenziert die Dimension Koordinaten ( [!DNL Coordinates.dim]) und gibt die Besuchermetrik als Metrik an, die zur Bestimmung der Größe der Punkte auf der Welt für jede Koordinate verwendet werden soll.

Ihre [!UICONTROL NL Geography] Profile oder andere Profile in Ihrer Installation können zusätzliche Bildebenen enthalten, die von der Adobe bereitgestellt oder von Ihrem Unternehmen erstellt wurden.

## Neue Ebene erstellen {#section-b5313773316c4e0fa748f7376a8e7f0b}

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Ebenentyp kopieren, der in der Datei [!DNL Geography] Profile in den Ordner Profile\*Profilname*\Maps und benennen und bearbeiten Sie dann die Datei entsprechend. Alle neuen Schichten müssen die folgenden Anforderungen erfüllen:

* Die [!DNL .layer] -Datei muss dem Format eines der unterstützten Ebenen-Typen entsprechen.
* Die [!DNL .layer] -Datei muss ggf. auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Lookup-Datei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden und ihr Pfad muss genau im [!DNL .layer] -Datei.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenen-Dateitypen und die zugehörigen Dateien finden Sie im Abschnitt in diesem Kapitel zum entsprechenden Ebenentyp.
