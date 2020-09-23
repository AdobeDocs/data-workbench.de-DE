---
description: Zielgruppe Insight Server-Computer, auf denen der Insight Server Replication Service ausgeführt wird, müssen die Protokolldateien auf diesem Repeater-Server lesen können.
solution: Analytics
title: Konfigurieren der Zugangssteuerung für Target-Maschinen
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---


# Konfigurieren der Zugangssteuerung für Target-Maschinen{#configuring-access-control-for-target-machines}

Zielgruppe Insight Server-Computer, auf denen der Insight Server Replication Service ausgeführt wird, müssen die Protokolldateien auf diesem Repeater-Server lesen können.

Der Zugriff auf die Zielgruppe wird über die [!DNL Access Control.cfg] Datei gewährt.

**So konfigurieren Sie die Zugriffskontrolle für den Zugriff auf Zielgruppen[!DNL Insight Server]**

1. Navigieren Sie zu dem [!DNL Access Control] Ordner, in dem Sie die Funktion zum Wiederholen installiert haben.

   Beispiel: [!DNL D:\Adobe\Repeater\Access Control]

1. Öffnen Sie [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Erstellen Sie eine Zugriffsgruppe für die [!DNL Insight Server] Computer, die auf die Protokolldateien auf diesem Repeater-Server zugreifen müssen. Geben Sie dieser Zugriffsgruppe einen Namen wie &quot;Replikations-Zielgruppen&quot;.

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

   1. Geben Sie im Abschnitt Mitglieder die IP-Adresse für jeden Computer an.
   1. Aktualisieren Sie die Elementanzahl für den Member-Vektor, um die Anzahl der von Ihnen eingefügten Computer-IP-Adressen anzuzeigen.
   1. Geben Sie im Abschnitt &quot;Schreibgeschützter Zugriff&quot;den Speicherort der Ereignis-Daten an, auf die die Replikationsdaten zugreifen, auf die die Zielgruppen zugreifen. Verwenden Sie Schrägstriche in der Pfadspezifikation (/). Der Standardspeicherort ist der [!DNL Logs] Ordner auf dem Repeater-Computer (/Logs/).
   1. Aktualisieren Sie die Elementanzahl für den Vektor mit schreibgeschütztem Zugriff, um die Anzahl der eingefügten Positionen wiederzugeben.

1. Aktualisieren Sie die Anzahl der Zugriffsgruppen im Zugriffskontrolle Groups-Vektor oben in der Datei, um den Zusatz der neuen Zugriffsgruppe widerzuspiegeln.

   ```
   Access Control Groups = vector: n items
   ```

1. Speichern Sie die Datei.
