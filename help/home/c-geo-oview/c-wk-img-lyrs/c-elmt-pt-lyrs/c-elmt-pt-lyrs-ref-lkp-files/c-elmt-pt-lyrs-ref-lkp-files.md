---
description: Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Längen- und Breitengraddaten zu erhalten, wird der Standort des Punkts durch Abrufen der einzelnen Elemente sowie der zugehörigen Längen- und Breitengrade aus der Lookup-Datei abgerufen.
title: Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien{#defining-element-point-layers-referencing-lookup-files}

Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Längen- und Breitengraddaten zu erhalten, wird der Standort des Punkts durch Abrufen der einzelnen Elemente sowie der zugehörigen Längen- und Breitengrade aus der Lookup-Datei abgerufen.

Statt eine Lookup-Datei zu verwenden, können Sie die Funktion [!DNL Dynamic Points] verwenden, mit der der Längen- und Breitengrad eines Standorts im Namen jedes Elements einer Dimension eingebettet wird. Siehe [Definieren von Elementpunktebenen mit dynamischen Punkten](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Um eine Elementpunktebene zu definieren, die auf eine Lookup-Datei verweist, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Eine in der** Datei oder einem Transformationsdatensatz definierte  [!DNL Transformation.cfg] Dimension enthält die -Datei. Informationen zu Konfigurationsdateien für Umwandlungen finden Sie im *Handbuch zur Datensatzkonfiguration*.

* **Eine Lookup-Datei** mit den Daten, die für die Darstellung der einzelnen Datenpunkte verwendet werden. Diese Datei muss mindestens drei Datenspalten für jeden Datenpunkt enthalten: der Schlüssel, der Längengrad und der Breitengrad. Weitere Informationen zum erforderlichen Format der Lookup-Datei finden Sie unter [Element Point Lookup File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Eine Ebenendatei,** die den Speicherort der Lookup-Datei angibt und die zugehörige Dimension und Metrik sowie die Schlüssel-, Längen- und Breitenspaltennamen in der Lookup-Datei angibt. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Element Point Layer File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Die mit dem Profil [!DNL Geography] bereitgestellte Datei [!DNL Zip Points.layer] ist eine Elementpunktebene, die die [!DNL Zipcode.dim]-Datei, die [!DNL Sessions.metric]-Datei, die [!DNL Zip Points.txt]-Lookup-Datei sowie die Namen der Spalten Schlüssel, Längen- und Breitengrad sowie Name in der Lookup-Datei angibt.
