---
description: Standardmäßig überwacht Insight Server die Ports 80 (HTTP) und 443 (HTTPS).
title: Überprüfen der Port-Einstellungen
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# Überprüfen der Port-Einstellungen{#checking-the-port-settings}

Standardmäßig überwacht Insight Server die Ports 80 (HTTP) und 443 (HTTPS).

Wenn diese Ports bereits von einem anderen Prozess auf dem Computer zugewiesen werden, auf dem Sie [!DNL Insight Server] installiert haben, ändern Sie die [!DNL Insight Server’s]-Anschlusszuweisungen wie folgt.

**So ändern Sie die Portzuweisungen**

1. Navigieren Sie zum Ordner [!DNL Components] im Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Öffnen Sie die Datei [!DNL Communications.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den Port und die SSL-Port-Einträge, wie unten dargestellt:

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

1. Wenn es sich nicht um die Ports handelt, die [!DNL Insight Server] verwenden soll, ändern Sie die Portzuweisungen, speichern und schließen Sie die Datei.
