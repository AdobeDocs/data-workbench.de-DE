---
description: Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielserver), müssen Sie die Datei "txlogd.conf"auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.
title: Ändern des Data Workbench Target-Servers
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Ändern des Data Workbench Target-Servers{#changing-the-target-data-workbench-server}

Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielserver), müssen Sie die Datei &quot;txlogd.conf&quot;auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.

**So ändern Sie die Zielgruppe[!DNL data workbench server]**

1. Beenden Sie sowohl den ursprünglichen Zielserver als auch den neuen Zielserver.
1. Kopieren Sie die aktuellste [!DNL .vsl]-Datei vom ursprünglichen Zielserver auf den neuen Zielserver. Wenn Sie den neuen Zielserver in einem späteren Schritt neu starten, werden alle neuen [!DNL Sensor]-Daten an die aktuelle, vorhandene [!DNL .vsl]-Datei angehängt, anstatt eine neue [!DNL .vsl]-Datei zu erstellen. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie auf dem ursprünglichen Zielserver zum Ordner [!DNL \Logs] im Installationsverzeichnis [!DNL data workbench server].

   1. Kopieren Sie die aktuellste [!DNL .vsl]-Datei im Ordner .
   1. Navigieren Sie auf dem neuen Zielserver zum Ordner [!DNL \Logs] im Installationsverzeichnis [!DNL data workbench server] und fügen Sie die Datei [!DNL .vsl] in diesen Ordner ein.

1. Öffnen und bearbeiten Sie auf einem der Webserver, auf dem [!DNL Sensor] installiert ist, die Datei [!DNL txlogd.conf]. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie zum Installationsverzeichnis [!DNL Sensor] und öffnen Sie die Datei [!DNL txlogd.conf] in einem Texteditor.

   1. Suchen Sie den Parameter ServerAddress und ändern Sie ihn entsprechend der Adresse des neuen Zielservers.
   1. Speichern und schließen Sie die Datei.

1. Wiederholen Sie die Schritte 2-3 für alle anderen Webserver, auf denen [!DNL Sensor] installiert ist.
1. Starten Sie den ursprünglichen Zielserver (sofern er noch verwendet werden soll) und den neuen Zielserver neu.
1. Die Daten werden an den neuen Zielserver gesendet, den Sie angegeben haben.
