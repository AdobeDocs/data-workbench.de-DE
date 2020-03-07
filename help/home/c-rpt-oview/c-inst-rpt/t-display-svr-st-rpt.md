---
description: Die Detaillierte Statusschnittstelle in Data Workbench ist hilfreich, um Fehler oder andere Probleme mit den Data Workbench Server- und Report Server-Computern zu beheben, die Clients von Data Workbench Server sind.
solution: Analytics
title: Berichtsserverstatus anzeigen
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Berichtsserverstatus anzeigen{#displaying-report-server-status}

Die Detaillierte Statusschnittstelle in Data Workbench ist hilfreich, um Fehler oder andere Probleme mit den Data Workbench Server- und Report Server-Computern zu beheben, die Clients von Data Workbench Server sind.

Um den Status des Berichts auf der [!DNL Master Server Detailed Status] Oberfläche anzuzeigen, müssen Sie dem [!DNL Servers] Vektor in der [!DNL Communications.cfg] Datei des Data Workbench-Servers einen Berichtsstatusserver hinzufügen. Im folgenden Verfahren wird beschrieben, wie Sie der [!DNL Communications.cfg] Datei den Berichtsstatusserver hinzufügen:

Weitere Informationen zu [!DNL Detailed Status] Schnittstellen finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

**So fügen Sie eine[!DNL Report Status Server]**

1. Navigieren Sie zum Ordner &quot;Components&quot;in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe).

   Beispiel: [!DNL C:\Adobe\Server\Components]
1. Öffnen Sie [!DNL Communications.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den [!DNL Servers] Vektor und fügen Sie dem Vektor den Berichtsstatusserver hinzu, wie im folgenden Dateifragment hervorgehoben.

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

1. Aktualisieren Sie die Elementanzahl für den [!DNL Servers] Vektor (inkrementieren Sie den Elementwert um 1), wie im Dateifragment im vorherigen Schritt hervorgehoben.
1. Speichern Sie die Datei.
