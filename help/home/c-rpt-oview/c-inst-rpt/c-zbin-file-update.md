---
description: Für alle Sprachen ist für Report Server 6.0 und höher die Datei "insight.zbin"erforderlich, die in den Berichtsserver-Stammordner kopiert wird.
solution: Analytics
title: Report Server mit einer Sprachdatei aktualisieren (.zbin-Datei)
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Report Server mit einer Sprachdatei aktualisieren (.zbin-Datei){#update-report-server-with-a-language-file-zbin-file}

Für alle Sprachen ist für Report Server 6.0 und höher die Datei &quot;insight.zbin&quot;erforderlich, die in den Berichtsserver-Stammordner kopiert wird.

Aktualisieren Sie die Sprachdateien für den Report Server:

1. Fügen Sie die umbenannte Datei &quot;insight.zbin&quot;dem Stammordner von ReportServer hinzu.
1. Die Berichtsserver-Konfigurationsdatei (reportserver.cfg) erfordert Schrifteinstellungen für Doppelbyte-Sprachen. Beispielsweise erfordert Chinesisch das Hinzufügen von Schriftarten mit SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Ein Parameter für Report Server 6.0 muss in der Befehlszeile für die Lokalisierung übergeben werden, z. B.:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Wenn kein Gebietsschema angegeben ist, wird als Berichtsserver standardmäßig Englisch verwendet.

   Führen Sie die folgenden Schritte aus, um den ReportServer als Dienst mit den Locale-Parametern zu starten:

   1. Starten Sie eine Eingabeaufforderung als Administrator.
   1. Navigieren Sie zum Installationsordner von ReportServer.
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

