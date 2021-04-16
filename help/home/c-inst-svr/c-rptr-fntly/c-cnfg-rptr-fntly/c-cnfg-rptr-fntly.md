---
description: Mit der Funktion "Repeater"kann eine Insight Server-FSU Sensor-erfasste Ereignis-Daten aus einer oder mehreren Quellen empfangen und die Daten an eine oder mehrere Insight Server-FSUs replizieren, die den Insight ServerReplication Service ausführen.
title: Konfigurieren der Repeater-Funktion
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Konfigurieren der Repeater-Funktion{#configuring-repeater-functionality}

Mit der Funktion &quot;Repeater&quot;kann eine Insight Server-FSU Sensor-erfasste Ereignis-Daten aus einer oder mehreren Quellen empfangen und die Daten an eine oder mehrere Insight Server-FSUs replizieren, die den Insight ServerReplication Service ausführen.

Siehe [Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Diese Funktion ermöglicht die Datenreplikation in redundante Einrichtungen für Disaster Recovery. Die Zielgruppe-Server fungieren als Netzwerkclient und verbinden sich mit dem Quell-FSU, um Kopien der Ereignis-Daten zur Einbeziehung in mehrere Datensätze anzufordern.

Sie können die Funktion zum Wiederholen von Inhalten in Netzwerkinfrastrukturen mit mehreren Firewalling-Ebenen verwenden, um die Kommunikation zwischen Komponenten, die durch Firewalls voneinander getrennt sind, über einen Port zu erreichen.

Informationen zu den Systemanforderungen für die Installation, Konfiguration und den Betrieb von [!DNL Repeater] finden Sie im Dokument *Systemanforderungen*.

Um [!DNL Repeater] zu installieren, müssen Sie die folgenden Schritte ausführen:

* [Konfigurieren einer Insight Server-FSU für Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Konfigurieren der Zugangssteuerung für Target-Maschinen](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Wenn Netzwerk-Firewalls den Zugriff auf [!DNL Repeater] von [!DNL Insight] erlauben, können Sie eine Verbindung wie unter [Erstellen einer Verbindung zwischen Insight und Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118) beschrieben erstellen.
