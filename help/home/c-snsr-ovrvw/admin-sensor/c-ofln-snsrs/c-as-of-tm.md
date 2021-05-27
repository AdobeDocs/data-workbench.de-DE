---
description: Ein Data Workbench-Server erkennt eine Datenquelle, z. B. einen Sensor, wenn er Daten von dieser Quelle erhält.
title: Grundlagen zur Zeit des Dateneingangs
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Grundlagen zur Zeit des Dateneingangs{#understanding-as-of-time}

Ein Data Workbench-Server erkennt eine Datenquelle, z. B. einen Sensor, wenn er Daten von dieser Quelle erhält.

Die Ausführungszeit ist eine Garantie dafür, dass das [!DNL data workbench server] Daten für alle Datenquellen hat, von denen es Kenntnis hat.

Angenommen, wir haben einen Satz von drei [!DNL Sensors] , die Daten an [!DNL data workbench server] senden: WEB1, WEB2 und WEB3. Da [!DNL data workbench server] die Daten von diesen [!DNL Sensors] empfängt und verarbeitet, werden automatisch Daten von jeder dieser Quellen erwartet. Die Ausführungszeit gibt an, wann [!DNL data workbench server] das letzte Mal Daten aus allen drei dieser Quellen erhalten hat.

Praktisch betrachtet interessiert das [!DNL data workbench server] nur die Zeit des Ausführungsrhythmus und nicht die Zeit, die man als &quot;Wandzeit&quot;bezeichnen könnte, oder die Zeit von einer Uhr an der Wand. Die [!DNL data workbench server] kennt die Zeit nur als Ausführungszeit. Dies ist besonders für Berichtszwecke wichtig, da es garantiert, dass Berichte immer auf der Grundlage des Ausführungszeitpunkts ausgeführt werden, wodurch sichergestellt wird, dass Berichte mit nur partiellen Daten nie an Endbenutzer des Systems gesendet werden können.

[!DNL data workbench server] verwendet Daten, die vom Transmitter gesendet werden, um die Ausführungszeit bereitzustellen, unabhängig davon, ob es sich um tatsächliche Daten handelt, die von der Website erfasst werden, oder um periodische Heartbeats, die von Ihrem [!DNL Sensors] gesendet werden. Diese Heartbeats dienen zwei Zwecken:

1. Um eine persistente HTTP/1.1-Verbindung zwischen [!DNL Sensor] und [!DNL data workbench server] offen zu halten.

1. Damit bleibt die Ausführungszeit für den Fall, dass kein Website-Traffic erfasst und an [!DNL data workbench server] gesendet wird, aktuell.
