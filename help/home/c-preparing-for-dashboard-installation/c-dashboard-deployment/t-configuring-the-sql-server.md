---
description: Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server erlauben.
title: Konfigurieren des SQL-Servers
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Konfigurieren des SQL-Servers{#configuring-the-sql-server}

{{eol}}

Bevor das Dashboard ausgeführt werden kann, müssen Sie ihm den Zugriff auf SQL Server erlauben.

1. Öffnen Sie SQL Management Studio als Administrator.
1. Neue Anmeldung durch Rechtsklick hinzufügen **[!UICONTROL Logins]** und auswählen **[!UICONTROL New Login]**.
1. Geben Sie den vollständigen Identitätsnamen des Anwendungspools ein.

   Standardmäßig wird die App-Pool-Identität nach dem Anwendungspool benannt. Wenn Sie `dashboard`eingeben, wird die Identität `IIS AppPool\dashboard`. 1. Wählen Sie **[!UICONTROL Server Roles]** und überprüfen Sie die **[!UICONTROL dbcreator]** Rolle.
1. Klicken **[!UICONTROL OK]** , um den neuen Benutzer hinzuzufügen.
