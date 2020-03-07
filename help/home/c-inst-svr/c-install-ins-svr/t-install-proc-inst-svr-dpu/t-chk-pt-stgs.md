---
description: Standardmäßig überwacht Insight Server die Anschlüsse 80 (für HTTP) und 443 (für HTTPS).
solution: Insight
title: Überprüfen der Port-Einstellungen
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Überprüfen der Port-Einstellungen{#checking-the-port-settings}

Standardmäßig überwacht Insight Server die Anschlüsse 80 (für HTTP) und 443 (für HTTPS).

Wenn diese Anschlüsse bereits durch einen anderen Prozess auf dem Computer, auf dem Sie installiert haben, zugeordnet sind, ändern Sie [!DNL Insight Server]die [!DNL Insight Server’s] Anschlusszuweisungen wie folgt:

**So ändern Sie die Anschlusszuweisungen**

1. Navigieren Sie zu dem [!DNL Components] Ordner, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Öffnen Sie die [!DNL Communications.cfg] Datei in einem Texteditor wie Notepad.
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

1. Wenn dies nicht die Anschlüsse sind, die Sie verwenden möchten, ändern Sie die Anschlusszuweisungen, speichern und schließen Sie die Datei. [!DNL Insight Server]
