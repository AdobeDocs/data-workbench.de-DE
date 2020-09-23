---
description: Beim Sammeln von Ereignis-Daten von einem Webserver setzt Sensor automatisch ein beständiges Cookie für jeden Besucher, der einen kleinen zufälligen Bezeichner enthält, ohne dass personenbezogene Daten erfasst werden.
solution: Analytics
title: Identifizierung von Besuchern und Sitzungen durch Sensor
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---


# Identifizierung von Besuchern und Sitzungen durch Sensor{#how-does-sensor-identify-visitors-and-sessions}

Beim Sammeln von Ereignis-Daten von einem Webserver setzt Sensor automatisch ein beständiges Cookie für jeden Besucher, der einen kleinen zufälligen Bezeichner enthält, ohne dass personenbezogene Daten erfasst werden.

Dieses Adobe-Cookie dient zur Identifizierung des eindeutigen Besuchers und aller zugehörigen Sitzungen.

Standardmäßig [!DNL Sensor] werden alle Felder im erweiterten Protokolldateiformat des W3C von jedem HTTP-Header erfasst. Sie können jedoch konfigurieren, [!DNL Sensor] dass alle Header erfasst werden, die zwischen Client und Server übertragen werden. Informationen zu den Datenfeldern für Ereignisse, die von [!DNL Sensor] in [!DNL .vsl] Dateien erfasst werden, finden Sie unter Datendatensatzfelder für [Ereignisse](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Die Browser einiger Besucher speichern keine Cookies dauerhaft, und eine sehr geringe Anzahl von Besuchern akzeptiert keine Cookies (auch keine Sitzungs-Cookies). Obwohl sie nur einen Bruchteil des gesamten Traffics einer Site ausmachen, können sie zu einer erheblichen Fehlzählung führen, wenn jede Ansicht durch einen solchen Besucher fälschlicherweise als Gesamtsitzung gezählt wird, wie dies von einer Protokolldatei-Analyse ausgeführt wird. Adobe behebt dieses Problem, indem Sie Besucher mit und ohne Cookies analysieren können.

Weitere Informationen zum Filter für fehlerhafte Sitzungen finden Sie im Handbuch *Data Workbenchs-Sensor*.
