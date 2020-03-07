---
description: Die Datei Internal.cfg, die im Profil-Manager angewendet wird, verhindert, dass Benutzer Ihre benutzerdefinierten Profile durch die Profile-, Dimensions-, Berichte-, Arbeitsflächen-, Metriken- und Filtermanager ändern.
title: Sperren von Profilen in der Workstation
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sperren von Profilen in der Workstation{#locking-profiles-in-the-workstation}

Die Datei Internal.cfg, die im Profil-Manager angewendet wird, verhindert, dass Benutzer Ihre benutzerdefinierten Profile durch die Profile-, Dimensions-, Berichte-, Arbeitsflächen-, Metriken- und Filtermanager ändern.

Sie können verhindern, dass Profildateien geändert und überschrieben werden, wenn Sie die Manager verwenden, indem Sie die **[!DNL Internal.cfg]** Datei in Ihrem benutzerdefinierten Profil im Profil-Manager speichern. Diese Konfigurationsdatei verhindert, dass Benutzer mehrere Dateien überschreiben, wenn sie in Managern arbeiten (Zugriff über das Menü **Admin** > **Profil** ).

**Sperren von Profilen im Profil-Manager**

1. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **Admin** > **Profilmanager**.

1. Klicken Sie im **Profil-Manager** mit der rechten Maustaste **[!DNL Context > Internal.cfg]** und **wählen Sie &quot;Lokal**&quot;.

1. Klicken Sie mit der rechten Maustaste auf das Kontrollkästchen in der Spalte **Benutzer** und speichern Sie es in einem `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Hinweis**: Nur Änderungen an Profildateien durch die Manager werden beim Speichern des Profils **[!DNL Internal.cfg]** in einem benutzerdefinierten Profil im Profil-Manager verhindert. Mit dem Befehl &quot;Auf Server **speichern** &quot;können Sie Arbeitsflächen weiterhin auf dem Server speichern.
