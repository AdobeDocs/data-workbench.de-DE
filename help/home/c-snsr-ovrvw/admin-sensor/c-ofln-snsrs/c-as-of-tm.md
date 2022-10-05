---
description: Ein Data Workbench-Server erkennt eine Datenquelle, z. B. einen Sensor, wenn er Daten von dieser Quelle erhält.
title: Grundlagen zur Zeit des Dateneingangs
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Grundlagen zur Zeit des Dateneingangs{#understanding-as-of-time}

{{eol}}

Ein Data Workbench-Server erkennt eine Datenquelle, z. B. einen Sensor, wenn er Daten von dieser Quelle erhält.

Die Ausführungsdauer ist eine Garantie dafür, dass die [!DNL data workbench server] verfügt über Daten für alle Datenquellen, von denen sie Kenntnis hat.

Nehmen wir an, wir haben eine Reihe von drei [!DNL Sensors] , die Daten an eine [!DNL data workbench server]: WEB1, WEB2 und WEB3. Als [!DNL data workbench server] empfängt und verarbeitet die Daten aus diesen [!DNL Sensors], werden automatisch Daten aus jeder dieser Quellen erwartet. Die Ausführungszeit gibt das letzte Mal an, dass die Variable [!DNL data workbench server] Daten aus allen drei dieser Quellen erhalten hat.

In der Praxis wird die [!DNL data workbench server] Es geht nur um den Zeitablauf und nicht um das, was man als &quot;Wandzeit&quot;bezeichnen könnte, oder die Zeit von einer Uhr an der Wand. Die [!DNL data workbench server] kennt die Zeit nur als Ausführungszeit. Dies ist besonders für Berichtszwecke wichtig, da es garantiert, dass Berichte immer auf der Grundlage des Ausführungszeitpunkts ausgeführt werden, wodurch sichergestellt wird, dass Berichte mit nur partiellen Daten nie an Endbenutzer des Systems gesendet werden können.

Die [!DNL data workbench server] verwendet Daten, die vom Transmitter gesendet werden, um die Ausführungszeit bereitzustellen, unabhängig davon, ob es sich um tatsächliche Daten handelt, die von der Website erfasst werden, oder um periodische Heartbeats, die von Ihrer [!DNL Sensors]. Diese Heartbeats dienen zwei Zwecken:

1. Um eine persistente HTTP/1.1-Verbindung zwischen der [!DNL Sensor] und [!DNL data workbench server].

1. Damit die Ausführungszeit auch dann aktuell bleibt, wenn kein Website-Traffic erfasst und an die [!DNL data workbench server].
