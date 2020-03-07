---
description: Das Profil "Data Workbench-Profilstatus"bietet aktuelle Informationen zum Status des Data Workbench-Servers basierend auf dem Profil und nicht auf Servermetriken oder historischen Daten.
solution: Analytics
title: Data Workbench-Profilstatus-Arbeitsbereich
topic: Data workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench-Profilstatus-Arbeitsbereich{#data-workbench-profile-status-workspace}

Das Profil &quot;Data Workbench-Profilstatus&quot;bietet aktuelle Informationen zum Status des Data Workbench-Servers basierend auf dem Profil und nicht auf Servermetriken oder historischen Daten.

## Datenbasis-Profilstatus {#section-65d1fa393cfd450cbacef3cba823fcc1}

Dieses Statusprofil enthält die aktuellen Daten des Data Workbench-Servers, jedoch nicht in Echtzeit, da der Agent alle zehn Minuten abgefragt wird und die Berichterstellung immer diese zehnminütige Latenz enthält. Genauer gesagt bieten die von diesem Profil erzeugten Datensätze die neueste Beobachtung des Servers vom Agenten, der meist eine Standardabfragezeit von zehn Minuten hat.

Weitere Referenzinformationen zu den im Profil-Status-Profil-Profil von Data Workbench verwendeten Dimensionen finden Sie unter [Insight-Profil-Status-Profil](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Dieser Bericht dient eher der Überwachung von Operationen als von Komponenten oder spezifischen Traffic-Fluktuationen.

![](assets/Status_General_page.png)

Das gibt uns einen Eindruck, wer in welchem Modus ist: Wenn für ein bestimmtes Profil eine hohe schnelle Eingangsrate angezeigt wird, befindet sich dieses Profil im Modus &quot;Schnelle Eingabe&quot;.

Wenn die angehaltene Metrik 1 ist, wird der Server angehalten. Wenn der Wert 0 ist, wird der Server nicht angehalten.

**Protokolllesen bei großen Batch-Lasten**

![](assets/Status_General_stalled_log.png)

