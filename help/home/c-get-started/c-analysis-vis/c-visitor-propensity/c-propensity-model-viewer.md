---
description: Mit einem Modell-Viewer können Sie mithilfe der Tendenzauswertung ein logistisches Regressionsmodell erstellen.
solution: Analytics
title: Modell-Viewer
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Model Viewer{#model-viewer}

Mit einem Modell-Viewer können Sie mithilfe der Tendenzauswertung ein logistisches Regressionsmodell erstellen.

Die Modellanzeige zeigt die Gewichte der einzelnen Eingabevariablen (einschließlich des Konstantenbegriffs) und ihren statistischen Fehlerbereich an. Eingabevariablen, die einen hohen absoluten Koeffizienten und eine geringe Fehlerspanne aufweisen, sind die wichtigsten Prädiktoren im Modell.

**So öffnen Sie ein Modell-Viewer-Diagramm**

1. Auswählen [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Bewegen Sie den Mauszeiger über &quot;Modell abgeschlossen&quot;eines gespeicherten Ergebnisses.

![](assets/propensity_model_viewer.png)

Die Eingabevariablen mit einem Koeffizienten >= 1 sind positive Einflüsse auf das Tendenzmodell. Die Koeffizienten &lt; 1 sind negative Einflüsse auf das Tendenzmodell. Der in den Klammern definierte Bereich ist der Fehler und zeigt die Konsistenz der Eingabevariablen über die erfolgreiche Population hinweg an.
