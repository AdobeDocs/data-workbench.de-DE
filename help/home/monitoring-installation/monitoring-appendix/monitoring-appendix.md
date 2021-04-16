---
description: In diesem Dokument werden die Profil mit ihren Feldern, Dimensionen und Metriken beschrieben, die vom Data Workbench Monitoring Profil verwendet werden.
title: Profildimensionen und Metriken in Data Workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Profildimensionen und Metriken in Data Workbench{#data-workbench-profile-dimensions-and-metrics}

In diesem Dokument werden die Profil mit ihren Feldern, Dimensionen und Metriken beschrieben, die vom Data Workbench Monitoring Profil verwendet werden.

Zur Überwachung der Data Workbench-Server werden Daten mit einem Skript erfasst, das den Detailstatus analysiert und gleichzeitig spezifische Serverinformationen erfasst. Die Daten des Data Workbench-Servers werden dann an einen Seiten-Tag-Aufruf weitergeleitet, damit der Data Workbench Sensor erfasst und in einer VSL Datei gespeichert wird.

## Profile, die vom Data Workbench Monitoring Profil {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Diese Profil bieten Dimensionen und Metriken, mit denen Sie Ansichten von Serverstatus- und Leistungsdaten durchführen können:

* [Dimensionen im Insight Profil Status-Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensionen im Insight Server Status-Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensionen im Insight Historic Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Metriken im Insight Historical Monitoring Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Mit den Status-Profilen können Sie die Leistung von Data Workbench aus operativer Sicht anzeigen. Das Profil **Profil Status** und das Profil **Serverstatus** erfassen Daten aus den Detailstatus- und den Data Workbench-Servern. Alle erfassten Daten werden zur Verwendung in das Feld `cs-uri-query` eingefügt.

Mit den **Historischen Profilen** können Sie die Auswirkungen von Konfigurations- und Hardwareänderungen anhand von Verlaufsdaten bewerten. Das historische Profil kann am nützlichsten sein, da es Ihnen ermöglicht, die Auswirkungen von Konfigurations- und Hardwareänderungen im Laufe der Zeit zu bewerten.
