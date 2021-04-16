---
description: Grundlegende Informationen zu den Geografie-Profil-Ebenen, den Arten von Bildebenen und dem Erstellen neuer Ebenen.
title: Grundlagen zu Bildebenen
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Grundlagen zu Bildebenen{#understanding-imagery-layers}

Grundlegende Informationen zu den Geografie-Profil-Ebenen, den Arten von Bildebenen und dem Erstellen neuer Ebenen.

## Arten von Bildebenen {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] ermöglicht die Ansicht der folgenden Arten von Bildebenen in Data Workbench:

* **Terrain-Bildebene:** Diese Art von Ebene zeigt Geländebilder der Erde an, über die geografische Daten angezeigt werden können. Die weltweite Visualisierung in Data Workbench ist ein Beispiel für eine Terrain-Bildebene. Siehe [Arbeiten mit Terrain-Bildebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktebene:** Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. Siehe [Arbeiten mit Elementpunktebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorebene:** Diese Art von Ebene zeigt Vektordaten (Liniengrafiken) auf der Welt an. Siehe [Arbeiten mit Vektorebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Aufgabe der Analyse angezeigt werden sollen.

## Geografische Profil-Ebenen {#section-4d9fb9b357764493a4d97d2b4068bb67}

Das [!DNL Geography]-Profil stellt Ihnen eine Reihe von Standardbildebenen zur Verfügung, die im Ordner Profiles\Geography\Maps folder within the data workbench server installation directory gespeichert sind:

* **Blue Marble 2km:** Diese Terrain-Bildebene erstellt eine 3-D-Karte der Welt, was angezeigt wird, wenn Sie die globale Visualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die Datei [!DNL Blue Marble 2km.layer] verweist auf die Datei [!DNL Blue Marble 2km.tsi].

   Weitere Informationen zum Arbeiten mit der globalen Visualisierung finden Sie im *Data Workbench Benutzerhandbuch*.

* **Zip-Punkte:** Diese Elementpunktebene ermöglicht die Zuordnung von Positionen in Ihrem Dataset mit einem US-Postleitzahl. Die Lookup-Datei [!DNL Zip Points.txt] (bereitgestellt von Adobe) enthält eine Liste aller Postleitzahlen der Vereinigten Staaten sowie die Längen- und Breitengrade der Postleitzahlen. Die Datei [!DNL Zip Points.layer] verweist auf die Datei [!DNL Zip Points.txt] und die Datei [!DNL Zipcode.dim] und enthält die Konfigurationsparameter, die zum Anzeigen der Speicherorte auf der Welt erforderlich sind. Jedes Element der ZIP-Code-Dimension ( [!DNL Zipcode.dim]), das Sie in Ihrem Dataset definieren, wird auf der Welt mit dem Breiten- und Längengrad zugeordnet, der für diesen Postleitzahl in der [!DNL Zip Points.txt]-Nachschlagedatei aufgelistet ist.

   Weitere Informationen zum Definieren von Dimensionen finden Sie im Handbuch zur Dataset-Konfiguration.**

* **Grenzen:** Diese Vektorschicht bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen der natürlichen physikalischen Merkmale der Erde, wie Seen und Inseln. Die Datei [!DNL Boundaries.layer] verweist auf eine oder mehrere der Dateien [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] und [!DNL world boundaries.vec].

* **IP-Koordinaten:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen zu ermöglichen, Positionen im Datensatz mithilfe von IP-Adressen zuzuordnen. Die [!DNL IP Coordinates.layer]-Datei verweist auf die Dimension &quot;Koordinaten&quot;( [!DNL Coordinates.dim]) und gibt die Metrik &quot;Besucher&quot;als Metrik an, die zur Bestimmung der Punktgröße auf der Welt für jede Koordinate verwendet werden soll.

Ihr [!DNL Geography]-Profil oder andere Profil in Ihrer Installation können zusätzliche Bildebenen enthalten, die die Adobe bereitgestellt oder Ihre Firma erstellt hat.

## Erstellen neuer Ebenen {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Typ der im Profil [!DNL Geography] enthaltenen Ebenendatei in einen beliebigen Profils\*Profil*\Maps-Ordner kopieren und dann die Datei entsprechend umbenennen und bearbeiten. Alle neuen Ebenen müssen folgende Anforderungen erfüllen:

* Die Datei [!DNL .layer] muss dem Format eines der unterstützten Ebenentypen entsprechen.
* Die [!DNL .layer]-Datei muss bei Bedarf auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Lookup-Datei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden, und ihr Pfad muss in der Datei [!DNL .layer] genau angegeben werden.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenendateien und die zugehörigen Dateien finden Sie im Abschnitt zum jeweiligen Ebenentyp in diesem Kapitel.
