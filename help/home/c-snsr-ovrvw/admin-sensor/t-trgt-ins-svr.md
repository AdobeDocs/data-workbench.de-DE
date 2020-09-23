---
description: Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielgruppe-Server), müssen Sie die Datei "txlogd.conf"auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.
solution: Analytics
title: Ändern des Data Workbench Target-Servers
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---


# Ändern des Data Workbench Target-Servers{#changing-the-target-data-workbench-server}

Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielgruppe-Server), müssen Sie die Datei &quot;txlogd.conf&quot;auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.

**So wechseln Sie zur Zielgruppe[!DNL data workbench server]**

1. Beenden Sie sowohl den Originalserver als auch den neuen Zielgruppe-Server für die Zielgruppe.
1. Kopieren Sie die aktuelle [!DNL .vsl] Datei vom Originalserver der Zielgruppe auf den neuen Zielgruppe-Server. Wenn Sie den neuen Zielgruppe-Server in einem späteren Schritt neu starten, werden alle neuen [!DNL Sensor] Daten an die aktuelle, vorhandene [!DNL .vsl] Datei angehängt, anstatt eine neue [!DNL .vsl] Datei zu erstellen. Führen Sie dazu die folgenden Schritte aus:

   1. Suchen Sie auf dem Originalserver der Zielgruppe nach dem [!DNL \Logs] Ordner im [!DNL data workbench server] Installationsordner.

   1. Kopieren Sie die aktuelle [!DNL .vsl] Datei im Ordner.
   1. Navigieren Sie auf dem neuen Zielgruppe-Server zum [!DNL \Logs] Ordner im [!DNL data workbench server] Installationsordner und fügen Sie die [!DNL .vsl] Datei in diesen Ordner ein.

1. Öffnen und bearbeiten Sie auf einem der Webserver, auf denen die [!DNL Sensor] Datei installiert [!DNL txlogd.conf] ist. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie zum [!DNL Sensor] Installationsordner und öffnen Sie die [!DNL txlogd.conf] Datei in einem Texteditor.

   1. Suchen Sie den Parameter &quot;ServerAddress&quot;und ändern Sie ihn entsprechend der Adresse des neuen Zielgruppe-Servers.
   1. Speichern und schließen Sie die Datei.

1. Wiederholen Sie die Schritte 2 bis 3 für alle verbleibenden Webserver, auf denen [!DNL Sensor] installiert ist.
1. Starten Sie den Originalserver der Zielgruppe (sofern er noch verwendet werden soll) und den neuen Zielgruppe-Server neu.
1. Die Daten werden an den von Ihnen angegebenen neuen Zielgruppe-Server gesendet.
