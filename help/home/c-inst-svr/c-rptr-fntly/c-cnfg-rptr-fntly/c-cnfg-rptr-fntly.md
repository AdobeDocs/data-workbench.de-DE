---
description: Die Funktion "Repeater"ermöglicht es einer Insight Server-FSU, von Sensor erfasste Ereignisdaten aus einer oder mehreren Quellen zu empfangen und die Daten an eine oder mehrere Insight Server-FSUs zu replizieren, die den Insight ServerReplication Service ausführen.
solution: Insight
title: Konfigurieren der Wiederholungsfunktion
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren der Wiederholungsfunktion{#configuring-repeater-functionality}

Die Funktion &quot;Repeater&quot;ermöglicht es einer Insight Server-FSU, von Sensor erfasste Ereignisdaten aus einer oder mehreren Quellen zu empfangen und die Daten an eine oder mehrere Insight Server-FSUs zu replizieren, die den Insight ServerReplication Service ausführen.

Siehe [Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Diese Funktion ermöglicht die Datenreplikation in redundante Einrichtungen für Disaster Recovery. Die Zielserver fungieren als Netzwerkclient und verbinden sich mit der Quell-FSU, um Kopien der Ereignisdaten zur Einbeziehung in mehrere Datensätze anzufordern.

Sie können die Funktion zum Wiederholen von Inhalten in Netzwerkinfrastrukturen mit mehreren Firewalling-Ebenen verwenden, um die Kommunikation zwischen Komponenten, die durch Firewalls voneinander getrennt sind, über einen Port zu erreichen.

Informationen zu den Systemanforderungen für Installation, Konfiguration und Betrieb [!DNL Repeater]finden Sie im Dokument *Mindestsystemanforderungen* .

Zur Installation [!DNL Repeater]müssen Sie die folgenden Schritte ausführen:

* [Konfigurieren einer Insight Server-FSU für Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Konfigurieren der Zugriffssteuerung für Zielcomputer](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Wenn Netzwerk-Firewalls den Zugriff auf Ihre Daten [!DNL Repeater] von [!DNL Insight]aus zulassen, können Sie eine Verbindung erstellen, wie unter [Erstellen einer Verbindung zwischen Insight und Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)beschrieben.
