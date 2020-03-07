---
description: Um eine Verbindung zu einem Data Workbench-Server herzustellen, muss Report Server über die Berechtigung zum Zugriff auf diesen Server verfügen.
solution: Analytics
title: Zugriff auf Data Workbench Server aktivieren
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zugriff auf Data Workbench Server aktivieren{#enabling-access-to-the-data-workbench-server}

Um eine Verbindung zu einem Data Workbench-Server herzustellen, muss Report Server über die Berechtigung zum Zugriff auf diesen Server verfügen.

Sie gewähren Zugriff auf einen Data Workbench-Server, indem Sie der Zugriffssteuerungsdatei des Servers den allgemeinen Namen des Report Server (wie im digitalen Zertifikat des Report Server zugewiesen) hinzufügen.

>[!NOTE]
>
>Beim Arbeiten in einer Clusterumgebung sollte Report Server so konfiguriert sein, dass auf den Master-Data Workbench-Server zugegriffen wird, um Synchronisierungsprobleme zu vermeiden. In Data Workbench können Sie Informationen zu Verarbeitungsservern im Cluster über den [!DNL Related Servers] Menüpunkt im [!DNL Servers Manager]anzeigen. Weitere Informationen zum Thema [!DNL Servers Manager]finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

Im folgenden Verfahren wird beschrieben, wie Sie Report Server manuell zur Zugriffssteuerungsdatei auf einem Data Workbench-Server hinzufügen. Um die Zugriffssteuerungsdatei auf diese Weise zu aktualisieren, müssen Sie über Dateisystemzugriff auf dem Computer verfügen, auf dem der Data Workbench-Server installiert ist.

Sie können die Zugriffssteuerungsdatei des Servers auch mit der in der [!DNL Server Files Manager] Datenbasis aktualisieren. Dazu muss der Data Workbench-Client über Administratorrechte auf dem Server verfügen.

Weitere Informationen zum Thema [!DNL Server Files Manager]finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-Benutzerhandbuchs*.

**So konfigurieren Sie den Zugriff auf einen Data Workbench-Server**

1. Navigieren Sie zum Ordner Zugriffssteuerung in dem Ordner, in dem Sie den Data Workbench-Server installiert haben (InsightServer64.exe).

   Beispiel: [!DNL C:\Adobe\Server\Access Control]

1. Öffnen Sie [!DNL Access Control.cfg] in einem Texteditor wie Notepad.
1. Suchen Sie nach dem Eintrag [!DNL Report Server AccessGroup] und fügen Sie dieser Gruppe einen [!DNL Report Server’s] allgemeinen Namen hinzu, wie im folgenden Dateifragment hervorgehoben. (Geben Sie den allgemeinen Namen genau so ein, wie er auf dem [!DNL Report Server’s] digitalen Zertifikat angezeigt wird.)

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
