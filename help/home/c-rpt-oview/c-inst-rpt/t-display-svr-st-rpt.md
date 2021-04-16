---
description: Die Detaillierte Statusschnittstelle in Data Workbench ist hilfreich, um Fehler oder andere Probleme mit Data Workbench Server- und Report Server-Computern zu beheben, die Clients von Data Workbench Server sind.
title: Anzeigen des Report Server-Status
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Anzeigen des Report Server-Status{#displaying-report-server-status}

Die Detaillierte Statusschnittstelle in Data Workbench ist hilfreich, um Fehler oder andere Probleme mit Data Workbench Server- und Report Server-Computern zu beheben, die Clients von Data Workbench Server sind.

Um den Status des Berichts in der [!DNL Master Server Detailed Status]-Schnittstelle Ansicht, müssen Sie einen Berichtsstatusserver zum Vektor [!DNL Servers] in der [!DNL Communications.cfg]- des Data Workbench-Servers hinzufügen. Im folgenden Verfahren wird beschrieben, wie Sie den Berichtsstatusserver zur Datei [!DNL Communications.cfg] hinzufügen:

Weitere Informationen zu [!DNL Detailed Status]-Schnittstellen finden Sie im Kapitel &quot;Administrative Schnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

**So fügen Sie eine[!DNL Report Status Server]**

1. Navigieren Sie zum Ordner &quot;Components&quot;in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe).

   Beispiel: [!DNL C:\Adobe\Server\Components]
1. Öffnen Sie [!DNL Communications.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den Vektor [!DNL Servers] und fügen Sie dem Vektor den Berichtsstatusserver hinzu, wie im folgenden Dateifragment hervorgehoben.

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

1. Aktualisieren Sie die Elementanzahl für den Vektor [!DNL Servers] (inkrementieren Sie den Elementwert um 1), wie im Dateifragment im vorherigen Schritt hervorgehoben.
1. Speichern Sie die Datei.
