---
description: Für alle Sprachen erfordert Report Server 6.0 und höher die Datei "insight.zbin", die in den Stammordner von Report Server kopiert wird.
title: Aktualisieren von Report Server mit einer Sprachdatei (.zbin-Datei)
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 10%

---

# Aktualisieren von Report Server mit einer Sprachdatei (.zbin-Datei){#update-report-server-with-a-language-file-zbin-file}

{{eol}}

Für alle Sprachen erfordert Report Server 6.0 und höher die Datei &quot;insight.zbin&quot;, die in den Stammordner von Report Server kopiert wird.

Aktualisieren Sie die Sprachdateien des Report Server:

1. Fügen Sie die umbenannte Datei &quot;insight.zbin&quot;zum Stammverzeichnis von ReportServer hinzu.
1. Die Report Server-Konfigurationsdatei (reportserver.cfg) erfordert Schrifteinstellungen für Doppelbyte-Sprachen. Chinesisch erfordert beispielsweise das Hinzufügen von Schriftarten mit SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Ein Parameter für Report Server 6.0 muss in der Befehlszeile zur Lokalisierung übergeben werden, z. B.:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Wenn kein Gebietsschema angegeben ist, wird für den Berichtsserver standardmäßig Englisch verwendet.

   Führen Sie die Schritte aus, um den ReportServer als Dienst mit den Locale-Parametern zu starten:

   1. Starten Sie eine Eingabeaufforderung als Administrator.
   1. Navigieren Sie zum Ordner ReportServer-Installation .
   1. Geben Sie den folgenden Befehl ein, um den Dienst zu starten:

      * Englisch: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Für Chinesisch: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. So überprüfen Sie, ob der ReportServer mit den richtigen Parametern ausgeführt wird:

   1. Öffnen Sie Windows Service Manager.
   1. Rechtsklick [!DNL Adobe Insight Report Server - Properties].

   Der Pfad zur ausführbaren Datei enthält die Parameter:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
