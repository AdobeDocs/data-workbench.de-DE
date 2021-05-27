---
description: Damit Report Portal in die Datenbank schreiben kann, die die zum Authentifizieren von Benutzern erforderlichen Informationen enthält, müssen Sie die entsprechenden Berechtigungen für die Datenbank festlegen.
title: Festlegen von Berechtigungen für die Datenbank
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Festlegen von Berechtigungen für die Datenbank{#set-permissions-for-the-database}

Damit Report Portal in die Datenbank schreiben kann, die die zum Authentifizieren von Benutzern erforderlichen Informationen enthält, müssen Sie die entsprechenden Berechtigungen für die Datenbank festlegen.

1. Navigieren Sie auf dem Computer, auf dem IIS ausgeführt wird, zu \*PortalName*\data\users.mdb.
1. Klicken Sie mit der rechten Maustaste auf die Datei **[!UICONTROL users.mdb]** und wählen Sie **[!UICONTROL Properties]** aus.
1. Klicken Sie auf der Registerkarte [!DNL Security] in Gruppen oder Benutzernamen auf **[!UICONTROL Users]**.
1. Wählen Sie in [!DNL Permission for User] in der Zeile Schreiben die Option **[!UICONTROL Allow]** aus.
1. Klicken Sie auf **[!UICONTROL OK]** und schließen Sie das Dialogfeld [!DNL Properties].
