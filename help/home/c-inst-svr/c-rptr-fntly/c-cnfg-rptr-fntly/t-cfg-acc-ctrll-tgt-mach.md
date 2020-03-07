---
description: Target Insight Server-Computer, auf denen der Insight Server Replication Service ausgeführt wird, müssen die Protokolldateien auf diesem Repeater-Server lesen können.
solution: Insight
title: Konfigurieren der Zugriffssteuerung für Zielcomputer
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren der Zugriffssteuerung für Zielcomputer{#configuring-access-control-for-target-machines}

Target Insight Server-Computer, auf denen der Insight Server Replication Service ausgeführt wird, müssen die Protokolldateien auf diesem Repeater-Server lesen können.

Der Zugriff auf die Zielcomputer wird über die [!DNL Access Control.cfg] Datei gewährt.

**So konfigurieren Sie die Zugriffssteuerung für den Zugriff auf Zielcomputer[!DNL Insight Server]**

1. Navigieren Sie zu dem [!DNL Access Control] Ordner, in dem Sie die Funktion zum Wiederholen installiert haben.

   Beispiel: [!DNL D:\Adobe\Repeater\Access Control]

1. Öffnen Sie [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Erstellen Sie eine Zugriffsgruppe für die [!DNL Insight Server] Computer, die auf die Protokolldateien auf diesem Repeater-Server zugreifen müssen. Geben Sie dieser Zugriffsgruppe einen Namen wie &quot;Replizierungsziele&quot;.

       Das folgende Dateifragment zeigt, wie die Zugriffsgruppe aussehen sollte.
       
       ```
       . . .
       6 = AccessGroup:
       Member = Vektor: N items
     0 = string: IP:Machine0IPAddress
     1 = String: IP:Machine1IPAddress
    . . .
       N = Zeichenfolge: IP:MachineNIPAddress
     Name = string: Replizierungsziele
     Schreibgeschützt-Zugriff = Vektor: 1 items
     0 = string: EventDataLocation
     Read-Write-Zugriff = Vektor: 0 Elemente
    . . .
       &quot;
   
   1. Geben Sie im Abschnitt Mitglieder die IP-Adresse für jeden Computer an.
   1. Aktualisieren Sie die Elementanzahl für den Member-Vektor, um die Anzahl der von Ihnen eingefügten Computer-IP-Adressen anzuzeigen.
   1. Geben Sie im Abschnitt &quot;Schreibgeschützter Zugriff&quot;den Speicherort der Ereignisdaten an, auf die die Replizierung den Zugriff zum Ziel hat. Verwenden Sie Schrägstriche in der Pfadspezifikation (/). Der Standardspeicherort ist der [!DNL Logs] Ordner auf dem Repeater-Computer (/Logs/).
   1. Aktualisieren Sie die Elementanzahl für den Vektor mit schreibgeschütztem Zugriff, um die Anzahl der eingefügten Positionen wiederzugeben.

1. Aktualisieren Sie die Anzahl der Zugriffsgruppen im Vektor Zugriffskontrollgruppen oben in der Datei, um die Hinzufügung der neuen Zugriffsgruppe widerzuspiegeln.

   ```
   Access Control Groups = vector: n items
   ```

1. Speichern Sie die Datei.
