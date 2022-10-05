---
description: Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.
title: Feststellen, dass die Datenübertragung funktioniert
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Feststellen, dass die Datenübertragung funktioniert{#confirming-that-the-data-transmitter-is-running}

{{eol}}

Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Überprüfen Sie, ob der Transmitter-Prozess ausgeführt wird.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Richten Sie in Insight Server administrative Warnhinweise ein.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Überprüfen Sie den Systemstatus des Sensors.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Überprüfen des Transmitter-Prozesses {#section-79806fa3b7034a8eaf571a66e24874d7}

Eine Möglichkeit, zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, zu überprüfen, ob der [!DNL Sensor] Sendervorgang wird auf jedem Webserver ausgeführt, auf dem ein [!DNL Sensor] installiert ist. Der Transmitter-Prozess erscheint in der Prozessliste des Webservers als &quot;txlogd&quot;. Sie können diese Prüfung mit einem Systemüberwachungstool durchführen.

## Einrichten administrativer Warnhinweise auf dem Data Workbench-Server {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Eine andere Möglichkeit, um zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, automatisierte administrative Warnhinweise im [!DNL data workbench server]. Wenn administrative Warnhinweise konfiguriert wurden, wird die [!DNL data workbench server] erzeugt einen E-Mail-Warnhinweis, wenn keine Daten von einer konfigurierten und zuvor verbundenen Person empfangen wurden [!DNL Sensor] innerhalb des im [!DNL Sensor] Parameter für Warnhinweis-Timeout (min) im [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] -Datei. Weitere Informationen zum Einrichten von Verwaltungswarnungen finden Sie im Abschnitt *Handbuch zur Installation und Verwaltung von Serverprodukten*.

## Überprüfen des Systemstatus des Sensors {#section-de9d7e359242487a9fbead4ed65aebbc}

Eine andere Möglichkeit, zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, die [!DNL Servers Manager] in der Data Workbench.

**So zeigen Sie die[!DNL Servers Manager]**

* Klicken Sie in Data Workbench mit der rechten Maustaste auf einen Arbeitsbereich und klicken Sie auf **[!UICONTROL Admin]**, dann unter [!DNL Manage]klicken **[!UICONTROL Servers]**.

Wenn das Symbol für eine [!DNL Sensor] grün ist, wird der Transmitter ausgeführt.

Weitere Informationen zum [!DNL Servers Manager], siehe das Kapitel &quot;Verwaltungsschnittstellen&quot;im Abschnitt *Data Workbench [!DNL Sensor] Handbuch*.
