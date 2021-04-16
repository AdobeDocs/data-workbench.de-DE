---
description: Das Data Workbench Profil Status-Profil bietet aktuelle Informationen zum Datenbasis-Serverstatus basierend auf dem Profil und nicht auf Servermetriken oder Verlaufsdaten.
title: Data Workbench-Arbeitsbereich zum Profilstatus
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench-Arbeitsbereich zum Profilstatus{#data-workbench-profile-status-workspace}

Das Data Workbench Profil Status-Profil bietet aktuelle Informationen zum Datenbasis-Serverstatus basierend auf dem Profil und nicht auf Servermetriken oder Verlaufsdaten.

## Status des Data Workbench-Profils {#section-65d1fa393cfd450cbacef3cba823fcc1}

Dieses Profil stellt die Daten des Data Workbench-Servers bereit, die aktuell sind, jedoch nicht in Echtzeit, da der Agent alle zehn Minuten abgefragt wird und Berichte immer diese zehnminütige Latenz aufweist. Genauer gesagt bieten die von diesem Profil generierten Datensätze die neueste Serverbeobachtung vom Agenten, der meist eine Standardabfragezeit von zehn Minuten hat.

Weitere Referenzinformationen zu den im Data Workbench Profil Status-Profil verwendeten Dimensionen finden Sie unter [Insight Profil Status Profil](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Dieser Bericht dient eher der Überwachung von Operationen als von Komponenten oder spezifischen Traffic-Fluktuationen.

![](assets/Status_General_page.png)

Das gibt uns einen Eindruck, wer in welchem Modus ist: Wenn für ein bestimmtes Profil eine hohe schnelle Eingangsrate angezeigt wird, befindet sich dieses Profil im Modus &quot;Schnelle Eingabe&quot;.

Wenn die angehaltene Metrik 1 ist, wird der Server angehalten. Wenn der Wert 0 ist, wird der Server nicht angehalten.

**Protokolllesen bei großen Batch-Lasten**

![](assets/Status_General_stalled_log.png)
