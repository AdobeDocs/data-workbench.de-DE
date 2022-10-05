---
description: Damit Report Portal in die Datenbank schreiben kann, die die zum Authentifizieren von Benutzern erforderlichen Informationen enthält, müssen Sie die entsprechenden Berechtigungen für die Datenbank festlegen.
title: Festlegen von Berechtigungen für die Datenbank
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Festlegen von Berechtigungen für die Datenbank{#set-permissions-for-the-database}

{{eol}}

Damit Report Portal in die Datenbank schreiben kann, die die zum Authentifizieren von Benutzern erforderlichen Informationen enthält, müssen Sie die entsprechenden Berechtigungen für die Datenbank festlegen.

1. Navigieren Sie auf dem Computer, auf dem IIS ausgeführt wird, zu \*PortalName*\data\users.mdb.
1. Klicken Sie mit der rechten Maustaste auf die **[!UICONTROL users.mdb]** Datei und wählen Sie **[!UICONTROL Properties]**.
1. Im [!DNL Security] Registerkarte in Gruppen oder Benutzernamen klicken Sie auf **[!UICONTROL Users]**.
1. In [!DNL Permission for User]Wählen Sie in der Zeile Schreiben die Option **[!UICONTROL Allow]**.
1. Klicken **[!UICONTROL OK]** und schließen Sie die [!DNL Properties] Dialogfeld.
