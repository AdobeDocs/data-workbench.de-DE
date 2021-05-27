---
description: Die Anweisungen zum Installieren einer Insight Server-FSU und zum Konfigurieren dieser FSU für die administrative Verwendung ähneln denen zum Installieren und Konfigurieren einer Insight Server-DPU.
title: Installationsverfahren für eine Insight Server-FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Installationsverfahren für eine Insight Server-FSU{#installation-procedures-for-an-insight-server-fsu}

Die Anweisungen zum Installieren einer Insight Server-FSU und zum Konfigurieren dieser FSU für die administrative Verwendung ähneln denen zum Installieren und Konfigurieren einer Insight Server-DPU.

Für *MS System Center Endpoint Protection* auf Windows 2012-Servern müssen diese ausführbaren Dateien zu den **Ausgeschlossenen Prozessen hinzugefügt werden:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Um eine [!DNL Insight Server]-FSU zu installieren und zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

1. Installieren Sie die Programmdateien [!DNL Insight Server].
1. Installieren Sie das digitale Zertifikat [!DNL Insight Server].
1. Überprüfen Sie die Port-Einstellungen in der Datei [!DNL Communications.cfg] .
1. Ändern Sie die Datei [!DNL Access Control.cfg], um den Administratorzugriff auf [!DNL the Server] von [!DNL the Client] zu ermöglichen.
1. Ändern Sie die Datei [!DNL server.address], um den Netzwerkspeicherort des Servers zu definieren.
1. Legen Sie die Parameter für die Windows-Speicherauslastung wie beschrieben fest.
1. Registrieren Sie [!DNL Insight Server] als Windows-Dienst wie beschrieben.

   Anweisungen zum Konfigurieren von Datenquellen, Berechtigungen und Kommunikation für eine [!DNL Insight Server]-FSU finden Sie im *Handbuch zur Datensatzkonfiguration*.
