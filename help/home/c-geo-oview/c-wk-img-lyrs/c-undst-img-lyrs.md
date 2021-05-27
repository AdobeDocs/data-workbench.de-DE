---
description: Konzeptinformationen zu den Geografie-Profilebenen, Arten von Bildebenen und Erstellen neuer Ebenen.
title: Grundlagen zu Bildebenen
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Grundlagen zu Bildebenen{#understanding-imagery-layers}

Konzeptinformationen zu den Geografie-Profilebenen, Arten von Bildebenen und Erstellen neuer Ebenen.

## Arten von Bildebenen {#section-ce25364651a04cd1b83f9ac7c231fa41}

Mit Data Workbench [!DNL Geography] können Sie die folgenden Arten von Bildebenen in Data Workbench anzeigen:

* **Topografiebildebene:**  Dieser Ebenentyp zeigt Topografiebilder der Erde an, über welche geografischen Daten angezeigt werden können. Die globale Visualisierung in Data Workbench ist ein Beispiel für eine Topografiebildebene. Siehe [Arbeiten mit Topografiebildebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktebene:**  Dieser Ebenentyp zeigt für jedes Element einer Dimension einen Punkt auf der Welt an. Siehe [Arbeiten mit Elementpunktebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorebene:** Dieser Ebenentyp zeigt Vektordaten (Liniengrafiken) auf der Welt an. Siehe [Arbeiten mit Vektorebenen](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

In Data Workbench können Sie auswählen, welche dieser Ebenen für eine bestimmte Analyseaufgabe angezeigt werden soll.

## Geografische Profilebenen {#section-4d9fb9b357764493a4d97d2b4068bb67}

Das Profil [!DNL Geography] bietet eine Reihe von Standardbildebenen, die im Ordner Profiles\Geography\Maps folder within the data workbench server installation directory gespeichert sind:

* **Blue Marble 2km:** Diese Topografiebildebene erstellt eine 3D-Weltkarte, die angezeigt wird, wenn Sie die globale Visualisierung zu einem Arbeitsbereich hinzufügen. Wenn diese Ebene nicht ausgewählt ist, ist der Globus nicht sichtbar, aber die anderen Ebenen werden weiterhin angezeigt. Die Datei [!DNL Blue Marble 2km.layer] verweist auf die Datei [!DNL Blue Marble 2km.tsi] .

   Weitere Informationen zum Arbeiten mit der globalen Visualisierung finden Sie im *Data Workbench-Benutzerhandbuch*.

* **Postleitzahlen:** Mit dieser Elementpunktebene können Sie Positionen in Ihrem Datensatz mithilfe einer US-Postleitzahl zuordnen. Die Lookup-Datei [!DNL Zip Points.txt] (bereitgestellt von Adobe) enthält eine Liste aller Postleitzahlen der Vereinigten Staaten sowie den Längen- und Breitengrad jeder Postleitzahl. Die Datei [!DNL Zip Points.layer] verweist auf die Datei [!DNL Zip Points.txt] und die Datei [!DNL Zipcode.dim] und enthält die Konfigurationsparameter, die zum Anzeigen der Speicherorte auf der Welt erforderlich sind. Jedes Element der ZIP-Code-Dimension ( [!DNL Zipcode.dim]), das Sie in Ihrem Datensatz definieren, wird auf der Welt mit dem Breiten- und Längengrad zugeordnet, der für diesen ZIP-Code in der Lookup-Datei [!DNL Zip Points.txt] aufgelistet ist.

   Informationen zum Definieren von Dimensionen finden Sie im *Handbuch zur Datensatzkonfiguration.*

* **Grenzen:** Diese Vektorschicht bietet die wichtigsten politischen Grenzen der Welt, wie Länder, sowie die Grenzen natürlicher physischer Merkmale der Erde, wie Seen und Inseln. Die Datei [!DNL Boundaries.layer] verweist auf eine oder mehrere der Dateien [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] und [!DNL world boundaries.vec].

* **IP-Koordinaten:** Diese Elementpunktebene verwendet dynamische Punkte, um Ihnen die Zuordnung von Speicherorten in Ihrem Datensatz mithilfe von IP-Adressen zu ermöglichen. Die Datei [!DNL IP Coordinates.layer] verweist auf die Dimension Koordinaten ( [!DNL Coordinates.dim]) und gibt die Metrik Besucher als Metrik an, die zur Bestimmung der Größe der Punkte auf der Welt für jede Koordinate verwendet werden soll.

Ihr [!DNL Geography]-Profil oder andere Profile in Ihrer Installation können zusätzliche Bildebenen enthalten, die von Ihrer Adobe bereitgestellt oder von Ihrem Unternehmen erstellt wurden.

## Erstellen neuer Ebenen {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Sie können neue Bildebenen erstellen, indem Sie den entsprechenden Ebenentyp, der im Profil [!DNL Geography] enthalten ist, in einen beliebigen Ordner &quot;Profile\*Profilname*\Maps&quot;kopieren und dann die Datei entsprechend umbenennen und bearbeiten. Alle neuen Schichten müssen die folgenden Anforderungen erfüllen:

* Die Datei [!DNL .layer] muss dem Format eines der unterstützten Ebenentypen entsprechen.
* Die [!DNL .layer]-Datei muss bei Bedarf auf die entsprechenden Lookup- und Dimensionsdateien verweisen.
* Die referenzierte Lookup-Datei muss auch im Installationsordner des Data Workbench-Servers gespeichert werden und ihr Pfad muss in der Datei [!DNL .layer] genau angegeben werden.

Weitere Informationen zum Format und den Parametern für die einzelnen Ebenen-Dateitypen und die zugehörigen Dateien finden Sie im Abschnitt in diesem Kapitel zum entsprechenden Ebenentyp.
