---
description: Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Breiten- und Längengraddaten abzurufen, wird die Position des Punkts durch Abrufen der einzelnen Elemente und der zugehörigen Längen- und Breitengrad aus der Lookup-Datei ermittelt.
title: Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Definieren von Elementpunktebenen mit Verweis auf Lookup-Dateien{#defining-element-point-layers-referencing-lookup-files}

Beim Erstellen einer Elementpunktebene, die auf eine Lookup-Datei verweist, um Breiten- und Längengraddaten abzurufen, wird die Position des Punkts durch Abrufen der einzelnen Elemente und der zugehörigen Längen- und Breitengrad aus der Lookup-Datei ermittelt.

Statt eine Lookup-Datei zu verwenden, können Sie die Funktion [!DNL Dynamic Points] verwenden, mit der die Breiten- und Längengrade einer Position im Namen jedes Elements einer Dimension eingebettet werden. Siehe [Definieren von Elementpunktebenen mithilfe von dynamischen Punkten](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Um eine Elementpunktebene zu definieren, die auf eine Lookup-Datei verweist, müssen Sie Folgendes erstellen oder bereits verfügbar sein:

* **Eine in der** Datei definierte  [!DNL Transformation.cfg] Dimension oder ein Transformationsdataset enthalten eine Datei. Weitere Informationen zu Transformationskonfigurationsdateien finden Sie im Handbuch *Dataset-Konfiguration*.

* **Eine Lookup-** Datei, die die Daten enthält, mit denen jeder Datenpunkt gezeichnet wird. Diese Datei muss mindestens drei Datenspalten für jeden Datenpunkt enthalten: Schlüssel, Längengrad und Breitengrad. Weitere Informationen zum erforderlichen Format der Lookup-Datei finden Sie unter [Element Point Lookup File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Eine Ebenendatei,** die den Speicherort der Lookup-Datei angibt und die zugehörige Dimension und Metrik sowie die Schlüssel-, Längen- und Breitenspaltennamen in der Lookup-Datei identifiziert. Weitere Informationen zum erforderlichen Format der Ebenendatei finden Sie unter [Element Point Layer File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Die [!DNL Zip Points.layer]-Datei, die mit dem [!DNL Geography]-Profil bereitgestellt wird, ist eine Elementpunktebene, die die [!DNL Zipcode.dim]-Datei, die [!DNL Sessions.metric]-Datei, die [!DNL Zip Points.txt]-Nachschlagedatei und die Namen der Schlüssel-, Längengrad-, Breiten- und Namensspalten in der Nachschlagedatei identifiziert.
