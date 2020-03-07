---
description: Jede DPU, von der aus das Dashboard Daten visualisieren soll, muss über eine Abfrage-API-Lizenz verfügen.
solution: Analytics
title: Überprüfen der Abfrage-API-Aktivierung
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Überprüfen der Abfrage-API-Aktivierung{#verifying-query-api-enablement}

Jede DPU, von der aus das Dashboard Daten visualisieren soll, muss über eine Abfrage-API-Lizenz verfügen.

Im Folgenden finden Sie einige Anweisungen, wie Sie überprüfen können, ob die Abfrage-API installiert und aktiviert ist.

1. Suchen Sie das Zertifikat des Data Workbench-Servers.
1. Öffnen Sie dieses Zertifikat in einem Texteditor.
1. Stellen Sie sicher, dass die Zeile im Zertifikat `Product = Query API` vorhanden ist.
1. Öffnen Sie den **[!UICONTROL Trace]** Ordner in einem Texteditor [!DNL InsightServer64.log] .
1. Vergewissern Sie sich, dass die Zeile in den neuesten Startprotokolleinträgen `Enabling Query API (licensed)` angezeigt wird.

* Wenn die Abfrage-API nicht aktiviert ist, wird der Eintrag angezeigt `Not enabling Query API (not licensed)`.
* Wenn Sie keine Protokolleinträge sehen oder vermuten, dass der Data Workbench-Server seit dem Hinzufügen der Abfrage-API neu gestartet wurde, starten Sie den Data Workbench-Server erneut und überprüfen Sie das Protokoll.

   Wenn Sie nicht überprüfen können, ob die Abfrage-API aktiviert ist, wenden Sie sich zwecks Hilfe an Adobe ClientCare.
