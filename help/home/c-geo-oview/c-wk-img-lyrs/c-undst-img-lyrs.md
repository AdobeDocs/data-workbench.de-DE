---
description: Grundlegende Informationen zu den Geografie-Profilebenen, den Arten von Bildebenen und dem Erstellen neuer Ebenen.
solution: Analytics
title: Verstehen von Bildebenen
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verstehen von Bildebenen{#understanding-imagery-layers}

Grundlegende Informationen zu den Geografie-Profilebenen, den Arten von Bildebenen und dem Erstellen neuer Ebenen.

## Arten von Bildebenen {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] ermöglicht Ihnen, die folgenden Arten von Bildebenen in Data Workbench anzuzeigen:

* **Terrain-Bildebene:** Diese Art von Ebene zeigt Bodenbilder der Erde an, über die geografische Daten angezeigt werden können. Die weltweite Visualisierung in Data Workbench ist ein Beispiel für eine Terrain-Bildebene. Siehe [Arbeiten mit Terrain-Bildebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktebene:** Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. Siehe [Arbeiten mit Elementpunktebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorebene:** Diese Art von Ebene zeigt Vektordaten (Strichgrafiken) auf der Welt an. Siehe [Arbeiten mit Vektorebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Analyseaufgabe angezeigt werden sollen.

## Geografische Profilebenen {#section-4d9fb9b357764493a4d97d2b4068bb67}

Das [!DNL Geography] Profil bietet eine Reihe von Standardbildebenen, die im Ordner Profiles\Geography\Maps folder within the data workbench server installation directory gespeichert werden:

* **Blaue Marmor 2 km:** Diese Terrain-Bildebene erstellt eine 3-D-Karte der Welt, was angezeigt wird, wenn Sie die globale Visualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die [!DNL Blue Marble 2km.layer] Datei verweist auf die [!DNL Blue Marble 2km.tsi] Datei.

   Informationen zum Arbeiten mit der globalen Visualisierung finden Sie im *Data Workbench-Benutzerhandbuch*.

* **Zip-Punkte:** Mit dieser Elementpunktebene können Sie Positionen in Ihrem Dataset mit einem US-Postleitzahl zuordnen. Die (von Adobe bereitgestellte) [!DNL Zip Points.txt] Lookup-Datei enthält eine Liste aller US-Postleitzahlen sowie die Breiten- und Längengrade der Postleitzahlen. Die [!DNL Zip Points.layer] Datei verweist auf die [!DNL Zip Points.txt] Datei und die [!DNL Zipcode.dim] Datei und enthält die Konfigurationsparameter, die zum Anzeigen der Speicherorte auf der Welt erforderlich sind. Jedes Element der ZIP-Code-Dimension ( [!DNL Zipcode.dim]), das Sie in Ihrem Datensatz definieren, wird auf der Welt mit dem Breiten- und Längengrad zugeordnet, der für diesen ZIP-Code in der [!DNL Zip Points.txt] Lookup-Datei aufgelistet ist.

   Informationen zum Definieren von Dimensionen finden Sie im Handbuch zur Konfiguration von *Datasets.*

* **Grenzen:** Diese Vektorschicht bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen der natürlichen physikalischen Merkmale der Erde, wie Seen und Inseln. Die [!DNL Boundaries.layer] Datei verweist auf eine oder mehrere der Dateien [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]und [!DNL world boundaries.vec] .

* **IP-Koordinaten:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen zu ermöglichen, Positionen in Ihrem Datensatz mithilfe von IP-Adressen zuzuordnen. Die [!DNL IP Coordinates.layer] Datei verweist auf die Dimension &quot;Koordinaten&quot;( [!DNL Coordinates.dim]) und gibt die Metrik &quot;Besucher&quot;als Metrik an, die zur Bestimmung der Größe der Punkte auf der Welt für jede Koordinate verwendet werden soll.

Ihr [!DNL Geography] Profil oder andere Profile in Ihrer Installation können zusätzliche Bildebenen enthalten, die von Adobe bereitgestellt oder von Ihrem Unternehmen erstellt wurden.

## Erstellen neuer Ebenen {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Typ der im Profil enthaltenen Ebenendatei in einen beliebigen Ordner &quot;Profile\*Profilname*\Maps&quot;kopieren und dann die Datei entsprechend umbenennen und bearbeiten. [!DNL Geography] Alle neuen Ebenen müssen folgende Anforderungen erfüllen:

* Die [!DNL .layer] Datei muss dem Format eines der unterstützten Ebenentypen entsprechen.
* Die [!DNL .layer] Datei muss gegebenenfalls auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Lookup-Datei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden und der Pfad muss in der [!DNL .layer] Datei genau angegeben werden.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenendateien und die zugehörigen Dateien finden Sie im Abschnitt zum jeweiligen Ebenentyp in diesem Kapitel.
