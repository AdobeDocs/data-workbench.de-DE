---
description: Verwenden Sie das historische Profil der Data Workbench, um zu sehen, wie Konfigurationen, Hardware und andere Änderungen die Leistung, Stabilität und Serverkapazität im Laufe der Zeit beeinflussen.
title: Data Workbench-Arbeitsbereich zur Historie
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Data Workbench-Arbeitsbereich zur Historie{#data-workbench-historic-workspace}

Verwenden Sie das historische Profil der Data Workbench, um zu sehen, wie Konfigurationen, Hardware und andere Änderungen die Leistung, Stabilität und Serverkapazität im Laufe der Zeit beeinflussen.

Das Historic-Profil umfasst einen Profil-basierten Datensatz [Profil Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) und den serverbasierten Datensatz [Serverleistung](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) unter der Registerkarte **[!UICONTROL Performance]**. Hierbei handelt es sich um die am häufigsten verwendeten Datensätze, die im Hinblick auf die Leistung des Data Workbench-Servers in der Vergangenheit angesehen wurden. Darüber hinaus können Sie die Ansichten [Komponenten](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) und [Verarbeitungsmodus](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) durch Auswahl der Registerkarte **[!UICONTROL Up Time]** durchführen.

![](assets/Historic_Performance.png)

Darüber hinaus können Sie die Ansichten [Komponenten](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) und [Verarbeitungsmodus](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) durch Auswahl der Registerkarte **[!UICONTROL Up Time]** durchführen.

Weitere Referenzinformationen zu den im Historischen Profil von Data Workbench verwendeten Dimensionen finden Sie unter [Dimensionen im historischen Profil von Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Profil Performance Workspace {#section-184a86f9de054970bf68515bb9dea85d}

Dieser Datensatz enthält die folgenden relevanten Metriken für die Datenbasisüberwachung.

* Schnelle Eingabe von MegaBytes pro Minute - Metriken, die während der anfänglichen Protokollverarbeitung umfangreiche Dateneingaben anzeigen.
* Schnelles Zusammenführen von MegaBytes pro Minute - Metriken mit Konvertierung.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Um eine echte Leistungsbewertung Ihres Profils durchzuführen, sollten Sie die Rate und nicht die abgelaufene Kalenderzeit betrachten. Die Rate wird als veränderte Werte zwischen den Abfragen alle zehn Minuten gemessen.

## Arbeitsbereich für Serverleistung {#section-5dad5870384b40e094d50173fcd90a09}

Dieser Datensatz überwacht Servermetriken über den Umfang der enthaltenen Profil hinaus und umfasst die folgenden relevanten Servermetriken für die Datenbasis-Überwachung.

* Geschätzte Sweep-Minuten — Geschätzte Abfrage-Auflösungszeit.
* Latenz der Umfrage in Millisekunden — Gibt an, wie viel Software beschäftigt ist, indem gemessen wird, wie lange es dauert, bis eine vollständige Phase der Wartung jeder Komponente durchläuft.

![](assets/Historic_Server_Performance.png)

## Komponentenarbeitsbereich {#section-5be7223abb384784bafe7b37c764ea66}

Dieser Datensatz befindet sich unter der Registerkarte &quot;Zeit&quot;.

![](assets/Up_Time.png)

Der Komponenten-Datensatz umfasst zwei Aspekte für die Komponentengesundheit:

* Kommunikationsmetrik — Hat der Data Workbench-Serverprozess geantwortet?
* Metrik &quot;Alle Komponenten&quot;— Oben auf der Seite &quot;Detaillierter Status&quot;befindet sich eine Liste von Komponenten, die der Host innerhalb der Data Workbench-Serverprozesse wartet. Wenn sich eine Komponente in einem Fehlerstatus befindet, wird sie in der Tabelle &quot;Komponenten&quot;in der Tabelle &quot;Fehler&quot;aufgeführt.

![](assets/Up_Time_components.png)

## Arbeitsbereich für Verarbeitungsmodus {#section-3e1dedb9474e4b4ba513240943e76817}

Dieser Arbeitsbereich befindet sich unter der Registerkarte &quot;Zeit&quot;. In diesem Arbeitsbereich können Sie feststellen, wie viel Zeit in den Modi &quot;Schnelle Eingabe&quot;, &quot;Schnelle Zusammenführung&quot;und &quot;Echtzeit&quot;benötigt wird.

![](assets/Up_Time_Processing_mode.png)

Dieser Datensatz bietet wichtige Merkmale für die Serverlast, z. B. die Identifizierung der Datenladung für

* Wochentag (z. B. schnelle Eingangsrate am Dienstag und Mittwoch),
* Tagesstunde (welcher Prozentsatz des Tages befindet sich im Modus &quot;Schnelle Eingabe&quot;?)
