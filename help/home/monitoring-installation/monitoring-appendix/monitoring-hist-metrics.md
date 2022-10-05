---
description: Im Folgenden werden die Metriken aufgelistet, die im Data Workbench-Profil zur Historischen Überwachung enthalten sind, und wie sie abgeleitet werden.
title: Dimensionen im Data Workbench-Profil zur Historie-Überwachung
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Dimensionen im Data Workbench-Profil zur Historie-Überwachung{#metrics-in-the-data-workbench-historical-monitoring-profile}

{{eol}}

Im Folgenden werden die Metriken aufgelistet, die im Data Workbench-Profil zur Historischen Überwachung enthalten sind, und wie sie abgeleitet werden.

| **Warnungskritiken** | Die Summe der Dimension &quot;Warnungskritisch&quot;für jedes Ping. |
|---|---|
| **Warnhinweis-Downloads** | Die Summe der Dimension &quot;Warnhinweis nach unten&quot;für jedes Ping. |
| **Warnhinweise** | Die Summe der Dimension &quot;Warnung&quot;für jeden Ping. |
| **Alle Komponenten** | Die Anzahl der Pings, bei denen der Erfolg der Komponentenprüfung gleich &quot;1&quot;ist, dividiert durch die Metrik Pings multipliziert mit 100. |
| **Stand der Verspätungsminuten** | Diese Metrik ist die Summe der As Of Delay Minutes für jeden Ping und anschließend durch die Pings-Metrik geteilt. |
| **Blöcke** | Die Summe eines für jeden Block. |
| **Alle blockieren** | Alle Blöcke. |
| **Gesamtkapazität** | Die Kapazitätsgröße Metrik Uhrzeiten 2 plus die Metrik Zeile Kapazität, geteilt durch 3. |
| **Kapazitätszeile** | Die Summe der Dimension &quot;Prozentsatz der Kapazitätszeilen&quot;für jedes Ping dividiert durch die Metrik &quot;Pings&quot;. |
| **Kapazitätsgröße** | Die Summe der Dimension &quot;Prozentsatz der Kapazitätsgröße&quot;für jedes Ping, dividiert durch die Metrik &quot;Pings&quot;. |
| **Kommunikation** | Die Anzahl der Pings, bei denen der Erfolg der Schnellprüfung mit &quot;1&quot;übereinstimmt, dividiert durch die Metrik &quot;Pings&quot;. |
| **Detaillierte Prüfung in Sekunden** | Die Summe der Dimension &quot;Detaillierte Prüfung Sekunden&quot;für jedes Ping, bei dem der Ping-Typ &quot;Server&quot;ist, dividiert durch die Metrik &quot;Pings&quot;. |
| **Dimension GigaBytes** | Die Summe der Dimension-Gigabyte pro Ping, dividiert durch die Pings-Metrik. |
| **Disk &quot;x&quot;** | Die Disk-Metriken werden berechnet, indem sie die Summe ihres verwendeten Festplattenprozentsatzes für jeden Ping, geteilt durch die Pings-Metrik, berechnen. |
| **Geschätzte Sweep-Minutes** | Dies ist die Summe der geschätzten Sweep-Dekasekonds für jeden Ping, geteilt durch die Pings-Metrik, bei der geschätzte Sweep-Dekasekonds größer als null ist, alle geteilt durch 6. |
| **Schneller Input MB pro Minute** | Die Summe der Fast Input MegaBytes pro Minute für jeden Ping geteilt durch die Anzahl der Pings, wenn Fast Input MegaBytes pro Minute größer als null ist. |
| **Schneller Eingabemodus** | Pings, bei denen die Dimension Verarbeitungsmodus gleich &quot;Schnelle Eingabe&quot;dividiert durch Pings ist. |
| **Schnelles Zusammenführen von MegaBytes pro Minute** | Die Summe der Megabyte der schnellen Zusammenführung pro Minute für jedes Ping, dividiert durch die Pings-Metrik. |
| **Schneller Zusammenführungsmodus** | Pings, bei denen der Verarbeitungsmodus gleich einer &quot;schnellen Zusammenführung&quot;geteilt durch die Pings-Metrik ist. |
| **Field GigaBytes** | Die Summe der Feld-Gigabyte-Dimension für jedes Ping dividiert durch die Pings-Metrik. |
| **Load** | Die Summe der Dimension &quot;Load Average&quot;für jedes Ping, dividiert durch die Metrik Pings . |
| **Protokolllesen** | Die Summe der Dimension &quot;Log Reading Processing&quot;für jede Ping, dividiert durch die Metrik Pings , die alle durch 10 dividiert wird. |
| **Speicherseite** | Die Summe des Dateiprozentsatzes der Speicherseitendatei für jedes Ping, dividiert durch die Metrik Pings . |
| **Physikalische Speicher** | Die Summe der Dimension Physikalischer Speicherprozentsatz für jedes Ping, dividiert durch die Metrik Pings . |
| **Speicherabfrage** | Die Summe des Speicherabfrageprozentsatzes für jedes Ping, geteilt durch die Pings-Metrik. |
| **Speicher insgesamt GB** | Die Summe der Dimension &quot;Physikalische MegaBytes insgesamt&quot;des Arbeitsspeichers für jedes Ping, dividiert durch die Metrik &quot;Pings&quot;. |
| **Netzwerkverbindungen** | Dies ist die Summe der Netzwerkverbindungen für jeden Ping dividiert durch die Metrik Pings . |
| **Pings x Gesamtkapazität** | Die Metrik &quot;Pings&quot;multipliziert mit der Metrik Gesamtkapazität . |
| **Umfragelatenz in Millisekunden** | Die Summe der Dimension &quot;Umfrage-Latenzzeit in Sekunden&quot;für jedes Ping, dividiert durch die Metrik &quot;Pings&quot;, multipliziert mit 10. |
| **Abfragenausführung** | Die Summe von einem pro Ping, bei dem die geschätzte Sweep-Dekasekonds größer als &quot;0&quot;ist, dividiert durch die Pings-Metrik, bei der der Ping-Typ gleich &quot;Server&quot;ist. |
| **Schnellprüfung in Sekunden** | Die Summe der Schnellprüfungen in Sekunden für jedes Ping, bei dem der Ping-Typ gleich &quot;Server&quot;ist, dividiert durch die Pings-Metrik. |
| **Ausgabezeilen** | Die Summe der Dimension &quot;Ausgabezeilen&quot;für jeden Ping dividiert durch die Metrik &quot;Pings&quot;, multipliziert mit 10000. |
| **Echtzeitmodus** | Die Anzahl der Pings, bei denen die Dimension &quot;Verarbeitungsmodus&quot;gleich &quot;Echtzeit&quot;ist, dividiert durch die Metrik Pings, alle multipliziert mit 100. |
| **Neuverarbeitungsmodus** | 100 minus der Anzahl der Pings, bei denen der Verarbeitungsmodus &quot;Echtzeit&quot;entspricht, dividiert durch die Pings-Metrik, multipliziert mit 100. |
| **Angehalten** | Die Summe der Dimension &quot;Verarbeitung angehalten&quot;in Insight [Profilstatus](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) Profil. |
| **Temp DB** | Die Summe des Temp DB Space-Prozentsatzes für jedes Ping, geteilt durch die Pings-Metrik. |
| **Umwandlung** | Die Summe des Transformationsprozentsatzes für jedes Ping dividiert durch die Pings-Metrik, die alle durch 10 dividiert wird. |
