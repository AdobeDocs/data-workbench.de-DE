---
description: Schritte zum Aktualisieren des Ordners "Transform".
solution: Insight
title: Transform aktualisieren
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Transform aktualisieren{#upgrading-transform}

Schritte zum Aktualisieren des Ordners &quot;Transform&quot;.

1. Öffnen Sie die [!DNL .zip] Datei für das [!DNL Insight Server] Release-Paket und öffnen Sie den [!DNL Profiles] Ordner in dieser [!DNL .zip] Datei.
1. Kopieren Sie den [!DNL Transform] Ordner in den [!DNL Profiles] Ordner im [!DNL Insight Server] Installationsordner. Dadurch wird der vorhandene [!DNL Transform] Ordner überschrieben.
1. Vergewissern Sie sich für jedes Profil, das das [!DNL Transform] Profil erbt, dass die [!DNL profile.cfg] Datei einen &quot;Transform&quot;-Eintrag im Ordner-Vektor enthält.
Die Datenverarbeitung beginnt nach der Synchronisierung des Profils.
