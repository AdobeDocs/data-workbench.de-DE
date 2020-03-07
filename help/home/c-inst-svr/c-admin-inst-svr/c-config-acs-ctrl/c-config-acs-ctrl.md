---
description: Die Konfigurationsdatei Zugriffssteuerung, Access Control.cfg, definiert die Zugriffskontrollgruppen, mit denen Insight Server Zugriffsberechtigungen für Dateien erteilt, die auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung basieren.
solution: Insight
title: Zugriffssteuerung konfigurieren
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zugriffssteuerung konfigurieren{#configuring-access-control}

Die Konfigurationsdatei Zugriffssteuerung, Access Control.cfg, definiert die Zugriffskontrollgruppen, mit denen Insight Server Zugriffsberechtigungen für Dateien erteilt, die auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung basieren.

**Empfohlene Häufigkeit:** Erforderlich

[!DNL Insight Server] bietet konfigurierbare Zugriffssteuerungsgruppen zur Verwaltung der Sicherheit von Verbindungen zu [!DNL Insight Server]. Zugriffskontrollgruppen identifizieren Benutzer, die Verwaltungsfunktionen ausführen dürfen [!DNL Insight].

Wenn Sie neuen Benutzern oder neuen Computern Zugriff gewähren müssen, z. B. wenn Sie einem [!DNL Insight Server] Cluster einen Computer hinzufügen, bearbeiten Sie einfach die Konfigurationsdatei Zugriffssteuerung.
