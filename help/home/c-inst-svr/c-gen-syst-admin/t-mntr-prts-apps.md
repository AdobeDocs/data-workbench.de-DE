---
description: Um Ihre Implementierung genauer zu überwachen, können Sie alle Anschlüsse auf Ihren Servercomputern sowie die Softwareprodukte überwachen, die auf jedem dieser Anschlüsse ausgeführt werden.
solution: Analytics
title: Überwachen von Ports und Programmen
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---


# Überwachen von Ports und Programmen{#monitoring-ports-and-applications}

Um Ihre Implementierung genauer zu überwachen, können Sie alle Anschlüsse auf Ihren Servercomputern sowie die Softwareprodukte überwachen, die auf jedem dieser Anschlüsse ausgeführt werden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Mithilfe einer Anwendung oder eines Skripts können Sie den TCP-Anschluss überwachen, an dem jede Anwendung ausgeführt wird (normalerweise Port 80 oder 443), um sicherzustellen, dass die Anwendung an diesen Anschluss gebunden ist. Dazu fordern Sie von dem zu überwachenden Computer eine Seite mit dem Anwendungsstatus an.

**So fordern Sie die Seite mit dem Anwendungsstatus an**

1. Ändern Sie auf dem zu überwachenden Computer die Zugriffskontrollen, damit die Überwachungsanwendung oder das Skript auf den Computer zugreifen kann. Anweisungen hierzu finden Sie unter [Konfigurieren der Zugriffskontrolle](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Verbinden mit [!DNL https://IP Address/Status/], wobei IP-Adresse die IP-Adresse des Computers ist, für den Sie den Status erhalten möchten.

   Beispiel: [!DNL https://127.0.0.1/Status/]

   Der Computer sollte mit einer Serverstatusbeschreibung antworten. Wenn das Ereignis nicht reagiert, überprüfen Sie die Protokolle und wenden Sie sich an den Kundendienst der Adobe.

   Weitere Informationen zu dieser Art der erweiterten Überwachung erhalten Sie bei Adobe Consulting Services.

