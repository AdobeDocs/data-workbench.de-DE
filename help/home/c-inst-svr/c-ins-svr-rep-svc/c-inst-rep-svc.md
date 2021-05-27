---
description: Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignisdaten an einen anderen Insight Server-Computer übertragen.
title: Installieren des Replikations-Services
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installieren des Replikations-Services{#installing-the-replication-service}

Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignisdaten an einen anderen Insight Server-Computer übertragen.

In der Regel ist der Computer, auf dem die Daten erfasst und gespeichert werden, so konfiguriert, dass er als [!DNL Repeater]-Computer ausgeführt wird. Siehe [Repeater-Funktion](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Die [!DNL Replication Service], die von der [!DNL Replicate.cfg]-Datei konfiguriert wird, ermöglicht einem [!DNL Insight Server]-Computer, Daten vom [!DNL Repeater]-Computer abzurufen und lokal zu speichern. Die Maschine [!DNL Insight Server] wird als Zielmaschine bezeichnet. Mehrere [!DNL Insight Server] DPUs können eine Verbindung zu einem einzelnen [!DNL Repeater] herstellen, um Kopien der Ereignisdaten zur Einbeziehung in mehrere Datensätze anzufordern.

Sie können das [!DNL Replication Service] in Netzwerkinfrastrukturen mit mehreren Ebenen von Firewalls verwenden, um eine Kommunikation zwischen einzelnen Ports und einem einzelnen Port zwischen Komponenten zu erreichen, die durch Firewalls getrennt sind.

**So installieren Sie die[!DNL Replication Service]**

Die [!DNL Replicate.cfg]-Datei sollte im Rahmen Ihrer [!DNL Insight Server]-Installation installiert werden. Sie finden die Datei im Ordner [!DNL Components] Ihres [!DNL Insight Server] -Installationsordners. Wenn Sie diese Datei nicht haben, wenden Sie sich an die Adobe.
