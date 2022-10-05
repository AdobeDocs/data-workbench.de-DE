---
description: Beim Erfassen von Ereignisdaten von einem Webserver setzt Sensor automatisch ein beständiges Cookie für jeden Besucher, der eine kleine zufällige Kennung enthält, ohne personenbezogene Daten zu erfassen.
title: Identifizierung von Besuchern und Sitzungen durch Sensor
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# Identifizierung von Besuchern und Sitzungen durch Sensor{#how-does-sensor-identify-visitors-and-sessions}

{{eol}}

Beim Erfassen von Ereignisdaten von einem Webserver setzt Sensor automatisch ein beständiges Cookie für jeden Besucher, der eine kleine zufällige Kennung enthält, ohne personenbezogene Daten zu erfassen.

Mit diesem Adobe-Cookie werden der Unique Visitor und alle zugehörigen Sitzungen identifiziert.

Standardmäßig [!DNL Sensor] erfasst alle Felder des W3C Extended Log File Format von jedem HTTP-Header, Sie können jedoch [!DNL Sensor] , um alle Header zu erfassen, die zwischen dem Client und dem Server übertragen werden. Informationen zu den Ereignisdatenfeldern, die von [!DNL Sensor] in [!DNL .vsl] -Dateien, siehe [Felder für Ereignisdatensätze](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Die Browser einiger Besucher speichern keine Cookies dauerhaft, und eine sehr geringe Anzahl von Browsern akzeptiert überhaupt keine Cookies (auch keine Sitzungs-Cookies). Obwohl sie nur einen Bruchteil des gesamten Traffics einer Site ausmachen, können sie zu einer signifikanten Fehlzählung führen, wenn jeder Seitenaufruf eines solchen Besuchers fälschlicherweise als gesamte Sitzung gezählt wird, wie dies bei einigen Protokolldateianalyseprogrammen der Fall ist. Adobe behebt dieses Problem, indem es Ihnen ermöglicht, Besucher mit und ohne Cookies zu analysieren.

Weitere Informationen zum Filter für fehlerhafte Sitzungen finden Sie unter *Data Workbench Sensor Guide*.
