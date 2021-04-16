---
description: Die Konfigurationsdatei der Zugriffskontrolle, Zugriffskontrolle.cfg, definiert die Zugriffskontrollen, mit denen Insight Server Zugriffsberechtigungen auf Dateien erteilt, die auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung basieren.
title: Konfigurieren der Zugangssteuerung
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Konfigurieren der Zugangssteuerung{#configuring-access-control}

Die Konfigurationsdatei der Zugriffskontrolle, Zugriffskontrolle.cfg, definiert die Zugriffskontrollen, mit denen Insight Server Zugriffsberechtigungen auf Dateien erteilt, die auf den Attributen (OU, CN usw.) des Zertifikats der eingehenden Verbindung basieren.

**Empfohlene Häufigkeit:** Nach Bedarf

[!DNL Insight Server] bietet konfigurierbare Zugriffskontrollen zur Verwaltung der Verbindungssicherheit  [!DNL Insight Server]. Benutzergruppen identifizieren Zugriffskontrollen, die Verwaltungsfunktionen über [!DNL Insight] ausführen dürfen.

Wenn Sie Zugriff auf neue Zugriffskontrollen oder neue Rechner bereitstellen müssen, z. B. wenn Sie einem [!DNL Insight Server]-Cluster einen Computer hinzufügen, bearbeiten Sie einfach die Konfigurationsdatei.
