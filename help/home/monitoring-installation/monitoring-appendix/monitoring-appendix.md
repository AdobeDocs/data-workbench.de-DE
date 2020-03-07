---
description: In diesem Dokument werden die Profile mit ihren Feldern, Dimensionen und Metriken beschrieben, die vom Datenbasis-Überwachungsprofil verwendet werden.
solution: Analytics
title: Datenbasis-Profildimensionen und -Metriken
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datenbasis-Profildimensionen und -Metriken{#data-workbench-profile-dimensions-and-metrics}

In diesem Dokument werden die Profile mit ihren Feldern, Dimensionen und Metriken beschrieben, die vom Datenbasis-Überwachungsprofil verwendet werden.

Zur Überwachung der Data Workbench-Server werden Daten mit einem Skript erfasst, das den Detailstatus analysiert und gleichzeitig spezifische Serverinformationen erfasst. Die Daten des Data Workbench-Servers werden dann an einen Seiten-Tag-Aufruf weitergeleitet, damit der Data Workbench Sensor erfasst und in einer VSL-Datei gespeichert wird.

## Von Data Workbench-Überwachungsprofil verwendete Profile {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Diese Profile bieten Dimensionen und Metriken, mit denen Sie den Serverstatus und Leistungsdaten anzeigen können:

* [Dimensionen im Insight-Profil-Status-Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensionen im Insight Server-Statusprofil](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensionen im Insight Historic-Profil](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Metriken im Historischen Überwachungsprofil von Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Mit den Statusprofilen können Sie die Leistung von Data Workbench aus operativer Perspektive anzeigen. Das Profil **Profilstatus** und das Profil **Serverstatus** erfassen Daten aus den Detailstatus- und den Data Workbench-Servern. Alle erfassten Daten werden zur Verwendung in das `cs-uri-query` Feld eingefügt.

Die **historischen Profile** ermöglichen es Ihnen, die Auswirkungen von Konfigurations- und Hardwareänderungen anhand historischer Daten zu bewerten. Das historische Profil kann am nützlichsten sein, da es Ihnen ermöglicht, die Auswirkungen von Konfigurations- und Hardwareänderungen im Laufe der Zeit zu bewerten.
