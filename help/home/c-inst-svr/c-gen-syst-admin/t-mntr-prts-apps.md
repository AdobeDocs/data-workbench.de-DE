---
description: Um Ihre Implementierung gründlicher zu überwachen, können Sie alle Ports auf Ihren Servercomputern sowie die Software-Produkte überwachen, die auf jedem dieser Ports ausgeführt werden.
title: Überwachen von Ports und Programmen
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# Überwachen von Ports und Programmen{#monitoring-ports-and-applications}

Um Ihre Implementierung gründlicher zu überwachen, können Sie alle Ports auf Ihren Servercomputern sowie die Software-Produkte überwachen, die auf jedem dieser Ports ausgeführt werden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Mithilfe einer Anwendung oder eines Skripts können Sie den TCP-Port überwachen, an dem jede Anwendung ausgeführt wird (normalerweise Port 80 oder 443), um sicherzustellen, dass die Anwendung an diesen Port gebunden ist. Dazu fordern Sie von dem zu überwachenden Computer eine Seite mit dem Anwendungsstatus an.

**So fordern Sie die Seite mit dem Anwendungsstatus an**

1. Ändern Sie auf dem Computer, den Sie überwachen möchten, die Zugriffssteuerung, sodass Ihre Überwachungsanwendung oder Ihr Skript auf den Computer zugreifen kann. Anweisungen finden Sie unter [Konfigurieren der Zugriffssteuerung](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Stellen Sie eine Verbindung zu [!DNL https://IP Address/Status/] her, wobei IP-Adresse die IP-Adresse des Computers ist, für den Sie den Status erhalten möchten.

   Beispiel: [!DNL https://127.0.0.1/Status/]

   Der Computer sollte mit einer Serverstatusbeschreibung antworten. Wenn es nicht reagiert, überprüfen Sie Ihre Ereignisprotokolle und wenden Sie sich an die Kundenunterstützung von Adobe.

   Weitere Informationen zu dieser Art von erweitertem Monitoring erhalten Sie von Adobe Consulting Services.
