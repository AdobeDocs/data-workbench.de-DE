---
description: Jede DPU, aus der das Dashboard Daten visualisieren soll, muss über eine Abfrage-API-Lizenz verfügen.
title: Überprüfen der Abfrage-API-Aktivierung
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Überprüfen der Abfrage-API-Aktivierung{#verifying-query-api-enablement}

{{eol}}

Jede DPU, aus der das Dashboard Daten visualisieren soll, muss über eine Abfrage-API-Lizenz verfügen.

Im Folgenden finden Sie einige Anweisungen dazu, wie Sie überprüfen können, ob die Abfrage-API installiert und aktiviert ist.

1. Suchen Sie das Zertifikat Ihres Data Workbench-Servers.
1. Öffnen Sie dieses Zertifikat in einem Texteditor.
1. Stellen Sie sicher, dass die Zeile `Product = Query API` im Zertifikat vorhanden ist.
1. Im **[!UICONTROL Trace]** Ordner, öffnen Sie die [!DNL InsightServer64.log] in einem Texteditor.
1. Stellen Sie in den neuesten Startprotokolleinträgen sicher, dass die Zeile `Enabling Query API (licensed)` angezeigt.

* Wenn die Abfrage-API nicht aktiviert ist, wird der Eintrag `Not enabling Query API (not licensed)`.
* Wenn Sie keine Protokolleinträge sehen oder vermuten, dass der Data Workbench-Server seit dem Hinzufügen der Abfrage-API neu gestartet wurde, starten Sie den Data Workbench-Server erneut und überprüfen Sie das Protokoll.

   Wenn Sie nicht überprüfen können, ob die Abfrage-API aktiviert ist, wenden Sie sich zur Unterstützung an Adobe ClientCare.
