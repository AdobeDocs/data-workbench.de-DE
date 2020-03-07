---
description: Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.
solution: Insight
title: Bestätigung, dass der Datensender ausgeführt wird
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bestätigung, dass der Datensender ausgeführt wird{#confirming-that-the-data-transmitter-is-running}

Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Überprüfen Sie, ob der Transmitter-Prozess ausgeführt wird.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Richten Sie Administratorwarnungen in Insight Server ein.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Überprüfen Sie den Systemstatus des Sensors.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Transmitter-Prozess überprüfen {#section-79806fa3b7034a8eaf571a66e24874d7}

Eine Möglichkeit, zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, zu überprüfen, ob der [!DNL Sensor] Transmitter-Prozess auf jedem Webserver ausgeführt wird, auf dem eine [!DNL Sensor] Instanz installiert ist. Der Transmitter-Prozess erscheint in der Prozessliste des Webservers als &quot;txlogd&quot;. Sie können diese Prüfung mit einem Systemüberwachungstool durchführen.

## Einrichten von Administratorwarnungen im Data Workbench-Server {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Eine andere Möglichkeit, zu überprüfen, ob der Sender ausgeführt wird, ist die Einrichtung automatisierter Administratorwarnungen im [!DNL data workbench server]. Wenn Verwaltungswarnungen konfiguriert wurden, [!DNL data workbench server] wird eine E-Mail-Warnung generiert, wenn keine Daten von einer konfigurierten und zuvor [!DNL Sensor] innerhalb des im Parameter &quot; [!DNL Sensor] Warnungszeitlimit (min)&quot;in der [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] Datei angegebenen Zeitraums gesendet wurden. Weitere Informationen zum Einrichten von Administratorwarnungen finden Sie im Handbuch zur Installation und Verwaltung von *Serverprodukten*.

## Überprüfen des Systemstatus des Sensors {#section-de9d7e359242487a9fbead4ed65aebbc}

Eine weitere Möglichkeit, zu überprüfen, ob der Transmitter ausgeführt wird, ist die manuelle Überprüfung der Daten [!DNL Servers Manager] in Data Workbench.

**So zeigen Sie die[!DNL Servers Manager]**

* Klicken Sie in Data Workbench mit der rechten Maustaste in einen Arbeitsbereich, klicken Sie **[!UICONTROL Admin]** und klicken Sie anschließend unter [!DNL Manage]und dann auf **[!UICONTROL Servers]**.

Wenn das Symbol für eine [!DNL Sensor] grün ist, wird der Sender ausgeführt.

Weitere Informationen zum Thema [!DNL Servers Manager]finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbench-[!DNL Sensor]Handbuchs*.
