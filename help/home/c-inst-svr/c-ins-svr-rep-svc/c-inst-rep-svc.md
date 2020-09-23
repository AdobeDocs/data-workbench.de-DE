---
description: Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignis-Daten an einen anderen Insight Server-Computer übertragen.
solution: Analytics
title: Installieren des Replikations-Services
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---


# Installieren des Replikations-Services{#installing-the-replication-service}

Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignis-Daten an einen anderen Insight Server-Computer übertragen.

Normalerweise ist der Computer, auf dem die Daten erfasst und gespeichert werden, für die Ausführung als [!DNL Repeater] Computer konfiguriert. Siehe [Repeater-Funktionen](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Die von der [!DNL Replication Service]Datei konfigurierte [!DNL Replicate.cfg] Datei ermöglicht es einem [!DNL Insight Server] Computer, Daten vom [!DNL Repeater] Computer abzurufen und lokal zu speichern. Die [!DNL Insight Server] Maschine wird als Zielgruppe bezeichnet. Mehrere [!DNL Insight Server] DPUs können eine Verbindung zu einer einzigen herstellen, [!DNL Repeater] um Kopien der Ereignis-Daten zur Einbeziehung in mehrere Datensätze anzufordern.

Sie können die [!DNL Replication Service] in Netzwerkinfrastrukturen mit mehreren Firewalling-Ebenen verwenden, um die Kommunikation zwischen Komponenten, die durch Firewalls voneinander getrennt sind, mit einem Port zu erreichen.

**So installieren Sie die[!DNL Replication Service]**

Die [!DNL Replicate.cfg] Datei sollte im Rahmen Ihrer [!DNL Insight Server] Installation installiert werden. Sie finden die Datei im [!DNL Components] Ordner Ihres [!DNL Insight Server] Installationsordners. Wenn Sie diese Datei nicht haben, wenden Sie sich an die Adobe.
