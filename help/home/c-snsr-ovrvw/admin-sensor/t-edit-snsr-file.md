---
description: Die Konfigurationsdatei "Sensor", txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.
title: Bearbeiten der Datei „Sensor txlogd.conf“
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Bearbeiten der Datei „Sensor txlogd.conf“{#editing-the-sensor-txlogd-conf-file}

Die Konfigurationsdatei &quot;Sensor&quot;, txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.

Zu diesen Parametern gehören die Adresse, die Anschlussnummer und das Kommunikationsprotokoll (HTTP oder HTTPS) des Servers. Die Konfigurationsdatei enthält außerdem Filteroptionen für Protokollinhalte und kontrollierte Experimentinformationen. Kontrollierte Experimente ermöglichen es Site-Designern, Experimente zum Testen von Inhalten oder Designänderungen in einer Untergruppe aller Site-Besucher durchzuführen.

Wenn Sie andere Parameter wie die IP-Adresse von [!DNL data workbench server] oder den Namen von [!DNL Sensor] ändern, können Sie [!DNL txlogd.conf] einfach durch die aktualisierte Version ersetzen und [!DNL Sensor] nimmt die Änderungen automatisch auf. [!DNL txlogd.conf] Auf einigen Systemen ist es möglicherweise nicht möglich, die Datei zu bearbeiten oder zu ersetzen, ohne den Webserver- oder Senderprozess zu beenden.

**So öffnen und bearbeiten Sie txlogd.conf**

1. Navigieren Sie zum Installationsordner [!DNL Sensor] und öffnen Sie die Datei [!DNL txlogd.conf] in einem Texteditor.
1. Bearbeiten Sie die Datei nach Bedarf.
1. Speichern und schließen Sie die Datei.

   * Der Speicherort der Konfigurationsdatei für kontrollierte Experimente (definiert durch den Parameter ExpFile in der Datei [!DNL txlogd.conf]) sollte sich in einem Verzeichnis auf dem Webserver befinden, auf das Ihre Webinhalt-Entwickler zugreifen können oder das von Ihrem Content-Management-System gesteuert wird.
   * Der Wert im Parameter ExpCookieURL ist eine virtuelle Seite, die zum Testen von Websites verwendet wird. Ein Benutzer, der diese Seite besucht, erhält eine neue Tracking-ID.

Weitere Informationen zum Arbeiten mit [!DNL txlogd.conf] erhalten Sie bei Adobe Consulting Services.
