---
description: Informationen zur allgemeinen Konfiguration des Sensors mit einer Webserverinstanz, die auf einem Webserver ausgeführt wird.
solution: Analytics
title: Arbeiten mit mehreren Instanzen eines Web-Servers
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# Arbeiten mit mehreren Instanzen eines Web-Servers{#working-with-multiple-instances-of-a-web-server}

Informationen zur allgemeinen Konfiguration des Sensors mit einer Webserverinstanz, die auf einem Webserver ausgeführt wird.

![](assets/web_inst.png)

In diesem Szenario schreibt eine einzelne Webserverinstanz Daten in die speicherzugeordnete Warteschlangendatei, die vom Sender gelesen und an die [!DNL data workbench server]gesendet wird.

Wenn Sie auf einem Webserver installiert [!DNL Sensor] sind, auf dem mehrere Sammlungsinstanzen ausgeführt werden, haben Sie zwei Möglichkeiten, diese zu konfigurieren:

* Sie können alle Sammlermodule eine Warteschlangendatei gemeinsam verwenden lassen.

   Bei Verwendung einer einzelnen Warteschlangendatei werden Verwaltung, Konfiguration und Verwaltung etwas vereinfacht, da die Architektur selbst weniger komplex ist. Bei einer einzelnen Warteschlangendatei wird jedoch der gesamte Webserver unabhängig von der Anzahl der Instanzen als WEB1 gekennzeichnet.

* Sie können die oben genannte Architektur mehrmals replizieren und jede Webserverinstanz über eine separate Warteschlangendatei verfügen.

   Dadurch können Sie jede Webserverinstanz eindeutig identifizieren. Mit anderen Worten, die Identifizierung des Webservers (und der entsprechenden SensorID in der [!DNL Sensor] Konfiguration) ist eine Funktion dieser Konfiguration.

In jedem Fall verfügen die Daten immer noch über alle Hostnameninformationen, sodass Sie zwischen [!DNL www.client.com], [!DNL www2.client.com]usw. unterscheiden können. Die richtige Konfiguration wird durch die Analyse von Zielen bestimmt und ob die Analysten die Daten basierend auf einer bestimmten Instanz auf einem Webserver segmentieren müssen.

>[!NOTE]
>
>Diese Art der Segmentierung wird in der Regel nur in der betrieblichen Analyse verwendet und bietet außerhalb dieses Bereichs keinen großen praktischen Nutzen.

