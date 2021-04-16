---
description: Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server gestatten.
title: Konfigurieren des SQL-Servers
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Konfigurieren des SQL-Servers{#configuring-the-sql-server}

Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server gestatten.

1. Öffnen Sie SQL Management Studio als Administrator.
1. hinzufügen Sie eine neue Anmeldung, indem Sie mit der rechten Maustaste auf **[!UICONTROL Logins]** klicken und **[!UICONTROL New Login]** auswählen.
1. Geben Sie den Namen für den vollständigen Anwendungspool ein.

   Standardmäßig wird die Anwendungspool-Identität nach dem Anwendungspool benannt. Wenn Sie `dashboard` wählen, wird die Identität `IIS AppPool\dashboard` benannt. 1. Wählen Sie **[!UICONTROL Server Roles]** und überprüfen Sie die Rolle **[!UICONTROL dbcreator]**.
1. Klicken Sie auf **[!UICONTROL OK]**, um den neuen Benutzer hinzuzufügen.
