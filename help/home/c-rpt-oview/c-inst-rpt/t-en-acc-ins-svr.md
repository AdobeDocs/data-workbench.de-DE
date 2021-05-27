---
description: Um eine Verbindung zu einem Data Workbench-Server herzustellen, muss Report Server über die Berechtigung zum Zugriff auf diesen Server verfügen.
title: Ermöglichen des Zugriffs auf den Data Workbench-Server
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Ermöglichen des Zugriffs auf den Data Workbench-Server{#enabling-access-to-the-data-workbench-server}

Um eine Verbindung zu einem Data Workbench-Server herzustellen, muss Report Server über die Berechtigung zum Zugriff auf diesen Server verfügen.

Sie gewähren Zugriff auf einen Data Workbench-Server, indem Sie den allgemeinen Namen von Report Server (wie im digitalen Zertifikat von Report Server zugewiesen) zur Zugriffssteuerungsdatei des Servers hinzufügen.

>[!NOTE]
>
>Bei der Arbeit in einer Clusterumgebung sollte Report Server für den Zugriff auf den Übergeordneten Data Workbench-Server konfiguriert werden, um Synchronisierungsprobleme zu vermeiden. In Data Workbench können Sie mithilfe des Menüelements [!DNL Related Servers] unter [!DNL Servers Manager] Informationen über Verarbeitungsserver in Ihrem Cluster anzeigen. Weitere Informationen zum [!DNL Servers Manager] finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

Im folgenden Verfahren wird beschrieben, wie Sie Report Server manuell zur Zugriffssteuerungsdatei auf einem Data Workbench-Server hinzufügen. Um die Zugriffssteuerungsdatei auf diese Weise zu aktualisieren, benötigen Sie Dateisystemzugriff auf den Computer, auf dem der Data Workbench-Server installiert ist.

Sie können die Zugriffssteuerungsdatei des Servers auch mit [!DNL Server Files Manager] in Data Workbench aktualisieren. Dazu muss Ihr Data Workbench-Client über Administratorrechte auf dem Server verfügen.

Weitere Informationen zum [!DNL Server Files Manager] finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

**So konfigurieren Sie den Zugriff auf einen Data Workbench-Server**

1. Navigieren Sie zum Ordner Zugriffssteuerung in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe).

   Beispiel: [!DNL C:\Adobe\Server\Access Control]

1. Öffnen Sie [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie den [!DNL Report Server AccessGroup] und fügen Sie [!DNL Report Server’s] gemeinsamen Namen zu dieser Gruppe hinzu, wie im folgenden Dateifragment hervorgehoben. (Geben Sie den allgemeinen Namen genau so ein, wie er auf dem digitalen Zertifikat [!DNL Report Server’s] angezeigt wird.)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Speichern Sie die Datei.
