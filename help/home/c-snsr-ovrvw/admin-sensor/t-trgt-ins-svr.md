---
description: Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielserver), müssen Sie die Datei "txlogd.conf"auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.
title: Ändern des Data Workbench Target-Servers
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Ändern des Data Workbench Target-Servers{#changing-the-target-data-workbench-server}

{{eol}}

Um den Data Workbench-Server zu ändern, mit dem ein Sensor kommuniziert (der Zielserver), müssen Sie die Datei &quot;txlogd.conf&quot;auf jedem Webserver bearbeiten, auf dem Sensor installiert ist.

**So ändern Sie die Zielgruppe[!DNL data workbench server]**

1. Beenden Sie sowohl den ursprünglichen Zielserver als auch den neuen Zielserver.
1. Die neueste Version kopieren [!DNL .vsl] -Datei vom ursprünglichen Zielserver zum neuen Zielserver. Wenn Sie den neuen Zielserver in einem späteren Schritt neu starten, führt dies zu allen neuen [!DNL Sensor] Daten, die an die aktuelle, vorhandene [!DNL .vsl] anstatt eine neue [!DNL .vsl] -Datei. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie auf dem ursprünglichen Zielserver zum [!DNL \Logs] im Ordner [!DNL data workbench server] Installationsverzeichnis.

   1. Die neueste Version kopieren [!DNL .vsl] -Datei im Ordner.
   1. Navigieren Sie auf dem neuen Zielserver zum [!DNL \Logs] im Ordner [!DNL data workbench server] Installationsverzeichnis und fügen Sie die [!DNL .vsl] in diesen Ordner.

1. Auf einem der Webserver, auf denen [!DNL Sensor] installiert ist, öffnen Sie die [!DNL txlogd.conf] -Datei. Führen Sie dazu die folgenden Schritte aus:

   1. Navigieren Sie zum [!DNL Sensor] Installationsordner und öffnen Sie die [!DNL txlogd.conf] in einem Texteditor.

   1. Suchen Sie den Parameter ServerAddress und ändern Sie ihn entsprechend der Adresse des neuen Zielservers.
   1. Speichern und schließen Sie die Datei.

1. Wiederholen Sie die Schritte 2-3 auf allen anderen Webservern, auf denen [!DNL Sensor] installiert ist.
1. Starten Sie den ursprünglichen Zielserver (sofern er noch verwendet werden soll) und den neuen Zielserver neu.
1. Die Daten werden an den neuen Zielserver gesendet, den Sie angegeben haben.
