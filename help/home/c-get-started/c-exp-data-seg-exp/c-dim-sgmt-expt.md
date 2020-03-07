---
description: Alle Daten, die Sie exportieren möchten, müssen als Dimension im Profil definiert werden.
solution: Analytics
title: Erstellen von Dimensionen für die Verwendung mit Segmentexport
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erstellen von Dimensionen für die Verwendung mit Segmentexport{#create-dimensions-for-use-with-segment-export}

Alle Daten, die Sie exportieren möchten, müssen als Dimension im Profil definiert werden.

Wenn die Dimension nicht bereits im Profil vorhanden ist, müssen Sie sie erstellen. Sie können Dimensionen mit einer der folgenden Methoden erstellen:

* Fügen Sie der [!DNL Transformation.cfg] Datei eine Dimension hinzu. Siehe Handbuch zur Konfiguration von *Datasets*.

* Create a new [!DNL .dim] file. Siehe [Erstellen und Bearbeiten abgeleiteter Dimensionen](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Treffen Sie Auswahlen in einer Visualisierung wie einer Prozesszuordnung oder einem Segment und speichern Sie die Auswahl als Dimension. Siehe [Speichern von Dimensionen aus Prozesszuordnungen](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) und [Erstellen von Segmentdimensionen](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

Für das Exportieren eines Datenfelds wie Tracking-ID oder E-Mail-Adresse (das viele Elemente enthalten kann) müssen Sie eine denormale Dimension erstellen, die die Rohzeichenfolgen der Daten speichert.

Weitere Informationen zu denormalen Dimensionen finden Sie im Handbuch zur Konfiguration von *Datasets*.
