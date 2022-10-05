---
description: Informationen zur allgemeinen Konfiguration des Sensors mit einer Webserverinstanz, die auf einem Webserver ausgeführt wird.
title: Arbeiten mit mehreren Instanzen eines Web-Servers
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Arbeiten mit mehreren Instanzen eines Web-Servers{#working-with-multiple-instances-of-a-web-server}

{{eol}}

Informationen zur allgemeinen Konfiguration des Sensors mit einer Webserverinstanz, die auf einem Webserver ausgeführt wird.

![](assets/web_inst.png)

In diesem Szenario schreibt eine einzelne Webserverinstanz Daten in die Memory Mapped Queue-Datei, die vom Transmitter gelesen und an die [!DNL data workbench server].

Wann [!DNL Sensor] auf einem Webserver installiert ist, auf dem mehrere Collector-Instanzen ausgeführt werden, können Sie ihn auf zwei Arten konfigurieren:

* Sie können alle Sammlermodule eine Warteschlangendatei gemeinsam nutzen lassen.

   Bei Verwendung einer einzelnen Warteschlangendatei wird die Verwaltung, Konfiguration und Verwaltung etwas vereinfacht, da die Architektur selbst weniger komplex ist. Bei einer einzelnen Warteschlangendatei wird jedoch der gesamte Webserver unabhängig von der Anzahl der Instanzen als WEB1 identifiziert.

* Sie können die oben beschriebene Architektur mehrmals replizieren und jede Webserverinstanz über eine separate Warteschlangendatei verfügen.

   Dadurch können Sie jede der Webserverinstanzen eindeutig identifizieren. Mit anderen Worten, die Identifizierung des Webservers (und die entsprechende Sensor-ID im [!DNL Sensor] -Konfiguration) eine Funktion dieser Konfiguration ist.

In jedem Fall enthalten die Daten weiterhin alle Hostnameninformationen, sodass Sie zwischen [!DNL www.client.com], [!DNL www2.client.com]usw. Die richtige Konfiguration wird durch die Analyseziele bestimmt und ob die Analysten die Daten basierend auf einer bestimmten Instanz segmentieren müssen, die auf einem Webserver ausgeführt wird.

>[!NOTE]
>
>Diese Art der Segmentierung wird in der Regel nur in der operativen Analyse verwendet und bietet außerhalb dieses Bereichs keinen praktischen Nutzen.
