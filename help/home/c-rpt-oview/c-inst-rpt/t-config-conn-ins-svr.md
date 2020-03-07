---
description: Bevor Sie Berichte und Warnungen erstellen können, müssen Sie Report Server konfigurieren, um die Adresse des Insight-Servers anzugeben und die Profile zu identifizieren, über die Sie Berichte erstellen möchten.
solution: Analytics
title: Verbindung zum Insight Server konfigurieren
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verbindung zum Insight Server konfigurieren{#configuring-the-connection-to-the-insight-server}

Bevor Sie Berichte und Warnungen erstellen können, müssen Sie Report Server konfigurieren, um die Adresse des Insight-Servers anzugeben und die Profile zu identifizieren, über die Sie Berichte erstellen möchten.

>[!NOTE]
>
>Bis Sie Report Server wie unten beschrieben konfigurieren, können Sie Report Server nicht erfolgreich ausführen. Wenn Sie versuchen, Report Server mit der nicht konfigurierten Datei auszuführen, die mit dem Programm installiert ist, erzeugt Report Server einen Fehlerstream.

**So konfigurieren Sie Report Server**

1. Navigieren Sie in Windows Explorer zu dem Ordner, in dem Sie Report Server installiert haben.
1. Öffnen Sie die [!DNL ReportServer.cfg] Datei im Editor und ändern Sie die Datei nach Bedarf.

   Das folgende Beispiel [!DNL Report Server.cfg] enthält standardmäßig nur die in der [!DNL Report Server.cfg] Datei enthaltenen Parameter (und hebt die erforderlichen Parametereinstellungen hervor). Wenn Sie den Adobe License Server über einen Proxyserver kontaktieren, müssen Sie den Lizenzvektor und dessen Parameter hinzufügen. Eine ausführliche Beschreibung finden Sie unter [Report Server.cfg-Parameter](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) .

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Speichern und schließen Sie die Datei.
