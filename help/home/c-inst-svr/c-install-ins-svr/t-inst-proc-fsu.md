---
description: Die Anweisungen zum Installieren und Konfigurieren einer Insight Server-FSU für administrative Zwecke sind denen zum Installieren und Konfigurieren einer Insight Server-DPU sehr ähnlich.
solution: Analytics
title: Installationsverfahren für eine Insight Server-FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---


# Installationsverfahren für eine Insight Server-FSU{#installation-procedures-for-an-insight-server-fsu}

Die Anweisungen zum Installieren und Konfigurieren einer Insight Server-FSU für administrative Zwecke sind denen zum Installieren und Konfigurieren einer Insight Server-DPU sehr ähnlich.

Für den *MS System Center-Endpunktschutz* auf Windows 2012-Servern müssen diese ausführbaren Dateien den **ausgeschlossenen Prozessen hinzugefügt werden:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Um ein [!DNL Insight Server] FSU zu installieren und zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

1. Installieren Sie die [!DNL Insight Server] Programm-Dateien.
1. Installieren Sie das [!DNL Insight Server] digitale Zertifikat.
1. Überprüfen Sie die Anschlusseinstellungen in der [!DNL Communications.cfg] Datei.
1. Ändern Sie die [!DNL Access Control.cfg] Datei, um den administrativen Zugriff [!DNL the Server] von zu ermöglichen [!DNL the Client].
1. Ändern Sie die [!DNL server.address] Datei, um den Netzwerkspeicherort des Servers zu definieren.
1. Legen Sie die Parameter für die Speichernutzung von Windows wie beschrieben fest.
1. Registrieren Sie sich [!DNL Insight Server] wie beschrieben als Windows-Dienst.

   Anweisungen zum Konfigurieren von Datenquellen, Berechtigungen und Kommunikation für ein [!DNL Insight Server] FSU finden Sie im Handbuch zur Konfiguration von *Datasets*.

