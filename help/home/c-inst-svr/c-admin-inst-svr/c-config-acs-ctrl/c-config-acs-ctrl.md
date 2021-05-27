---
description: Die Konfigurationsdatei Zugriffskontrolle, Access Control.cfg, definiert die Zugriffskontrollgruppen, mit denen Insight Server Dateien basierend auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung Berechtigungen erteilt.
title: Konfigurieren der Zugangssteuerung
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Konfigurieren der Zugangssteuerung{#configuring-access-control}

Die Konfigurationsdatei Zugriffskontrolle, Access Control.cfg, definiert die Zugriffskontrollgruppen, mit denen Insight Server Dateien basierend auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung Berechtigungen erteilt.

**Empfohlene Häufigkeit:** Nach Bedarf

[!DNL Insight Server] bietet konfigurierbare Zugriffssteuerungsgruppen, um die Sicherheit von Verbindungen zu zu verwalten  [!DNL Insight Server]. Zugriffskontrollgruppen identifizieren Benutzer, die über [!DNL Insight] Administratorfunktionen ausführen dürfen.

Wenn Sie neuen Benutzern oder neuen Computern Zugriff gewähren müssen, z. B. beim Hinzufügen eines Computers zu einem [!DNL Insight Server]-Cluster, bearbeiten Sie einfach die Konfigurationsdatei Zugriffssteuerung .
