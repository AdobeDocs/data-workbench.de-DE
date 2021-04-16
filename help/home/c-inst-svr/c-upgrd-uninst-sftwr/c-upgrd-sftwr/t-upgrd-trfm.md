---
description: Schritte zum Aktualisieren des Ordners "Transform".
title: Upgrade von Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Upgrade von Transform{#upgrading-transform}

Schritte zum Aktualisieren des Ordners &quot;Transform&quot;.

1. Öffnen Sie die Datei [!DNL .zip] für das [!DNL Insight Server] Release-Paket und öffnen Sie den Ordner [!DNL Profiles] in dieser [!DNL .zip]-Datei.
1. Kopieren Sie den Ordner [!DNL Transform] in den Ordner [!DNL Profiles] im Installationsordner von [!DNL Insight Server]. Dadurch wird der vorhandene Ordner [!DNL Transform] überschrieben.
1. Vergewissern Sie sich für jedes Profil, das das [!DNL Transform]-Profil erbt, dass die [!DNL profile.cfg]-Datei einen &quot;Transform&quot;-Eintrag im Ordner-Vektor enthält.
Die Datenverarbeitung beginnt nach der Synchronisierung des Profils.
