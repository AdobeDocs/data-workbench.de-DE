---
description: Schritte zum Aktualisieren des Ordners "Transform".
title: Upgrade von Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Upgrade von Transform{#upgrading-transform}

{{eol}}

Schritte zum Aktualisieren des Ordners &quot;Transform&quot;.

1. Öffnen Sie die [!DNL .zip] -Datei für [!DNL Insight Server] Release-Paket und öffnen Sie die [!DNL Profiles] Ordner innerhalb dieses Ordners [!DNL .zip] -Datei.
1. Kopieren Sie die [!DNL Transform] Ordner in [!DNL Profiles] Ordner in [!DNL Insight Server] Installationsverzeichnis. Dadurch werden die vorhandenen [!DNL Transform] Ordner.
1. Für jedes Profil, das die [!DNL Transform] Profil, bestätigen Sie, dass die [!DNL profile.cfg] hat einen &quot;Transform&quot;-Eintrag im Ordner-Vektor.
Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.
