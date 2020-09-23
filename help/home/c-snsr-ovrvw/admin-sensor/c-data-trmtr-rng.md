---
description: Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.
solution: Analytics
title: Feststellen, dass die Datenübertragung funktioniert
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# Feststellen, dass die Datenübertragung funktioniert{#confirming-that-the-data-transmitter-is-running}

Überprüfen Sie, ob der Sender ausgeführt wird, indem Sie Warnhinweise einrichten, den Systemstatus des Sensors überprüfen und vieles mehr.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

* [Überprüfen Sie, ob der Transmitter-Prozess ausgeführt wird.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Richten Sie Administratorwarnungen in Insight Server ein.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Überprüfen Sie den Systemstatus des Sensors.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Transmitter-Prozess überprüfen {#section-79806fa3b7034a8eaf571a66e24874d7}

Eine Möglichkeit, zu überprüfen, ob der Transmitter ausgeführt wird, besteht darin, zu überprüfen, ob der [!DNL Sensor] Transmitter-Prozess auf jedem Webserver ausgeführt wird, auf dem eine [!DNL Sensor] Instanz installiert ist. Der Transmitter-Prozess erscheint als &quot;txlogd&quot;in der Liste der Prozesse des Webservers. Sie können diese Prüfung mit einem Systemüberwachungstool durchführen.

## Einrichten von Administratorwarnungen im Data Workbench-Server {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Eine andere Möglichkeit, zu überprüfen, ob der Sender ausgeführt wird, ist die Einrichtung automatisierter Administratorwarnungen im [!DNL data workbench server]. Wenn Verwaltungswarnungen konfiguriert wurden, [!DNL data workbench server] wird eine E-Mail-Warnung generiert, wenn keine Daten von einer konfigurierten und zuvor [!DNL Sensor] innerhalb des im Parameter &quot; [!DNL Sensor] Warnungszeitlimit (min)&quot;in der [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] Datei angegebenen Zeitraums gesendet wurden. Weitere Informationen zum Einrichten von Administratorwarnungen finden Sie im Handbuch zur Installation und Verwaltung von *Serverprodukten*.

## Überprüfen des Systemstatus des Sensors {#section-de9d7e359242487a9fbead4ed65aebbc}

Eine weitere Möglichkeit, zu überprüfen, ob der Sender läuft, ist die manuelle Überprüfung der [!DNL Servers Manager] Data Workbench.

**Zur Ansicht der[!DNL Servers Manager]**

* Klicken Sie in der Data Workbench mit der rechten Maustaste auf einen Arbeitsbereich, klicken Sie auf **[!UICONTROL Admin]** und dann unter [!DNL Manage]und klicken Sie auf **[!UICONTROL Servers]**.

Wenn das Symbol für eine [!DNL Sensor] grün ist, wird der Sender ausgeführt.

Weitere Informationen zum Thema [!DNL Servers Manager]finden Sie im Kapitel &quot;Verwaltungsschnittstellen&quot;des *Data Workbenchs-[!DNL Sensor]Handbuchs*.
