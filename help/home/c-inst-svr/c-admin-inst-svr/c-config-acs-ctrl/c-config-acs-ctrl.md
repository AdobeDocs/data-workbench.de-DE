---
description: Die Konfigurationsdatei Zugriffskontrolle, Access Control.cfg, definiert die Zugriffskontrollgruppen, mit denen Insight Server Dateien basierend auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung Berechtigungen erteilt.
title: Konfigurieren der Zugangssteuerung
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Konfigurieren der Zugangssteuerung{#configuring-access-control}

{{eol}}

Die Konfigurationsdatei Zugriffskontrolle, Access Control.cfg, definiert die Zugriffskontrollgruppen, mit denen Insight Server Dateien basierend auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung Berechtigungen erteilt.

**Empfohlene Häufigkeit:** Bei Bedarf

[!DNL Insight Server] bietet konfigurierbare Zugriffssteuerungsgruppen, um die Sicherheit von Verbindungen zu verwalten [!DNL Insight Server]. Zugriffskontrollgruppen identifizieren Benutzer, die über Administratorfunktionen verfügen [!DNL Insight].

Wenn Sie neuen Benutzern oder neuen Computern Zugriff gewähren müssen, z. B. beim Hinzufügen eines Computers zu einer [!DNL Insight Server] -Cluster, bearbeiten Sie einfach die Konfigurationsdatei Zugriffskontrolle .
