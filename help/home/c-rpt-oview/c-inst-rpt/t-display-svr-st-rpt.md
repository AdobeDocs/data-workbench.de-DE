---
description: Die detaillierte Statusschnittstelle in Data Workbench ist hilfreich, um Fehler oder andere Probleme mit den Data Workbench Server- und Report Server-Computern zu beheben, die Clients von Data Workbench Server sind.
title: Anzeigen des Report Server-Status
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Anzeigen des Report Server-Status{#displaying-report-server-status}

{{eol}}

Die detaillierte Statusschnittstelle in Data Workbench ist hilfreich, um Fehler oder andere Probleme mit den Data Workbench Server- und Report Server-Computern zu beheben, die Clients von Data Workbench Server sind.

So zeigen Sie den Status des Berichts im [!DNL Master Server Detailed Status] müssen Sie einen Berichtsstatus-Server zum [!DNL Servers] Vektor im Data Workbench-Server [!DNL Communications.cfg] -Datei. Im Folgenden wird beschrieben, wie Sie den Berichtsstatus-Server zum [!DNL Communications.cfg] Datei:

Weitere Informationen finden Sie unter [!DNL Detailed Status] -Schnittstellen, siehe Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuch*.

**So fügen Sie eine[!DNL Report Status Server]**

1. Navigieren Sie zum Ordner &quot;Components&quot;in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe).

   Beispiel: [!DNL C:\Adobe\Server\Components]
1. Öffnen [!DNL Communications.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie die [!DNL Servers] und fügen Sie den Berichtsstatus-Server diesem Vektor hinzu, wie im folgenden Dateifragment hervorgehoben.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Aktualisieren Sie die Anzahl der Elemente für die [!DNL Servers] -Vektor (d. h., inkrementieren Sie den Elementwert um 1), wie im Dateifragment im vorherigen Schritt hervorgehoben.
1. Speichern Sie die Datei.
