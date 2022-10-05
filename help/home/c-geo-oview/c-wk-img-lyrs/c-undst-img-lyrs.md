---
description: Konzeptinformationen zu den Geografie-Profilebenen, Arten von Bildebenen und Erstellen neuer Ebenen.
title: Grundlagen zu Bildebenen
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Grundlagen zu Bildebenen{#understanding-imagery-layers}

{{eol}}

Konzeptinformationen zu den Geografie-Profilebenen, Arten von Bildebenen und Erstellen neuer Ebenen.

## Arten von Bildebenen {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] ermöglicht Ihnen, die folgenden Arten von Bildebenen in Data Workbench anzuzeigen:

* **Topografiebildebene:** Diese Art von Ebene zeigt Topografiebilder der Erde, über welche geografischen Daten angezeigt werden können. Die globale Visualisierung in Data Workbench ist ein Beispiel für eine Topografiebildebene. Siehe [Arbeiten mit Topografiebildebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktebene:** Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. Siehe [Arbeiten mit Elementpunktebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorebene:** Diese Art von Ebene zeigt Vektordaten (Liniengrafiken) auf der Welt an. Siehe [Arbeiten mit Vektorebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Analyseaufgabe angezeigt werden soll.

## Geografische Profilebenen {#section-4d9fb9b357764493a4d97d2b4068bb67}

Die [!DNL Geography] profile bietet eine Reihe von Standardbildebenen, die im Ordner Profile\Geografie\Maps im Installationsordner des Data Workbench-Servers gespeichert sind:

* **Blauer Marmor 2 km:** Diese Topografiebildebene erstellt eine 3D-Weltkarte, die angezeigt wird, wenn Sie die Globalvisualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die [!DNL Blue Marble 2km.layer] -Datei referenziert die [!DNL Blue Marble 2km.tsi] -Datei.

   Weitere Informationen zum Arbeiten mit der globalen Visualisierung finden Sie in der *Data Workbench-Benutzerhandbuch*.

* **Postleitzahlen:** Mit dieser Elementpunktebene können Sie Positionen in Ihrem Datensatz mithilfe einer US-Postleitzahl zuordnen. Die [!DNL Zip Points.txt] Die Lookup-Datei (bereitgestellt von Adobe) enthält eine Liste aller US-Postleitzahlen sowie den Längen- und Breitengrad jeder Postleitzahl. Die [!DNL Zip Points.layer] -Datei referenziert die [!DNL Zip Points.txt] und [!DNL Zipcode.dim] und enthält die Konfigurationsparameter, die zur Anzeige der Orte auf der Welt erforderlich sind. Jedes Element der Dimension Postleitzahl ( [!DNL Zipcode.dim]), die Sie in Ihrem Datensatz definieren, auf der Welt mithilfe des Breiten- und Längengrads zugeordnet wird, der für diese Postleitzahl in der [!DNL Zip Points.txt] Suchdatei.

   Informationen zum Definieren von Dimensionen finden Sie unter *Anleitung zur Datensatzkonfiguration.*

* **Grenzen:** Diese Vektorebene bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen der natürlichen physischen Merkmale der Erde, wie Seen und Inseln. Die [!DNL Boundaries.layer] -Datei referenziert eine oder mehrere der [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]und [!DNL world boundaries.vec] Dateien.

* **IP-Koordinaten:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen zu ermöglichen, Positionen in Ihrem Datensatz mithilfe von IP-Adressen zuzuordnen. Die [!DNL IP Coordinates.layer] -Datei referenziert die Dimension Koordinaten ( [!DNL Coordinates.dim]) und gibt die Besuchermetrik als Metrik an, die zur Bestimmung der Größe der Punkte auf der Welt für jede Koordinate verwendet werden soll.

Ihre [!DNL Geography] Profile oder andere Profile in Ihrer Installation können zusätzliche Bildebenen enthalten, die von der Adobe bereitgestellt oder von Ihrem Unternehmen erstellt wurden.

## Erstellen neuer Ebenen {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Ebenentyp kopieren, der in der Datei [!DNL Geography] Profile in den Ordner Profile\*Profilname*\Maps und benennen und bearbeiten Sie dann die Datei entsprechend. Alle neuen Schichten müssen die folgenden Anforderungen erfüllen:

* Die [!DNL .layer] -Datei muss dem Format eines der unterstützten Ebenen-Typen entsprechen.
* Die [!DNL .layer] -Datei muss ggf. auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Lookup-Datei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden und ihr Pfad muss genau im [!DNL .layer] -Datei.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenen-Dateitypen und die zugehörigen Dateien finden Sie im Abschnitt in diesem Kapitel zum entsprechenden Ebenentyp.
