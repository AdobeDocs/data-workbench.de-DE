---
description: Die Verwaltungsaufgaben für die Repeater-Funktion sind denen für Insight Server sehr ähnlich.
solution: Insight
title: Administration von Repeater
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Administration von Repeater{#administering-repeater}

Die Verwaltungsaufgaben für die Repeater-Funktion sind denen für Insight Server sehr ähnlich.

Es gelten die folgenden Verwaltungsaufgaben: Ausnahmen oder Änderungen, die Sie vornehmen müssen, damit die [!DNL Insight Server] DPU mit dem Repeater-Server verwendet werden kann, werden nach jedem Schritt vermerkt.

* [Digitales Zertifikat erneut validieren](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Bestätigen, dass der Dienst ausgeführt wird](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Suchen Sie in der Liste der Dienste im Bedienfeld &quot;Dienste&quot;nach &quot;Repeater&quot;.

* [Zugriffssteuerung konfigurieren](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Überwachungsdatentypen](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) Der für den Repeater-Server geltende Datentyp sind Ereignis-, Betriebssystem- und Systemdaten. Wenn Sie den Repeater-Server für den Backup-Speicher verwenden und mehr Datenspeicherplatz auf dem Computer verfügbar sein muss, können Sie alle Protokolldateien bis auf den aktuellen Tag auf einen anderen Computer oder ein Datenspeichermedium (Zip-Laufwerk, Band usw.) verschieben. Beim Verschieben der Daten müssen Sie den Repeater-Dienst nicht beenden.

   >[!NOTE]
   >
   >Sie sollten die Integrität der Sicherungskopien Ihrer [!DNL .vsl] Dateien überprüfen, bevor Sie sie aus Repeater löschen.

* [Administrative Warnungen konfigurieren](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Überwachen von Verwaltungsereignissen](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Prüfprotokolle überwachen](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Konfigurieren von Mitteilungen](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Das Neustarten der Dienstfunktion](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)[!DNL Repeater] ist so ausgelegt, dass sie kontinuierlich ausgeführt wird. Wenn Sie den Computer neu starten, wird der Repeater automatisch neu gestartet. Wenn Sie den Repeater manuell starten und beenden müssen, können Sie dies über das Bedienfeld &quot;Dienste&quot;in Windows tun.

