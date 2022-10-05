---
description: Bevor Sie Berichte und Warnhinweise generieren können, müssen Sie Report Server konfigurieren, um die Adresse des Insight-Servers anzugeben und die Profile zu identifizieren, für die der Bericht erstellt werden soll.
title: Konfigurieren der Verbindung zu Insight Server
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Konfigurieren der Verbindung zu Insight Server{#configuring-the-connection-to-the-insight-server}

{{eol}}

Bevor Sie Berichte und Warnhinweise generieren können, müssen Sie Report Server konfigurieren, um die Adresse des Insight-Servers anzugeben und die Profile zu identifizieren, für die der Bericht erstellt werden soll.

>[!NOTE]
>
>Bis Sie Report Server wie unten beschrieben konfigurieren, können Sie Report Server nicht erfolgreich ausführen. Wenn Sie versuchen, Report Server mit der nicht konfigurierten Datei auszuführen, die mit dem Programm installiert ist, erzeugt Report Server einen Fehlerstrom.

**So konfigurieren Sie Report Server**

1. Navigieren Sie mit Windows Explorer zu dem Ordner, in dem Sie Report Server installiert haben.
1. Öffnen Sie die [!DNL ReportServer.cfg] -Datei im Editor speichern und die Datei nach Bedarf ändern.

   Das folgende Beispiel [!DNL Report Server.cfg] enthält nur die Parameter, die im [!DNL Report Server.cfg] -Datei (und markiert die erforderlichen Parametereinstellungen). Wenn Sie den Adobe License Server über einen Proxyserver kontaktieren, müssen Sie den Lizenzvektor und dessen Parameter hinzufügen. Siehe [Parameter für Report Server.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) für eine ausführliche Beschreibung.

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
