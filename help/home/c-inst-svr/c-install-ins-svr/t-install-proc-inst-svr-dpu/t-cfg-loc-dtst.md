---
description: Standardmäßig schreibt Insight Server seinen Datensatz (temp.db) auf dasselbe Laufwerk wie die Insight Server-Programm-Dateien.
title: Konfigurieren des Datensatzstandorts (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Konfigurieren des Datensatzstandorts (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Standardmäßig schreibt Insight Server seinen Datensatz (temp.db) auf dasselbe Laufwerk wie die Insight Server-Programm-Dateien.

Wenn Sie beispielsweise [!DNL Insight Server] auf Laufwerk C installieren, wird das Dataset in Laufwerk C geschrieben.

Wenn [!DNL Insight Server] den Datensatz auf einem anderen Laufwerk beibehalten soll oder wenn die zu erfassende Datenmenge die Verwendung mehrerer Laufwerke erfordert, müssen Sie die [!DNL Disk Files.cfg]-Datei aktualisieren, um anzugeben, wo [!DNL Insight Server] die [!DNL temp.db]-Datei schreiben soll.

**So konfigurieren Sie den Speicherort von &quot;temp.db&quot;**

1. Navigieren Sie zum Ordner [!DNL Components] in dem Ordner, in dem Sie [!DNL Insight Server] installiert haben.

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Öffnen Sie die Datei [!DNL Disk Files.cfg] in einem Texteditor wie Notepad.

   Standardmäßig enthält diese Datei einen einzelnen Eintrag in der Dateistruktur, wie unten dargestellt.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Um den Speicherort von [!DNL temp.db] zu ändern, ändern Sie die Definition der Festplattendateien. Das folgende Beispiel zeigt, wie Sie die Konfiguration bearbeiten, um die [!DNL temp.db]-Datei über die Laufwerke C, D und E zu verteilen:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Beachten Sie die Verwendung der Dublette-Backslashes in den Dateinamen oben. In Konfigurationsdateien ist der umgekehrte Schrägstrich ein Escape-Zeichen. [!DNL Insight Server] Es wird verwendet, um spezielle Steuerfolgen (z. B. \t für ein Tabulatorzeichen) im Text auszudrücken. Um einen tatsächlichen umgekehrten Schrägstrich darzustellen, müssen Sie den umgekehrten Schrägstrich zweimal eingeben (z. B. \\), um die Escape-Funktion zu überschreiben. Dies gilt nur, wenn Konfigurationsdateien in einem Texteditor wie Notepad bearbeitet werden.
