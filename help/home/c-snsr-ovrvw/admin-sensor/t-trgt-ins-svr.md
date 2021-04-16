---
description: Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielgruppe-Server), müssen Sie die Datei "txlogd.conf"auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.
title: Ändern des Data Workbench Target-Servers
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Ändern des Data Workbench Target-Servers{#changing-the-target-data-workbench-server}

Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielgruppe-Server), müssen Sie die Datei &quot;txlogd.conf&quot;auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.

**So wechseln Sie zur Zielgruppe[!DNL data workbench server]**

1. Beenden Sie sowohl den Originalserver als auch den neuen Zielgruppe-Server für die Zielgruppe.
1. Kopieren Sie die aktuelle [!DNL .vsl]-Datei vom Originalserver der Zielgruppe auf den neuen Zielgruppe-Server. Wenn Sie den neuen Zielgruppe-Server in einem späteren Schritt neu starten, werden alle neuen [!DNL Sensor]-Daten an die aktuelle, vorhandene [!DNL .vsl]-Datei angehängt, anstatt eine neue [!DNL .vsl]-Datei zu erstellen. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie auf dem Originalserver zur Zielgruppe [!DNL \Logs] im Installationsordner [!DNL data workbench server].

   1. Kopieren Sie die aktuellste [!DNL .vsl]-Datei im Ordner.
   1. Navigieren Sie auf dem neuen Zielgruppen-Server zum Ordner [!DNL \Logs] im Installationsordner [!DNL data workbench server] und fügen Sie die [!DNL .vsl]-Datei in diesen Ordner ein.

1. Öffnen Sie auf einem der Webserver, auf denen [!DNL Sensor] installiert ist, die Datei [!DNL txlogd.conf] und bearbeiten Sie sie. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie zum Installationsordner [!DNL Sensor] und öffnen Sie die Datei [!DNL txlogd.conf] in einem Texteditor.

   1. Suchen Sie den Parameter &quot;ServerAddress&quot;und ändern Sie ihn entsprechend der Adresse des neuen Zielgruppe-Servers.
   1. Speichern und schließen Sie die Datei.

1. Wiederholen Sie die Schritte 2-3 auf allen verbleibenden Webservern, auf denen [!DNL Sensor] installiert ist.
1. Starten Sie den Originalserver der Zielgruppe (sofern er noch verwendet werden soll) und den neuen Zielgruppe-Server neu.
1. Die Daten werden an den von Ihnen angegebenen neuen Zielgruppe-Server gesendet.
