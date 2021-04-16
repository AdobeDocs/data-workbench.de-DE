---
description: Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignis-Daten an einen anderen Insight Server-Computer übertragen.
title: Installieren des Replikations-Services
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installieren des Replikations-Services{#installing-the-replication-service}

Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignis-Daten an einen anderen Insight Server-Computer übertragen.

Normalerweise ist der Computer, auf dem die Daten erfasst und gespeichert werden, für die Ausführung als [!DNL Repeater]-Computer konfiguriert. Siehe [Wiederholungsfunktion](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Die von der [!DNL Replicate.cfg]-Datei konfigurierte [!DNL Replication Service]-Maschine ermöglicht es einem [!DNL Insight Server]-Computer, Daten vom [!DNL Repeater]-Computer abzurufen und lokal zu speichern. Die [!DNL Insight Server]-Maschine wird als Zielgruppe bezeichnet. Mehrere [!DNL Insight Server] DPUs können eine Verbindung zu einem einzelnen [!DNL Repeater] herstellen, um Kopien der Ereignis-Daten zur Einbeziehung in mehrere Datensätze anzufordern.

Sie können das [!DNL Replication Service] in Netzwerkinfrastrukturen mit mehreren Firewalling-Ebenen verwenden, um die Kommunikation zwischen Komponenten, die durch Firewalls getrennt sind, mit einem Port zu erreichen.

**So installieren Sie die[!DNL Replication Service]**

Die [!DNL Replicate.cfg]-Datei sollte als Teil der [!DNL Insight Server]-Installation installiert werden. Sie finden die Datei im Ordner [!DNL Components] Ihres [!DNL Insight Server]-Installationsordners. Wenn Sie diese Datei nicht haben, wenden Sie sich an die Adobe.
