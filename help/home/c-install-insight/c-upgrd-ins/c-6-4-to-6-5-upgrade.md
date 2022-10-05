---
description: Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.5 zu aktualisieren.
title: Upgrade von Version 6.4 auf 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%

---

# Upgrade von Version 6.4 auf 6.5{#upgrading-to}

{{eol}}

Führen Sie die folgenden Schritte aus, um auf Data Workbench v6.5 zu aktualisieren.

## Upgrade-Anforderungen und Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Befolgen Sie diese Anforderungen und Empfehlungen bei der Aktualisierung auf Data Workbench 6.5.

* Änderungen in **[!DNL Components for Processing Servers\Communications.cfg]** müssen Sie diese Datei für die DWB-Version 6.5 aktualisieren. Die *SourceListServer*, *SegmentExportServer* und *NormalizeServer* -Einträge wurden entfernt. ( DPUs sollten nicht ausgeführt werden *sourcelist*, *Segmentexport* oder *Server normalisieren*. )

* Korrelationszeichner, Korrelationsmatrix, Assoziations-Akkord, Zuordnungsmatrix, Propensity Score und Best Fit Attribution-Visualisierungen sind jetzt Visualisierungen mit mehreren Durchgängen.

   Wenn ein Arbeitsbereich mehrere Visualisierungen mit mehreren Durchgängen enthält, kann Report Server standardmäßig keine Berichte mit dem Fehler generieren:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Vermeiden Sie diesen Fehler, indem Sie Ihre [!DNL ReportServer.cfg] oder fügen Sie diese Zeile Ihrer vorhandenen Datei im *Berichterstellung* Abschnitt.

   ```
   Max Multipass Per Slice = int: n
   ```

   wobei n die maximale Anzahl von Visualisierungen mit mehreren Durchgängen ist, die von Report Server in einem Arbeitsbereich unterstützt werden.
