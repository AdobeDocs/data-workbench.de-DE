---
description: Im Folgenden werden die Metriken aufgelistet, die im Historischen Überwachungsprofil von Data Workbench enthalten sind und wie sie abgeleitet werden.
solution: Analytics
title: Metriken im historischen Überwachungsprofil von Data Workbench
topic: Data workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Metriken im historischen Überwachungsprofil von Data Workbench{#metrics-in-the-data-workbench-historical-monitoring-profile}

Im Folgenden werden die Metriken aufgelistet, die im Historischen Überwachungsprofil von Data Workbench enthalten sind und wie sie abgeleitet werden.

| **Warnungskritiken** | Die Summe der Dimension &quot;Warnungskritisch&quot;für jede Ping. |
|---|---|
| **Warnhinweis-Downloads** | Die Summe der Dimension &quot;Warnhinweis nach unten&quot;für jede Seite. |
| **Warnhinweise** | Die Summe der Warnungsdimension für jede Ping. |
| **Alle Komponenten** | Die Anzahl der Seiten, bei denen der Komponentenprüfungserfolg gleich &quot;1&quot;geteilt durch die mit 100 multiplizierte Pings-Metrik ist. |
| **Ab Verspätungsminuten** | Diese Metrik ist die Summe der Ausführungsminuten pro Ping und anschließend geteilt durch die Pings-Metrik. |
| **Blöcke** | Die Summe von 1 für jeden Block. |
| **Alle blockieren** | Alle Blöcke. |
| **Kapazität insgesamt** | Die Metrik &quot;Kapazitätsgröße&quot;ist 2 Mal plus die Metrik &quot;Kapazitätszeile&quot;geteilt durch 3. |
| **Kapazitätszeile** | Die Summe der Dimension &quot;Prozentsatz der Kapazitätszeile&quot;für jede Ping dividiert durch die Metrik &quot;Pings&quot;. |
| **Kapazitätsgröße** | Die Summe der Dimension &quot;Prozentsatz der Kapazitätsgröße&quot;für jedes Ping, geteilt durch die Metrik &quot;Pings&quot;. |
| **Kommunikation** | Die Anzahl der Seiten, bei denen der Erfolg der Schnellprüfung mit &quot;1&quot;übereinstimmt, geteilt durch die Metrik &quot;Seiten&quot;. |
| **Detaillierte Prüfung in Sekunden** | Die Summe der Dimension &quot;Detaillierte Prüfung (Sekunden)&quot;für jedes Ping, bei dem der Ping-Typ &quot;Server&quot;ist, dividiert durch die Pings-Metrik. |
| **Dimension GigaBytes** | Die Summe der Dimension Gigabytes für jede Ping, dividiert durch die Pings-Metrik. |
| **Disk &quot;x&quot;** | Die Disk-Metriken werden berechnet, indem die Summe des verwendeten Festplattenprozentsatzes für jede Ping-Datei, geteilt durch die Pings-Metrik, berechnet wird. |
| **Geschätzte Sweep-Minuten** | Dies ist die Summe der geschätzten Sweep-Dekaseconds für jeden Ping, geteilt durch die Pings-Metrik, bei der geschätzte Sweep-Dekaseconds größer als null sind, alle geteilt durch 6. |
| **Schnelle Eingabe MB pro Minute** | Die Summe der schnellen Eingabe MegaBytes pro Minute für jedes Ping geteilt durch die Anzahl der Pings, wenn die schnelle Eingabe MegaBytes pro Minute größer als null ist. |
| **Schneller Eingabemodus** | Pings, bei denen die Dimension &quot;Verarbeitungsmodus&quot;gleich &quot;Schnelle Eingabe&quot;geteilt durch Pings ist. |
| **Schnelles Zusammenführen von MegaBytes pro Minute** | Die Summe der Megabyte der schnellen Zusammenführung pro Minute für jedes Ping, geteilt durch die Pings-Metrik. |
| **Schneller Zusammenführungsmodus** | Pings, bei denen der Verarbeitungsmodus gleich &quot;schnelle Zusammenführung&quot;geteilt durch die Pings-Metrik ist. |
| **Feld GigaBytes** | Die Summe der Field-Gigabytes-Dimension für jede Ping-Metrik dividiert durch die Pings-Metrik. |
| **Load** | Die Summe der Dimension &quot;Load Average&quot;für jede Ping, dividiert durch die Metrik &quot;Pings&quot;. |
| **Protokolllesen** | Die Summe der Verarbeitungsdimension für Protokolllesen für jede Ping, dividiert durch die Pings-Metrik, alle dividiert durch 10. |
| **Speicherseite** | Die Summe der Speicherseitendateiprozentsätze für jede Ping, dividiert durch die Pings-Metrik. |
| **Physikalischer Speicher** | Die Summe der Dimension Physikalischer Speicherprozentsatz für jedes Ping, dividiert durch die Metrik &quot;Pings&quot;. |
| **Speicherabfrage** | Die Summe des Speichernabfrageprozentsatzes für jede Ping, geteilt durch die Pings-Metrik. |
| **Speicher insgesamt GB** | Die Summe der Dimension &quot;Physical MegaBytes Total&quot;des Speichers für jedes Ping, geteilt durch die Metrik &quot;Pings&quot;. |
| **Netzwerkverbindungen** | Dies ist die Summe der Netzwerkverbindungen für jede Ping geteilt durch die Pings-Metrik. |
| **Pings x Kapazität insgesamt** | Die Metrik &quot;Pings&quot;multipliziert mit der Metrik &quot;Gesamtkapazität&quot;. |
| **Umfragelatenz in Millisekunden** | Die Summe der Dimension &quot;Umfragelatenz in Zentisekunden&quot;für jedes Ping, dividiert durch die Metrik &quot;Pings&quot;, alle multipliziert mit 10. |
| **Abfrage-Ausführung** | Die Summe von 1 für jede Ping, bei der geschätzte Sweep-Dekaseconds größer als &quot;0&quot;ist, dividiert durch die Pings-Metrik, bei der Ping-Typ gleich &quot;server&quot;ist. |
| **Schnellprüfung in Sekunden** | Die Summe der Schnellprüfungssekunden für jedes Ping, wobei Ping-Typ gleich &quot;Server&quot;ist, geteilt durch die Pings-Metrik. |
| **Ausgabezeilen** | Die Summe der Ausgabezeilendimension für jeden Ping dividiert durch die Pings-Metrik, multipliziert mit 100000. |
| **Echtzeitmodus** | Die Anzahl der Seiten, bei denen die Dimension &quot;Verarbeitungsmodus&quot;gleich &quot;Echtzeit&quot;ist, geteilt durch die Metrik &quot;Seiten&quot;, alle multipliziert mit 100. |
| **Wiederaufbereitungsmodus** | 100 minus die Anzahl der Seiten, bei denen der Verarbeitungsmodus gleich &quot;Echtzeit&quot;geteilt durch die Pings-Metrik ist, multipliziert mit 100. |
| **Unterbrochen** | Die Summe der Dimension &quot;Verarbeitung angehalten&quot;im Insight- [Profilstatus](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) -Profil. |
| **Temp DB** | Die Summe des Temp DB Space-Prozentsatzes für jede Ping, geteilt durch die Pings-Metrik. |
| **Transformation** | Die Summe der Transformationsprozentsätze für jedes Ping dividiert durch die Pings-Metrik, alle dividiert durch 10. |

