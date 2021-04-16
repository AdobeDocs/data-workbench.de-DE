---
description: Jede DPU, von der das Dashboard Daten visualisieren soll, muss über eine Abfragen-API-Lizenz verfügen.
title: Überprüfen der Abfrage-API-Aktivierung
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Überprüfen der Abfrage-API-Aktivierung{#verifying-query-api-enablement}

Jede DPU, von der das Dashboard Daten visualisieren soll, muss über eine Abfragen-API-Lizenz verfügen.

Im Folgenden finden Sie einige Anweisungen, wie Sie überprüfen können, ob die Abfragen-API installiert und aktiviert ist.

1. Suchen Sie das Zertifikat des Data Workbench-Servers.
1. Öffnen Sie dieses Zertifikat in einem Texteditor.
1. Stellen Sie sicher, dass die Zeile `Product = Query API` im Zertifikat vorhanden ist.
1. Öffnen Sie im Ordner **[!UICONTROL Trace]** den Ordner [!DNL InsightServer64.log] in einem Texteditor.
1. Stellen Sie sicher, dass in den neuesten Startprotokolleinträgen die Zeile `Enabling Query API (licensed)` angezeigt wird.

* Wenn die Abfragen-API nicht aktiviert ist, wird der Eintrag `Not enabling Query API (not licensed)` angezeigt.
* Wenn Sie keine Protokolleinträge sehen oder vermuten, dass der Data Workbench-Server seit dem Hinzufügen der Abfrage-API neu gestartet wurde, starten Sie den Data Workbench-Server erneut und überprüfen Sie das Protokoll.

   Wenn Sie nicht überprüfen können, ob die Abfragen-API aktiviert ist, wenden Sie sich zwecks Hilfe an Adobe ClientCare.
