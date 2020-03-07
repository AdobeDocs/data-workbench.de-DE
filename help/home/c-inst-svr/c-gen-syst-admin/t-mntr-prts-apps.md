---
description: Um Ihre Implementierung genauer zu überwachen, können Sie alle Anschlüsse auf Ihren Servercomputern sowie die Softwareprodukte überwachen, die auf jedem dieser Anschlüsse ausgeführt werden.
solution: Insight
title: Anschlüsse und Anwendungen überwachen
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Anschlüsse und Anwendungen überwachen{#monitoring-ports-and-applications}

Um Ihre Implementierung genauer zu überwachen, können Sie alle Anschlüsse auf Ihren Servercomputern sowie die Softwareprodukte überwachen, die auf jedem dieser Anschlüsse ausgeführt werden.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Mithilfe einer Anwendung oder eines Skripts können Sie den TCP-Anschluss überwachen, an dem jede Anwendung ausgeführt wird (normalerweise Port 80 oder 443), um sicherzustellen, dass die Anwendung an diesen Anschluss gebunden ist. Dazu fordern Sie von dem zu überwachenden Computer eine Seite mit dem Anwendungsstatus an.

**So fordern Sie die Seite mit dem Anwendungsstatus an**

1. Ändern Sie auf dem zu überwachenden Computer die Zugriffssteuerung, damit Ihre Überwachungsanwendung oder Ihr Skript auf den Computer zugreifen kann. Anweisungen hierzu finden Sie unter [Konfigurieren der Zugriffssteuerung](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Verbinden mit [!DNL https://IP Address/Status/], wobei IP-Adresse die IP-Adresse des Computers ist, für den Sie den Status erhalten möchten.

   Beispiel: [!DNL https://127.0.0.1/Status/]

   Der Computer sollte mit einer Serverstatusbeschreibung antworten. Wenn die Meldung nicht reagiert, überprüfen Sie Ihre Ereignisprotokolle und wenden Sie sich an den Adobe-Kundendienst.

   Weitere Informationen zu dieser Art der erweiterten Überwachung erhalten Sie bei Adobe Consulting Services.

