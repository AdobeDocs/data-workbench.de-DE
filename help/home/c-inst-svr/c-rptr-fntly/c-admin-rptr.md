---
description: Die administrativen Aufgaben für die Repeater-Funktion sind denen für Insight Server sehr ähnlich.
solution: Analytics
title: Administration der Repeater-Funktion
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---


# Administration der Repeater-Funktion{#administering-repeater}

Die administrativen Aufgaben für die Repeater-Funktion sind denen für Insight Server sehr ähnlich.

Es gelten die folgenden administrativen Aufgaben: Ausnahmen oder Änderungen, die Sie vornehmen müssen, damit die [!DNL Insight Server] DPU mit dem Repeater-Server verwendet werden kann, werden nach jedem Schritt vermerkt.

* [Erneute Validierung des digitalen Zertifikats](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Feststellen, dass der Service ausgeführt wird](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Suchen Sie in der Liste der Dienste im Bedienfeld &quot;Dienste&quot;nach &quot;Repeater&quot;.

* [Konfigurieren der Zugangssteuerung](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Überwachungsdatentypen](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) Der für den Repeater-Server geltende Datentyp sind Ereignis-, Betriebssystem- und Systemdaten. Wenn Sie den Repeater-Server für die Backup-Datenspeicherung verwenden und mehr Datenspeicherplatz auf dem Computer zur Verfügung stehen müssen, können Sie alle Protokolldateien bis auf den aktuellen Tag auf einen anderen Computer oder ein Datenmedium (Zip-Laufwerk, Band usw.) verschieben, um die Datenspeicherung zu aktivieren. Beim Verschieben der Daten müssen Sie den Repeater-Dienst nicht beenden.

   >[!NOTE]
   >
   >Sie sollten die Integrität der Sicherungskopien Ihrer [!DNL .vsl] Dateien überprüfen, bevor Sie sie aus Repeater löschen.

* [Konfigurieren administrativer Warnhinweise](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Überwachen administrativer Ereignisse](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Überwachen von Auditprotokollen](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Konfigurieren der Kommunikation](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Das Neustarten der Dienstfunktion](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)[!DNL Repeater] ist so ausgelegt, dass sie kontinuierlich ausgeführt wird. Wenn Sie den Computer neu starten, wird der Repeater automatisch neu gestartet. Wenn Sie den Repeater manuell Beginn und stoppen müssen, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun.

