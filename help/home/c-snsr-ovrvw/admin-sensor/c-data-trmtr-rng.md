---
description: Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.
title: Feststellen, dass die Datenübertragung funktioniert
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Feststellen, dass die Datenübertragung funktioniert{#confirming-that-the-data-transmitter-is-running}

Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Überprüfen Sie, ob der Transmitter-Prozess ausgeführt wird.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Richten Sie in Insight Server administrative Warnhinweise ein.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Überprüfen Sie den Systemstatus des Sensors.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Überprüfen des Transmitter-Prozesses {#section-79806fa3b7034a8eaf571a66e24874d7}

Eine Möglichkeit, zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, zu überprüfen, ob der Transmitter-Prozess [!DNL Sensor] auf jedem Webserver ausgeführt wird, auf dem eine [!DNL Sensor]-Instanz installiert ist. Der Transmitter-Prozess erscheint in der Prozessliste des Webservers als &quot;txlogd&quot;. Sie können diese Prüfung mit einem Systemüberwachungstool durchführen.

## Einrichten administrativer Warnhinweise im Data Workbench-Server {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Eine andere Möglichkeit, um zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, automatisierte administrative Warnhinweise in der [!DNL data workbench server] einzurichten. Wenn administrative Warnhinweise konfiguriert wurden, generiert der [!DNL data workbench server] einen E-Mail-Warnhinweis, wenn er innerhalb des im Parameter [!DNL Sensor] Warnhinweis-Timeout (min) in der Datei [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] angegebenen Zeitraums keine Daten von einem konfigurierten und zuvor verbundenen [!DNL Sensor] empfangen hat. Weitere Informationen zum Einrichten von Administratorwarnungen finden Sie im *Handbuch zur Installation und Verwaltung von Serverprodukten*.

## Überprüfen des Systemstatus des Sensors {#section-de9d7e359242487a9fbead4ed65aebbc}

Eine weitere Möglichkeit, um zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, die [!DNL Servers Manager] in der Data Workbench manuell zu überprüfen.

**So zeigen Sie die[!DNL Servers Manager]**

* Klicken Sie in Data Workbench mit der rechten Maustaste auf einen Arbeitsbereich, klicken Sie auf **[!UICONTROL Admin]** und dann unter [!DNL Manage] auf **[!UICONTROL Servers]**.

Wenn das Symbol für ein [!DNL Sensor] grün ist, wird der Transmitter ausgeführt.

Weitere Informationen zum [!DNL Servers Manager] finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;der *Data Workbench [!DNL Sensor] Guide*.
