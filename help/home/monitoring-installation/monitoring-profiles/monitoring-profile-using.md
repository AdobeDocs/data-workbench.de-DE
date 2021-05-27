---
description: Das Profil-Status-Profil von Data Workbench bietet aktuelle Informationen zum Server-Status von Data Workbench, die auf dem Profil und nicht auf Servermetriken oder historischen Daten basieren.
title: Data Workbench-Arbeitsbereich zum Profilstatus
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench-Arbeitsbereich zum Profilstatus{#data-workbench-profile-status-workspace}

Das Profil-Status-Profil von Data Workbench bietet aktuelle Informationen zum Server-Status von Data Workbench, die auf dem Profil und nicht auf Servermetriken oder historischen Daten basieren.

## Data Workbench-Profilstatus {#section-65d1fa393cfd450cbacef3cba823fcc1}

Dieses Statusprofil stellt die aktuellen Daten des Data Workbench-Servers bereit, jedoch nicht in Echtzeit, da der Agent alle zehn Minuten abgerufen wird und die Berichterstellung immer diese zehnminütige Latenz enthält. Genauer gesagt bieten die von diesem Profil generierten Datensätze die neueste Beobachtung des Servers vom Agenten, der meist einen standardmäßigen Abrufezeitraum von zehn Minuten hat.

Weitere Referenzinformationen zu den Dimensionen, die im Profil &quot;Profilstatus&quot;von Data Workbench verwendet werden, finden Sie unter [Profil-Statusprofil für Insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Dieser Bericht dient eher der Überwachung von Vorgängen als Komponenten oder spezifischen Traffic-Schwankungen.

![](assets/Status_General_page.png)

Dies gibt uns ein Gefühl, wer in welchem Modus ist: Wenn wir eine hohe Schnelle Eingangsrate für ein bestimmtes Profil sehen, befindet sich dieses Profil im Modus Schnelle Eingabe .

Wenn die Metrik &quot;Angehalten&quot;1 ist, wird der Server angehalten. Wenn der Wert 0 beträgt, wird der Server nicht angehalten.

**Protokolllesung für große Batch-Ladevorgänge**

![](assets/Status_General_stalled_log.png)
