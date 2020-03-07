---
description: Die Anweisungen zum Installieren und Konfigurieren einer Insight Server-FSU für administrative Zwecke sind denen zum Installieren und Konfigurieren einer Insight Server-DPU sehr ähnlich.
solution: Insight
title: Installationsverfahren für eine Insight Server-FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installationsverfahren für eine Insight Server-FSU{#installation-procedures-for-an-insight-server-fsu}

Die Anweisungen zum Installieren und Konfigurieren einer Insight Server-FSU für administrative Zwecke sind denen zum Installieren und Konfigurieren einer Insight Server-DPU sehr ähnlich.

Für den *MS System Center-Endpunktschutz* auf Windows 2012-Servern müssen diese ausführbaren Dateien den **ausgeschlossenen Prozessen hinzugefügt werden:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Um ein [!DNL Insight Server] FSU zu installieren und zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

1. Installieren Sie die [!DNL Insight Server] Programmdateien.
1. Installieren Sie das [!DNL Insight Server] digitale Zertifikat.
1. Überprüfen Sie die Anschlusseinstellungen in der [!DNL Communications.cfg] Datei.
1. Ändern Sie die [!DNL Access Control.cfg] Datei, um den administrativen Zugriff [!DNL the Server] von zu ermöglichen [!DNL the Client].
1. Ändern Sie die [!DNL server.address] Datei, um den Netzwerkspeicherort des Servers zu definieren.
1. Legen Sie die Parameter für die Speichernutzung von Windows wie beschrieben fest.
1. Registrieren Sie sich [!DNL Insight Server] wie beschrieben als Windows-Dienst.

   Anweisungen zum Konfigurieren von Datenquellen, Berechtigungen und Kommunikation für ein [!DNL Insight Server] FSU finden Sie im Handbuch zur Konfiguration von *Datasets*.

