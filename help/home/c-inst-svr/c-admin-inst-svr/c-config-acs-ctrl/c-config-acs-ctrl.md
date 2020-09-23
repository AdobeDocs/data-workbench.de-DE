---
description: Die Konfigurationsdatei der Zugriffskontrolle, Zugriffskontrolle.cfg, definiert die Zugriffskontrollen, mit denen Insight Server Zugriffsberechtigungen auf Dateien erteilt, die auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung basieren.
solution: Analytics
title: Konfigurieren der Zugangssteuerung
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# Konfigurieren der Zugangssteuerung{#configuring-access-control}

Die Konfigurationsdatei der Zugriffskontrolle, Zugriffskontrolle.cfg, definiert die Zugriffskontrollen, mit denen Insight Server Zugriffsberechtigungen auf Dateien erteilt, die auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung basieren.

**Empfohlene Häufigkeit:** Erforderlich

[!DNL Insight Server] bietet konfigurierbare Zugriffskontrollen zur Verwaltung der Verbindungssicherheit [!DNL Insight Server]. Benutzergruppen identifizieren Zugriffskontrollen, die Verwaltungsfunktionen durchführen dürfen [!DNL Insight].

Wenn Sie Zugriff auf neue Zugriffskontrollen oder Maschinen haben möchten, z. B. wenn Sie einem [!DNL Insight Server] Cluster einen Computer hinzufügen, bearbeiten Sie einfach die Konfigurationsdatei.
