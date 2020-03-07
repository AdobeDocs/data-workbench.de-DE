---
description: Standardmäßig schreibt Insight Server seinen Datensatz (temp.db) auf dasselbe Laufwerk wie die Insight Server-Programmdateien.
solution: Insight
title: Speicherort des Datensatzes konfigurieren (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Speicherort des Datensatzes konfigurieren (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Standardmäßig schreibt Insight Server seinen Datensatz (temp.db) auf dasselbe Laufwerk wie die Insight Server-Programmdateien.

Wenn Sie beispielsweise [!DNL Insight Server] auf Laufwerk C installieren, wird der Datensatz in Laufwerk C geschrieben.

Wenn Sie den Datensatz auf einem anderen Laufwerk verwalten möchten oder wenn die zu erfassende Datenmenge die Verwendung mehrerer Laufwerke erfordert, müssen Sie die [!DNL Insight Server] Datei aktualisieren, um anzugeben, wo [!DNL Disk Files.cfg] die [!DNL Insight Server] [!DNL temp.db] Datei geschrieben werden soll.

**So konfigurieren Sie den Speicherort von &quot;temp.db&quot;**

1. Navigieren Sie zu dem [!DNL Components] Ordner, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Öffnen Sie die [!DNL Disk Files.cfg] Datei in einem Texteditor wie Notepad.

   Standardmäßig enthält diese Datei einen einzelnen Eintrag in der Dateistruktur, wie unten dargestellt.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Um den Speicherort von zu ändern, ändern Sie [!DNL temp.db]die Definition der Festplattendateien. Das folgende Beispiel zeigt, wie Sie die Konfiguration bearbeiten, um die [!DNL temp.db] Datei über die Laufwerke C, D und E zu verteilen:

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
   >Beachten Sie die Verwendung der doppelten Schrägstriche in den Dateinamen oben. In [!DNL Insight Server] Konfigurationsdateien ist der umgekehrte Schrägstrich ein Escape-Zeichen. Es wird verwendet, um spezielle Steuerfolgen (z. B. \t für ein Tabulatorzeichen) im Text auszudrücken. Um einen tatsächlichen umgekehrten Schrägstrich darzustellen, müssen Sie den umgekehrten Schrägstrich zweimal eingeben (z. B. \\), um die Escape-Funktion zu überschreiben. Dies gilt nur, wenn Konfigurationsdateien in einem Texteditor wie Notepad bearbeitet werden.

