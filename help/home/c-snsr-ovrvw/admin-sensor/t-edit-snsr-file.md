---
description: Die Konfigurationsdatei "Sensor", txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.
solution: Analytics
title: Bearbeiten der Datei „Sensor txlogd.conf“
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---


# Bearbeiten der Datei „Sensor txlogd.conf“{#editing-the-sensor-txlogd-conf-file}

Die Konfigurationsdatei &quot;Sensor&quot;, txlogd.conf, enthält Parameter, die Sensor verwendet, um eine Verbindung mit dem Data Workbench-Server herzustellen.

Zu diesen Parametern gehören die Adresse, die Anschlussnummer und das Kommunikationsprotokoll (HTTP oder HTTPS) des Servers. Die Konfigurationsdatei enthält außerdem Filteroptionen für Protokollinhalte und kontrollierte Experimentinformationen. Kontrollierte Experimente ermöglichen es Site-Designern, Experimente zum Testen von Inhalten oder Designänderungen in einer Untergruppe aller Site-Besucher durchzuführen.

Wenn Sie andere [!DNL txlogd.conf] Parameter ändern, z. B. die IP-Adresse der [!DNL data workbench server] oder den Namen der [!DNL Sensor][!DNL txlogd.conf] [!DNL Sensor] , können Sie einfach durch die aktualisierte Version ersetzen und die Änderungen automatisch abrufen. Auf einigen Systemen ist es möglicherweise nicht möglich, die Datei zu bearbeiten oder zu ersetzen, ohne den Webserver- oder Senderprozess zu beenden.

**So öffnen und bearbeiten Sie txlogd.conf**

1. Navigieren Sie zum [!DNL Sensor] Installationsordner und öffnen Sie die [!DNL txlogd.conf] Datei in einem Texteditor.
1. Bearbeiten Sie die Datei nach Bedarf.
1. Speichern und schließen Sie die Datei.

   * Der Speicherort der Konfigurationsdatei für kontrollierte Experimente (definiert durch den ExpFile-Parameter in der [!DNL txlogd.conf] Datei) sollte sich in einem Ordner auf dem Webserver befinden, auf den Ihre Webinhalt-Entwickler zugreifen können oder der von Ihrem Content-Management-System gesteuert wird.
   * Der Wert im Parameter ExpCookieURL ist eine virtuelle Seite, die zum Testen von Websites verwendet wird. Ein Benutzer, der diese Seite besucht, erhält eine neue Tracking-ID.

Weitere Informationen zur Zusammenarbeit [!DNL txlogd.conf]erhalten Sie bei Adobe Consulting Services.
