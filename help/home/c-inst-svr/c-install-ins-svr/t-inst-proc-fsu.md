---
description: Die Anweisungen zum Installieren einer Insight Server-FSU und zum Konfigurieren dieser FSU für die administrative Verwendung ähneln denen zum Installieren und Konfigurieren einer Insight Server-DPU.
title: Installationsverfahren für eine Insight Server-FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Installationsverfahren für eine Insight Server-FSU{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

Die Anweisungen zum Installieren einer Insight Server-FSU und zum Konfigurieren dieser FSU für die administrative Verwendung ähneln denen zum Installieren und Konfigurieren einer Insight Server-DPU.

Für *MS System Center Endpunktschutz* Auf Windows 2012-Servern müssen diese ausführbaren Dateien zum **Ausgeschlossene Prozesse:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

So installieren und konfigurieren Sie eine [!DNL Insight Server] FSU, müssen Sie die folgenden Aufgaben ausführen:

1. Installieren Sie die [!DNL Insight Server] Programmdateien.
1. Installieren Sie die [!DNL Insight Server] digitales Zertifikat.
1. Überprüfen Sie die Port-Einstellungen in der [!DNL Communications.cfg] -Datei.
1. Ändern Sie die [!DNL Access Control.cfg] -Datei, um Administratorzugriff zu ermöglichen [!DNL the Server] von [!DNL the Client].
1. Ändern Sie die [!DNL server.address] -Datei, um den Netzwerkspeicherort des Servers zu definieren.
1. Legen Sie die Parameter für die Windows-Speicherauslastung wie beschrieben fest.
1. registrieren [!DNL Insight Server] als Windows-Dienst wie beschrieben.

   Anweisungen zum Konfigurieren von Datenquellen, Berechtigungen und Mitteilungen für eine [!DNL Insight Server] FSU, siehe *Anleitung zur Datensatzkonfiguration*.
