---
description: Wertprofil-Metriken
title: Wertprofil-Metriken
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# Wertprofil-Metriken{#value-profile-metrics}

| Metrik | Formel | Ebene | Beschreibung |
|---|---|---|---|
| Konversion  | `Sessions[not Session_Value=#0]/Sessions` | Sitzung | Der Prozentsatz der Sitzungen, die einen Geschäftswert generiert haben (wie vom Business Value Model definiert). |
| Wertebereich | `Value/total(Value)` | Sitzung | Der Prozentsatz des Gesamtwerts, der aus dem ausgewählten Satz von Sitzungen generiert wurde. |
| Wert | `sum(Session_Value, Session)*0.01` | Sitzung | Der generierte Geschäftswert in Dollar insgesamt (gemäß Definition durch das Geschäftswertmodell). |
| Wertereignisse | `Sessions[not Session_Value=#0]` | Sitzung | Die Anzahl der Sitzungen, die einen Geschäftswert generiert haben (wie vom Business Value Model definiert). |
| Wertereignisse pro Besucher | `(Value_Events/Visitors) by Visitor` | Besucher. | Die durchschnittliche Anzahl von Sitzungen für jeden Besucher, der einen Geschäftswert generiert hat (wie vom Business Value Model definiert). |
| Wert pro Besucher | `(Value/Visitors) by Visitor` | Besucher. | Der durchschnittliche Geschäftswert, der von jedem Besucher in Dollar generiert wurde. |
