---
description: Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignisdaten an einen anderen Insight Server-Computer übertragen.
solution: Insight
title: Replikationsdienst installieren
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Replikationsdienst installieren{#installing-the-replication-service}

Mit dem Insight ServerReplication Service können Sie die auf einem Insight Server-Computer erfassten und gespeicherten Ereignisdaten an einen anderen Insight Server-Computer übertragen.

Normalerweise ist der Computer, auf dem die Daten erfasst und gespeichert werden, für die Ausführung als [!DNL Repeater] Computer konfiguriert. Siehe [Repeater-Funktionen](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Die von der [!DNL Replication Service]Datei konfigurierte [!DNL Replicate.cfg] Datei ermöglicht es einem [!DNL Insight Server] Computer, Daten vom [!DNL Repeater] Computer abzurufen und lokal zu speichern. Die [!DNL Insight Server] Maschine wird als Zielmaschine bezeichnet. Mehrere [!DNL Insight Server] DPUs können eine Verbindung zu einer einzigen herstellen, [!DNL Repeater] um Kopien der Ereignisdaten zur Einbeziehung in mehrere Datensätze anzufordern.

Sie können die [!DNL Replication Service] in Netzwerkinfrastrukturen mit mehreren Firewalling-Ebenen verwenden, um die Kommunikation zwischen Komponenten, die durch Firewalls voneinander getrennt sind, mit einem Port zu erreichen.

**So installieren Sie die[!DNL Replication Service]**

Die [!DNL Replicate.cfg] Datei sollte im Rahmen Ihrer [!DNL Insight Server] Installation installiert werden. Sie finden die Datei im [!DNL Components] Ordner Ihres [!DNL Insight Server] Installationsordners. Wenn Sie diese Datei nicht haben, wenden Sie sich an Adobe.
