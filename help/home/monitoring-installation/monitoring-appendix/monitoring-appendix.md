---
description: In diesem Dokument werden die Profile mit ihren Feldern, Dimensionen und Metriken beschrieben, die vom Data Workbench-Überwachungsprofil verwendet werden.
title: Profildimensionen und Metriken in Data Workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Profildimensionen und Metriken in Data Workbench{#data-workbench-profile-dimensions-and-metrics}

In diesem Dokument werden die Profile mit ihren Feldern, Dimensionen und Metriken beschrieben, die vom Data Workbench-Überwachungsprofil verwendet werden.

Zur Überwachung von Data Workbench-Servern werden Daten mithilfe eines Skripts erfasst, das den Detailstatus analysiert und gleichzeitig bestimmte Serverinformationen erfasst. Die Daten des Data Workbench-Servers werden dann an einen Seiten-Tag-Aufruf übergeben, damit der Data Workbench Sensor Daten erfassen und in einer VSL Datei speichern kann.

## Vom Data Workbench-Überwachungsprofil verwendete Profile {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Diese Profile bieten Dimensionen und Metriken, mit denen Sie Serverstatus- und Leistungsdaten anzeigen können:

* [Dimensionen im Insight-Profil zum Profilstatus](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensionen im Insight Server-Statusprofil](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensionen im Profil &quot;Insight-Historie&quot;](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Metriken im Insight Historical Monitoring-Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Mit den Statusprofilen können Sie die Leistung von Data Workbench aus betrieblicher Sicht anzeigen. Das Profil **Profilstatus** und das Profil **Serverstatus** erfassen Daten aus dem Detaillierten Status und den Data Workbench-Servern. Alle erfassten Daten werden zur Verwendung in das Feld `cs-uri-query` eingefügt.

Die **Historische Profile** ermöglichen es Ihnen, die Auswirkungen von Konfigurations- und Hardwareänderungen mithilfe von historischen Daten zu bewerten. Das Verlaufsprofil kann am nützlichsten sein, da es es Ihnen ermöglicht, die Auswirkungen von Konfigurations- und Hardwareänderungen im Laufe der Zeit zu bewerten.
