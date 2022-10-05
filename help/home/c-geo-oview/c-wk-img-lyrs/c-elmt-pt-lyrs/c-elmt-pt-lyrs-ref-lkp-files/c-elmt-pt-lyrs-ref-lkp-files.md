---
description: Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Längen- und Breitengraddaten zu erhalten, wird der Standort des Punkts durch Abrufen der einzelnen Elemente sowie der zugehörigen Längen- und Breitengrade aus der Lookup-Datei abgerufen.
title: Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Längen- und Breitengraddaten zu erhalten, wird der Standort des Punkts durch Abrufen der einzelnen Elemente sowie der zugehörigen Längen- und Breitengrade aus der Lookup-Datei abgerufen.

Anstatt eine Lookup-Datei zu verwenden, können Sie die [!DNL Dynamic Points] -Funktion, die den Längen- und Breitengrad eines Standorts im Namen jedes Elements einer Dimension einbettet. Siehe [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Um eine Elementpunktebene zu definieren, die auf eine Lookup-Datei verweist, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Dimension** definiert im [!DNL Transformation.cfg] -Datei oder einem Transformationsdatensatz enthält die -Datei. Informationen zu Konfigurationsdateien für Umwandlungen finden Sie in der *Anleitung zur Datensatzkonfiguration*.

* **Eine Lookup-Datei** enthält die Daten, die zur Zeichnung jedes Datenpunkts verwendet werden. Diese Datei muss mindestens drei Datenspalten für jeden Datenpunkt enthalten: der Schlüssel, der Längengrad und der Breitengrad. Weitere Informationen zum erforderlichen Format der Lookup-Datei finden Sie unter [Format der Elementpunkt-Lookup-Datei](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Ebenendatei** , der den Speicherort der Lookup-Datei angibt und die zugehörige Dimension und Metrik sowie die Schlüssel-, Längen- und Breitenspaltennamen in der Lookup-Datei identifiziert. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Format der Elementpunkt-Schichtdatei](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Die [!DNL Zip Points.layer] -Datei, die mit der [!DNL Geography] profile ist eine Elementpunktebene, die die [!DNL Zipcode.dim] -Datei, die [!DNL Sessions.metric] -Datei, die [!DNL Zip Points.txt] Lookup-Datei sowie die Namen der Schlüssel-, Längen-, Breiten- und Namensspalten in der Lookup-Datei.
