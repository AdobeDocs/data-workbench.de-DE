---
description: Die Konfigurationsdatei für Sensor, txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.
title: Bearbeiten der Datei „Sensor txlogd.conf“
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Bearbeiten der Datei „Sensor txlogd.conf“{#editing-the-sensor-txlogd-conf-file}

Die Konfigurationsdatei für Sensor, txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.

Zu diesen Parametern gehören die Adresse des Servers, die Portnummer und das Kommunikationsprotokoll (HTTP oder HTTPS). Die Konfigurationsdatei enthält auch Filteroptionen für Protokollinhalte und kontrollierte Experimentinformationen. Kontrollierte Experimente ermöglichen es Site-Designern, Experimente durchzuführen, um Inhalte oder Designänderungen in einer Untergruppe aller Site-Besucher zu testen.

Wenn Sie andere [!DNL txlogd.conf]-Parameter ändern, z. B. die IP-Adresse von [!DNL data workbench server] oder den Namen von [!DNL Sensor], können Sie [!DNL txlogd.conf] einfach durch die aktualisierte Version ersetzen, und [!DNL Sensor] übernimmt automatisch die Änderungen. Auf einigen Systemen können Sie die Datei möglicherweise nicht bearbeiten oder ersetzen, ohne den Webserver- oder Senderprozess zu stoppen.

**So öffnen und bearbeiten Sie txlogd.conf**

1. Navigieren Sie zum Installationsverzeichnis [!DNL Sensor] und öffnen Sie die Datei [!DNL txlogd.conf] in einem Texteditor.
1. Bearbeiten Sie die Datei nach Bedarf.
1. Speichern und schließen Sie die Datei.

   * Der Speicherort der kontrollierten Experimentkonfigurationsdatei (definiert durch den Parameter ExpFile in der Datei [!DNL txlogd.conf] ) sollte sich in einem Ordner auf dem Webserver befinden, auf den Ihre Web-Content-Entwickler zugreifen können oder der von Ihrem Content-Management-System gesteuert wird.
   * Der Wert im Parameter ExpCookieURL ist eine virtuelle Seite, die zum Testen von Websites verwendet wird. Einem Benutzer, der diese Seite besucht, wird eine neue Tracking-ID zugewiesen.

Weitere Informationen zur Arbeit mit [!DNL txlogd.conf] erhalten Sie von Adobe Consulting Services.
