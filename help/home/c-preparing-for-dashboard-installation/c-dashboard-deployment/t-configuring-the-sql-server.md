---
description: Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server gestatten.
solution: Analytics
title: SQL Server konfigurieren
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# SQL Server konfigurieren{#configuring-the-sql-server}

Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server gestatten.

1. Öffnen Sie SQL Management Studio als Administrator.
1. Fügen Sie eine neue Anmeldung hinzu, indem Sie mit der rechten Maustaste klicken **[!UICONTROL Logins]** und **[!UICONTROL New Login]**.
1. Geben Sie den Namen für den vollständigen Anwendungspool ein.

   Standardmäßig wird die Anwendungspool-Identität nach dem Anwendungspool benannt. Wenn Sie `dashboard`diese Option wählen, wird die Identität benannt `IIS AppPool\dashboard`. 1. Wählen Sie die **[!UICONTROL Server Roles]** Rolle aus **[!UICONTROL dbcreator]** und prüfen Sie sie.
1. Click **[!UICONTROL OK]** to add the new user.
