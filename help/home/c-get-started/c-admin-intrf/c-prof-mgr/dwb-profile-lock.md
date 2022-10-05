---
description: Die im Profil-Manager angewendete Datei "Internal.cfg"verhindert Änderungen, die von Benutzern an Ihren benutzerdefinierten Profilen durch die Profil-, Dimensionen-, Berichte-, Arbeitsbereichs-, Metrik- und Filtermanager vorgenommen werden.
title: Sperren von Profilen in der Workstation
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 5%

---

# Sperren von Profilen in der Workstation{#locking-profiles-in-the-workstation}

{{eol}}

Die im Profil-Manager angewendete Datei &quot;Internal.cfg&quot;verhindert Änderungen, die von Benutzern an Ihren benutzerdefinierten Profilen durch die Profil-, Dimensionen-, Berichte-, Arbeitsbereichs-, Metrik- und Filtermanager vorgenommen werden.

Sie können verhindern, dass Profildateien bei Verwendung der Manager geändert und überschrieben werden, indem Sie die **[!DNL Internal.cfg]** in Ihr benutzerdefiniertes Profil im Profil-Manager. Diese Konfigurationsdatei verhindert, dass Benutzer mehrere Dateien überschreiben, wenn sie in Managern arbeiten (auf die über die **Admin** > **Profil** Menü).

**Sperren von Profilen im Profil-Manager**

1. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **Admin** > **Profil-Manager**.

1. Im **Profil-Manager**, Rechtsklick **[!DNL Context > Internal.cfg]** und **Lokal machen**.

1. Rechtsklick auf Häkchen in **Benutzer** in einer Spalte speichern `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Hinweis**: Beim Speichern der **[!DNL Internal.cfg]** in ein benutzerdefiniertes Profil im Profil-Manager. Sie können Arbeitsbereiche von der Arbeitsfläche aus weiterhin mit dem **Auf Server speichern** Befehl.
