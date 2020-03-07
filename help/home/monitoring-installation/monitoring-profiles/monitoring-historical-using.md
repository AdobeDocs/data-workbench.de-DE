---
description: Verwenden Sie das historische Profil der Data Workbench, um zu sehen, wie Konfigurationen, Hardware und andere Änderungen die Leistung, Stabilität und Serverkapazität im Laufe der Zeit beeinflussen.
solution: Analytics
title: Data Workbench Historic Workspace
topic: Data workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench Historic Workspace{#data-workbench-historic-workspace}

Verwenden Sie das historische Profil der Data Workbench, um zu sehen, wie Konfigurationen, Hardware und andere Änderungen die Leistung, Stabilität und Serverkapazität im Laufe der Zeit beeinflussen.

Das historische Profil enthält einen profilbasierten [Profilleistungsdataset](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) und den serverbasierten [Serverleistungsdataset](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) unter der **[!UICONTROL Performance]** Registerkarte. Hierbei handelt es sich um die am häufigsten verwendeten Datensätze, die im Hinblick auf die Leistung des Data Workbench-Servers in der Vergangenheit angesehen wurden. Darüber hinaus können Sie die [Komponenten](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) und den [Verarbeitungsmodus](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) anzeigen, indem Sie auf die **[!UICONTROL Up Time]** Registerkarte klicken.

![](assets/Historic_Performance.png)

Darüber hinaus können Sie die [Komponenten](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) und den [Verarbeitungsmodus](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) anzeigen, indem Sie auf die **[!UICONTROL Up Time]** Registerkarte klicken.

Weitere Referenzinformationen zu den im Historischen Profil von Data Workbench verwendeten Dimensionen finden Sie unter [Dimensionen im historischen Profil von Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Arbeitsbereich &quot;Profilleistung&quot; {#section-184a86f9de054970bf68515bb9dea85d}

Dieser Datensatz enthält die folgenden relevanten Metriken für die Datenbasisüberwachung.

* Schnelle Eingabe von MegaBytes pro Minute - Metriken, die während der anfänglichen Protokollverarbeitung umfangreiche Dateneingaben anzeigen.
* Schnelles Zusammenführen von MegaBytes pro Minute - Metriken mit Konvertierung.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Um eine echte Leistungsbewertung Ihres Profils durchzuführen, sollten Sie die Rate und nicht die abgelaufene Kalenderzeit betrachten. Die Rate wird als veränderte Werte zwischen den Abfragen alle zehn Minuten gemessen.

## Arbeitsbereich &quot;Serverleistung&quot; {#section-5dad5870384b40e094d50173fcd90a09}

Dieser Datensatz überwacht Servermetriken über den Umfang der enthaltenen Profile hinaus und umfasst die folgenden relevanten Servermetriken für die Datenbasis-Überwachung.

* Geschätzte Sweep-Minuten — Geschätzte Abfrageauflösungszeit.
* Latenz der Umfrage in Millisekunden — Gibt an, wie viel Software beschäftigt ist, indem gemessen wird, wie lange es dauert, bis eine vollständige Phase der Wartung jeder Komponente durchläuft.

![](assets/Historic_Server_Performance.png)

## Komponentenarbeitsbereich {#section-5be7223abb384784bafe7b37c764ea66}

Dieser Datensatz befindet sich unter der Registerkarte &quot;Zeit&quot;.

![](assets/Up_Time.png)

Der Komponenten-Datensatz umfasst zwei Aspekte für die Komponentengesundheit:

* Kommunikationsmetrik — Hat der Data Workbench-Serverprozess geantwortet?
* Metrik &quot;Alle Komponenten&quot;— Oben auf der Seite &quot;Detaillierter Status&quot;befindet sich eine Liste der Komponenten, die der Host in den Data Workbench-Serverprozessen wartet. Wenn sich eine Komponente in einem Fehlerstatus befindet, wird sie in der Tabelle &quot;Komponenten&quot;in der Tabelle &quot;Fehler&quot;aufgeführt.

![](assets/Up_Time_components.png)

## Arbeitsbereich &quot;Verarbeitungsmodus&quot; {#section-3e1dedb9474e4b4ba513240943e76817}

Dieser Arbeitsbereich befindet sich unter der Registerkarte &quot;Zeit&quot;. In diesem Arbeitsbereich können Sie feststellen, wie viel Zeit in den Modi &quot;Schnelle Eingabe&quot;, &quot;Schnelle Zusammenführung&quot;und &quot;Echtzeit&quot;benötigt wird.

![](assets/Up_Time_Processing_mode.png)

Dieser Datensatz bietet wichtige Merkmale für die Serverlast, z. B. die Identifizierung der Datenladung für

* Wochentag (z. B. schnelle Eingangsrate am Dienstag und Mittwoch),
* Tagesstunde (welcher Prozentsatz des Tages befindet sich im Modus &quot;Schnelle Eingabe&quot;?)

