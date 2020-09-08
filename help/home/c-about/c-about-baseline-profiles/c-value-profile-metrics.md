---
description: 'null'
solution: Analytics
title: Wertprofil-Metriken
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# Wertprofil-Metriken{#value-profile-metrics}

| Metrik | Formel | Ebene | Beschreibung |
|---|---|---|---|
| Konversion | `Sessions[not Session_Value=#0]/Sessions` | Sitzung | Der Prozentsatz der Sitzungen, die einen Geschäftswert generiert haben (wie vom Geschäftswertmodell definiert). |
| Anteil des Werts | `Value/total(Value)` | Sitzung | Der Prozentsatz des Gesamtwerts, der aus dem ausgewählten Satz von Sitzungen generiert wurde. |
| Wert | `sum(Session_Value, Session)*0.01` | Sitzung | Der generierte Geschäftswert in Dollar (laut Definition des Geschäftswertmodells). |
| Ereignis | `Sessions[not Session_Value=#0]` | Sitzung | Die Anzahl der Sitzungen, die einen Geschäftswert generiert haben (wie vom Geschäftswertmodell definiert). |
| Ereignis pro Besucher | `(Value_Events/Visitors) by Visitor` | Besucher | Die durchschnittliche Anzahl der Sitzungen für jeden Besucher, der einen Geschäftswert generiert hat (wie vom Geschäftswertmodell definiert). |
| Wert pro Besucher | `(Value/Visitors) by Visitor` | Besucher | Der durchschnittliche Geschäftswert, der von jedem Besucher in Dollar generiert wurde. |
