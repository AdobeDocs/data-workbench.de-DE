---
description: Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignisdaten an einen anderen Insight Server-Computer übertragen.
title: Installieren des Replikations-Services
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installieren des Replikations-Services{#installing-the-replication-service}

{{eol}}

Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignisdaten an einen anderen Insight Server-Computer übertragen.

In der Regel ist der Computer, auf dem die Daten erfasst und gespeichert werden, so konfiguriert, dass er als [!DNL Repeater] Maschine. Siehe [Repeater-Funktion](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Die [!DNL Replication Service], der von der [!DNL Replicate.cfg] -Datei, aktiviert eine [!DNL Insight Server] Maschine zum Abrufen von Daten aus der [!DNL Repeater] und speichern Sie es lokal. Die [!DNL Insight Server] Maschine wird als Zielmaschine bezeichnet. Mehrere [!DNL Insight Server] DPUs können eine Verbindung zu einer [!DNL Repeater] , um Kopien der Ereignisdaten zur Aufnahme in mehrere Datensätze anzufordern.

Sie können die [!DNL Replication Service] in Netzwerkinfrastrukturen mit mehreren Ebenen des Firewalls, um eine Kommunikation zwischen einzelnen Ports und einem einzigen Port zwischen Komponenten zu ermöglichen, die durch Firewalls voneinander getrennt sind.

**So installieren Sie die[!DNL Replication Service]**

Die [!DNL Replicate.cfg] sollte als Teil Ihrer [!DNL Insight Server] Installation. Sie finden die Datei im [!DNL Components] Ordner Ihres [!DNL Insight Server] Installationsverzeichnis. Wenn Sie diese Datei nicht haben, wenden Sie sich an die Adobe.
