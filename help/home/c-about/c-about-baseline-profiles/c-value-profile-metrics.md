---
description: 'null'
solution: Analytics
title: Werteprofilmetriken
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Werteprofilmetriken{#value-profile-metrics}

| Metrik | Formel | Ebene | Beschreibung |
|---|---|---|---|
| Konversion | [!DNL-[SitzungenNicht Sitzung_Wert=#0]/Sitzungen] | Sitzung | Der Prozentsatz der Sitzungen, die einen Geschäftswert generiert haben (wie vom Geschäftswertmodell definiert). |
| Anteil des Werts | [!DNL Value/total(Value)] | Sitzung | Der Prozentsatz des Gesamtwerts, der aus dem ausgewählten Satz von Sitzungen generiert wurde. |
| Wert | [!DNL sum(Session_Value, Session)*0.01] | Sitzung | Der generierte Geschäftswert in Dollar (laut Definition des Geschäftswertmodells). |
| Wertereignisse | [!DNL-[SitzungenNicht Sitzung_Wert=#0]] | Sitzung | Die Anzahl der Sitzungen, die einen Geschäftswert generiert haben (wie vom Geschäftswertmodell definiert). |
| Wertereignisse pro Besucher | [!DNL (Value_Events/Visitors) by Visitor] | Besucher | Die durchschnittliche Anzahl der Sitzungen für jeden Besucher, die einen Geschäftswert generiert haben (wie vom Geschäftswertmodell definiert). |
| Wert pro Besucher | [!DNL (Value/Visitors) by Visitor] | Besucher | Der durchschnittliche Geschäftswert, der von jedem Besucher in Dollar generiert wurde. |
