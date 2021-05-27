---
description: Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server erlauben.
title: Konfigurieren des SQL-Servers
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Konfigurieren des SQL-Servers{#configuring-the-sql-server}

Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server erlauben.

1. Öffnen Sie SQL Management Studio als Administrator.
1. Fügen Sie eine neue Anmeldung hinzu, indem Sie mit der rechten Maustaste auf **[!UICONTROL Logins]** klicken und **[!UICONTROL New Login]** auswählen.
1. Geben Sie den vollständigen Identitätsnamen des Anwendungspools ein.

   Standardmäßig wird die App-Pool-Identität nach dem Anwendungspool benannt. Wenn Sie `dashboard` auswählen, erhält die Identität den Namen `IIS AppPool\dashboard`. 1. Wählen Sie **[!UICONTROL Server Roles]** aus und überprüfen Sie die Rolle **[!UICONTROL dbcreator]** .
1. Klicken Sie auf **[!UICONTROL OK]** , um den neuen Benutzer hinzuzufügen.
