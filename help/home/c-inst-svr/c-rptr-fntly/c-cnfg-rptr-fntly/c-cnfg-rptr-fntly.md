---
description: Mit der Repeater-Funktion kann eine Insight Server-FSU Sensor-erfasste Ereignisdaten aus einer oder mehreren Quellen empfangen und die Daten an eine oder mehrere Insight Server-FSUs replizieren, die den Insight ServerReplication Service ausführen.
title: Konfigurieren der Repeater-Funktion
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Konfigurieren der Repeater-Funktion{#configuring-repeater-functionality}

{{eol}}

Mit der Repeater-Funktion kann eine Insight Server-FSU Sensor-erfasste Ereignisdaten aus einer oder mehreren Quellen empfangen und die Daten an eine oder mehrere Insight Server-FSUs replizieren, die den Insight ServerReplication Service ausführen.

Siehe [Replikationsdienst für Insight Server](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Diese Funktion ermöglicht die Datenreplikation an redundante Einrichtungen für Disaster Recovery-Zwecke. Die Zielserver fungieren als Netzwerkclients und verbinden sich mit der Quell-FSU, um Kopien der Ereignisdaten zur Aufnahme in mehrere Datensätze anzufordern.

Sie können die Repeater-Funktion in Netzwerkinfrastrukturen mit mehreren Ebenen von Firewalls verwenden, um die Kommunikation zwischen Komponenten, die durch Firewalls getrennt sind, von einem Port zum nächsten zu erreichen.

Informationen zu den Systemanforderungen für Installation, Konfiguration und Betrieb [!DNL Repeater], siehe *Mindestsystemanforderungen* Dokument.

Installieren [!DNL Repeater]müssen Sie die Schritte ausführen, die für die folgenden beiden Vorgehensweisen aufgelistet sind:

* [Konfigurieren einer Insight Server-FSU für Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Konfigurieren der Zugangssteuerung für Target-Maschinen](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Wenn Netzwerk-Firewalls den Zugriff auf Ihre [!DNL Repeater] von [!DNL Insight], können Sie eine Verbindung wie in [Erstellen einer Verbindung zwischen Insight und Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
