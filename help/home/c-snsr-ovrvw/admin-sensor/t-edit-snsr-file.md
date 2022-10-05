---
description: Die Konfigurationsdatei für Sensor, txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.
title: Bearbeiten der Datei „Sensor txlogd.conf“
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Bearbeiten der Datei „Sensor txlogd.conf“{#editing-the-sensor-txlogd-conf-file}

{{eol}}

Die Konfigurationsdatei für Sensor, txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.

Zu diesen Parametern gehören die Adresse des Servers, die Portnummer und das Kommunikationsprotokoll (HTTP oder HTTPS). Die Konfigurationsdatei enthält auch Filteroptionen für Protokollinhalte und kontrollierte Experimentinformationen. Kontrollierte Experimente ermöglichen es Site-Designern, Experimente durchzuführen, um Inhalte oder Designänderungen in einer Untergruppe aller Site-Besucher zu testen.

Beim Ändern anderer [!DNL txlogd.conf] -Parameter, z. B. die IP-Adresse der [!DNL data workbench server] oder der Name der [!DNL Sensor], können Sie [!DNL txlogd.conf] mit der aktualisierten Version und [!DNL Sensor] nimmt die Änderungen automatisch auf. Auf einigen Systemen können Sie die Datei möglicherweise nicht bearbeiten oder ersetzen, ohne den Webserver- oder Senderprozess zu stoppen.

**So öffnen und bearbeiten Sie txlogd.conf**

1. Navigieren Sie zum [!DNL Sensor] Installationsordner und öffnen Sie die [!DNL txlogd.conf] in einem Texteditor.
1. Bearbeiten Sie die Datei nach Bedarf.
1. Speichern und schließen Sie die Datei.

   * Der Speicherort der Konfigurationsdatei für gesteuerte Experimente (definiert durch den Parameter ExpFile im [!DNL txlogd.conf] -Datei) in einem Ordner auf dem Webserver gespeichert sein, auf den Ihre Web-Content-Entwickler zugreifen können oder das von Ihrem Content-Management-System gesteuert wird.
   * Der Wert im Parameter ExpCookieURL ist eine virtuelle Seite, die zum Testen von Websites verwendet wird. Einem Benutzer, der diese Seite besucht, wird eine neue Tracking-ID zugewiesen.

Weitere Informationen zum Arbeiten mit [!DNL txlogd.conf], wenden Sie sich bitte an Adobe Consulting Services.
