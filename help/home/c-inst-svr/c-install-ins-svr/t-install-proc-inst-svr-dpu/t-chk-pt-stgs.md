---
description: Standardmäßig überwacht Insight Server die Anschlüsse 80 (für HTTP) und 443 (für HTTPS).
title: Überprüfen der Port-Einstellungen
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# Überprüfen der Port-Einstellungen{#checking-the-port-settings}

Standardmäßig überwacht Insight Server die Anschlüsse 80 (für HTTP) und 443 (für HTTPS).

Wenn diese Anschlüsse bereits durch einen anderen Prozess auf dem Computer zugeordnet sind, auf dem Sie [!DNL Insight Server] installiert haben, ändern Sie die Zuweisungen für [!DNL Insight Server’s] mit dem folgenden Verfahren.

**So ändern Sie die Anschlusszuweisungen**

1. Navigieren Sie zum Ordner [!DNL Components] in dem Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Öffnen Sie die Datei [!DNL Communications.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den Anschluss und die SSL-Port-Einträge, wie unten dargestellt:

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. Wenn dies nicht die Anschlüsse sind, die [!DNL Insight Server] verwendet werden sollen, ändern Sie die Anschlusszuweisungen und speichern und schließen Sie die Datei.
