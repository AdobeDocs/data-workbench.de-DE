---
description: Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.5 zu aktualisieren.
title: Upgrade von 6.4 auf 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Upgrading 6.4 to 6.5{#upgrading-to}

Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.5 zu aktualisieren.

## Upgrade-Anforderungen und Empfehlungen {#section-8704a9ac358246cd81233dd0982d534f}

Befolgen Sie diese Anforderungen und Empfehlungen bei der Aktualisierung auf Data Workbench 6.5.

* Änderungen in der **[!DNL Components for Processing Servers\Communications.cfg]** Datei erfordern, dass Sie diese Datei für die DWB 6.5-Version aktualisieren. Die Einträge *SourceListServer*, *SegmentExportServer* und *NormalizeServer* wurden entfernt. (DPUs sollten keine *Quellliste*, keinen *Segmentexport* oder keine *Normalisierung der Server* ausführen. )

* Korrelationsfeldzeichner, Korrelationsmatrix, Vereinszeichner, Assoziierungsmatrix, Tendenzauswertung und Visualisierungen zur optimalen Anpassung sind jetzt Visualisierungen mit mehreren Durchgängen.

   Wenn eine Arbeitsfläche mehrere Visualisierungen mit mehreren Durchgängen enthält, kann Report Server standardmäßig keine Berichte mit folgendem Fehler generieren:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Vermeiden Sie diesen Fehler, indem Sie Ihre [!DNL ReportServer.cfg] Datei aktualisieren oder diese Zeile zu Ihrer vorhandenen Datei im Abschnitt *Berichterstellung* hinzufügen.

   ```
   Max Multipass Per Slice = int: n
   ```

   wobei n die maximale Anzahl von Multipass-Visualisierungen ist, die von Report Server in einem Arbeitsbereich unterstützt werden.

