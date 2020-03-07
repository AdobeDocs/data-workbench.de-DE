---
description: Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Breiten- und Längengraddaten abzurufen, wird die Position des Punkts durch Abrufen der einzelnen Elemente und der zugehörigen Längen- und Breitengrad aus der Lookup-Datei ermittelt.
solution: Analytics
title: Definieren von Elementpunktebenen mit Verweis auf Suchdateien
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definieren von Elementpunktebenen mit Verweis auf Suchdateien{#defining-element-point-layers-referencing-lookup-files}

Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Breiten- und Längengraddaten abzurufen, wird die Position des Punkts durch Abrufen der einzelnen Elemente und der zugehörigen Längen- und Breitengrad aus der Lookup-Datei ermittelt.

Anstatt eine Lookup-Datei zu verwenden, können Sie die [!DNL Dynamic Points] Funktion verwenden, die die Längen- und Breitengrade einer Position in den Namen jedes Elements einer Dimension einbettet. Siehe [Definieren von Elementpunktebenen mithilfe von dynamischen Punkten](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Um eine Elementpunktebene zu definieren, die auf eine Lookup-Datei verweist, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Eine Dimension** , die in der [!DNL Transformation.cfg] Datei oder in einem Transformationsdataset definiert ist, enthält die Datei. Weitere Informationen zu Transformationskonfigurationsdateien finden Sie im Handbuch zur Konfiguration von *DataSet*.

* **Eine Lookup-Datei** , die die Daten enthält, die zur Darstellung der einzelnen Datenpunkte verwendet werden. Diese Datei muss mindestens drei Datenspalten für jeden Datenpunkt enthalten: Schlüssel, Längengrad und Breitengrad. Weitere Informationen zum erforderlichen Format der Lookup-Datei finden Sie unter [Element Point Lookup File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Eine Ebenendatei** , die den Speicherort der Lookup-Datei angibt und die zugehörige Dimension und Metrik sowie die Schlüssel-, Längen- und Breitenspaltennamen in der Lookup-Datei identifiziert. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter Dateiformat für [Elementpunkte](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Die mit dem [!DNL Zip Points.layer] Profil bereitgestellte [!DNL Geography] Datei ist eine Elementpunktebene, die die [!DNL Zipcode.dim] Datei, die [!DNL Sessions.metric] Datei, die [!DNL Zip Points.txt] Nachschlagedatei und die Namen der Schlüssel-, Längen-, Breiten- und Namensspalten in der Nachschlagedatei identifiziert.

