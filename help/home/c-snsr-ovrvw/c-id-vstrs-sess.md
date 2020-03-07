---
description: Beim Sammeln von Ereignisdaten von einem Webserver setzt Sensor automatisch ein beständiges Cookie für jeden Besucher, der einen kleinen zufälligen Bezeichner enthält, ohne dass persönliche Identifizierungsinformationen erfasst werden.
solution: Insight
title: Wie identifiziert Sensor Besucher und Sitzungen?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Wie identifiziert Sensor Besucher und Sitzungen?{#how-does-sensor-identify-visitors-and-sessions}

Beim Sammeln von Ereignisdaten von einem Webserver setzt Sensor automatisch ein beständiges Cookie für jeden Besucher, der einen kleinen zufälligen Bezeichner enthält, ohne dass persönliche Identifizierungsinformationen erfasst werden.

Mit diesem Adobe-Cookie werden der individuelle Besucher und alle zugehörigen Sitzungen identifiziert.

Standardmäßig [!DNL Sensor] werden alle Felder im erweiterten Protokolldateiformat des W3C von jedem HTTP-Header erfasst. Sie können jedoch konfigurieren, [!DNL Sensor] dass alle Header erfasst werden, die zwischen Client und Server übertragen werden. Informationen zu den Ereignisdatenfeldern, die von [!DNL Sensor] in [!DNL .vsl] Dateien erfasst werden, finden Sie unter [Ereignisdatensatzfelder](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Einige Browser von Besuchern speichern Cookies nicht dauerhaft, und eine sehr geringe Anzahl von Browsern akzeptiert überhaupt keine Cookies (auch keine Sitzungs-Cookies). Obwohl sie nur einen Bruchteil des gesamten Traffics einer Site ausmachen, können sie zu einer erheblichen Fehlzählung führen, wenn jede Seitenansicht eines solchen Besuchers fälschlicherweise als gesamte Sitzung gezählt wird, wie dies von einer Protokolldatei-Analysesoftware ausgeführt wird. Adobe behebt dieses Problem, indem es Ihnen ermöglicht, Besucher mit und ohne Cookies zu analysieren.

Weitere Informationen zum Filter für fehlerhafte Sitzungen finden Sie im *Data Workbench Sensor Guide*.
