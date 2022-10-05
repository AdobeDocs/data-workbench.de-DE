---
description: Target Insight Server-Computer, die den Insight Server Replication Service ausführen, müssen die Protokolldateien auf diesem Repeater-Server lesen können.
title: Konfigurieren der Zugangssteuerung für Target-Maschinen
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# Konfigurieren der Zugangssteuerung für Target-Maschinen{#configuring-access-control-for-target-machines}

{{eol}}

Target Insight Server-Computer, die den Insight Server Replication Service ausführen, müssen die Protokolldateien auf diesem Repeater-Server lesen können.

Der Zugriff auf die Zielgeräte wird über die [!DNL Access Control.cfg] -Datei.

**So konfigurieren Sie die Zugriffskontrolle für den Zugriff nach Zielgruppen [!DNL Insight Server] Maschinen**

1. Navigieren Sie zum [!DNL Access Control] -Ordner in dem Verzeichnis, in dem Sie die Repeater-Funktion installiert haben.

   Beispiel: [!DNL D:\Adobe\Repeater\Access Control]

1. Öffnen [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Erstellen Sie eine Zugriffsgruppe für die [!DNL Insight Server] Maschinen, die auf die Protokolldateien auf diesem Repeater-Server zugreifen müssen. Geben Sie dieser Zugriffsgruppe einen Namen wie &quot;Replikations-Ziele&quot;.

   Das folgende Dateifragment zeigt, wie die Zugriffsgruppe aussehen sollte.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. Geben Sie im Bereich Mitglieder die IP-Adresse für jeden Computer an.
   1. Aktualisieren Sie die Artikelanzahl für den Vektor &quot;Mitglieder&quot;, um die Anzahl der von Ihnen eingefügten maschinellen IP-Adressen widerzuspiegeln.
   1. Geben Sie im Abschnitt Schreibgeschützter Zugriff den Speicherort der Ereignisdaten an, auf die die Replikation als Ziel für den Zugriff dient. Verwenden Sie Schrägstriche in der Pfadspezifikation (/). Der Standardspeicherort ist die [!DNL Logs] Ordner auf dem Repeater-Computer (/Logs/).
   1. Aktualisieren Sie die Artikelanzahl für den schreibgeschützten Zugriffsvektor, um die Anzahl der von Ihnen eingefügten Speicherorte widerzuspiegeln.

1. Aktualisieren Sie die Anzahl der Zugriffsgruppen im Vektor Zugriffssteuerungsgruppen oben in der Datei, um das Hinzufügen der neuen Zugriffsgruppe widerzuspiegeln.

   ```
   Access Control Groups = vector: n items
   ```

1. Speichern Sie die Datei.
