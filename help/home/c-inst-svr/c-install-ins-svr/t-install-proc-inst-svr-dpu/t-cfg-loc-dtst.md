---
description: Standardmäßig schreibt Insight Server seinen Datensatz (temp.db) auf dasselbe Laufwerk wie die Insight Server-Programmdateien.
title: Konfigurieren des Datensatzstandorts (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Konfigurieren des Datensatzstandorts (temp.db){#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

Standardmäßig schreibt Insight Server seinen Datensatz (temp.db) auf dasselbe Laufwerk wie die Insight Server-Programmdateien.

Wenn Sie beispielsweise [!DNL Insight Server] auf Laufwerk C schreibt er den Datensatz in Laufwerk C.

Wenn Sie möchten [!DNL Insight Server] um den Datensatz auf einem anderen Laufwerk zu verwalten oder wenn die Menge der Daten, die Sie erfassen, die Verwendung mehrerer Laufwerke erfordert, müssen Sie die [!DNL Disk Files.cfg] -Datei an der gewünschten Stelle angeben [!DNL Insight Server] , um [!DNL temp.db] -Datei.

**So konfigurieren Sie den Speicherort von &quot;temp.db&quot;**

1. Navigieren Sie zum [!DNL Components] Ordner im Verzeichnis, in dem Sie installiert haben [!DNL Insight Server].

   Beispiel: [!DNL C:\Adobe\Server\Components]

1. Öffnen Sie die [!DNL Disk Files.cfg] in einem Texteditor wie Notepad.

   Standardmäßig enthält diese Datei einen einzigen Eintrag in der Struktur der Festplattendateien, wie unten dargestellt.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. So ändern Sie den Speicherort von [!DNL temp.db]ändern Sie die Definition der Festplattendateien. Das folgende Beispiel zeigt, wie Sie die Konfiguration so bearbeiten, dass die [!DNL temp.db] Datei über die Laufwerke C, D und E hinweg:

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
   >Beachten Sie die Verwendung der doppelten Backslashes in den oben genannten Dateinamen. In [!DNL Insight Server] Konfigurationsdateien, ist der umgekehrte Schrägstrich ein Escape-Zeichen. Sie wird verwendet, um spezielle Kontrollsequenzen (z. B. \t für ein Tabulatorzeichen) im Text auszudrücken. Um einen tatsächlichen umgekehrten Schrägstrich darzustellen, müssen Sie den umgekehrten Schrägstrich zweimal eingeben (z. B. \\), um die Escape-Funktion zu überschreiben. Dies gilt nur bei der Bearbeitung von Konfigurationsdateien in einem Texteditor wie Notepad.
