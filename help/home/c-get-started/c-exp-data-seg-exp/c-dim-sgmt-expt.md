---
description: Alle Daten, die Sie exportieren möchten, müssen als Dimension im Profil definiert werden.
title: Erstellen von Dimensionen für die Verwendung mit Segmentexport
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# Erstellen von Dimensionen für die Verwendung mit Segmentexport{#create-dimensions-for-use-with-segment-export}

{{eol}}

Alle Daten, die Sie exportieren möchten, müssen als Dimension im Profil definiert werden.

Wenn die Dimension nicht bereits im Profil vorhanden ist, müssen Sie sie erstellen. Sie können Dimensionen mit einer der folgenden Methoden erstellen:

* Fügen Sie der [!DNL Transformation.cfg] -Datei. Siehe *Anleitung zur Datensatzkonfiguration*.

* Erstellen Sie eine neue [!DNL .dim] -Datei. Siehe [Erstellen und Bearbeiten abgeleiteter Dimensionen](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Treffen Sie Auswahlen in einer Visualisierung wie einer Prozesszuordnung oder einem Segment und speichern Sie die Auswahlen als Dimension. Siehe [Speichern von Dimensionen aus Prozesskarten](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) und [Erstellen von Dimensionen](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

Für den Export eines Datenfelds wie Tracking-ID oder E-Mail-Adresse (das viele Elemente enthalten kann) ist es erforderlich, eine denormale Dimension zu erstellen, in der die Rohzeichenfolgen der Daten gespeichert werden.

Weitere Informationen zu denormalen Dimensionen finden Sie unter *Anleitung zur Datensatzkonfiguration*.
