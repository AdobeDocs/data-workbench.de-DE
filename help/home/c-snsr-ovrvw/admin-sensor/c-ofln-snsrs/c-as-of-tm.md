---
description: Ein Data Workbench-Server erkennt eine Datenquelle, z. B. einen Sensor, wenn er Daten von dieser Quelle erhält.
solution: Insight
title: '"Ausführungszeit"'
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# &quot;Ausführungszeit&quot;{#understanding-as-of-time}

Ein Data Workbench-Server erkennt eine Datenquelle, z. B. einen Sensor, wenn er Daten von dieser Quelle erhält.

Die Ausführungszeit ist eine Garantie dafür, dass die Daten für alle Datenquellen, von denen sie Kenntnis hat, [!DNL data workbench server] vorliegen.

Nehmen wir an, wir haben eine Reihe von drei [!DNL Sensors] Daten, die Daten an eine senden [!DNL data workbench server]: WEB1, WEB2 und WEB3. Während der [!DNL data workbench server] Empfänger und die Verarbeitung der Daten aus diesen Quellen erfolgt [!DNL Sensors], werden automatisch die Daten aus den einzelnen Quellen erwartet. Die Ausführungszeit gibt das letzte Mal an, dass die Daten aus allen drei Quellen [!DNL data workbench server] empfangen wurden.

In der Praxis interessiert sich die Zeit [!DNL data workbench server] nur für das Zeitlimit und nicht für das, was man als &quot;Wandzeit&quot;bezeichnen könnte, oder die Zeit von einer Uhr an der Wand. Die Zeit [!DNL data workbench server] kennt man nur als Ausführungszeit. Dies ist besonders wichtig für die Berichterstellung, da es gewährleistet, dass Berichte immer auf der Grundlage des Ausführungszeitraums ausgeführt werden, wodurch sichergestellt wird, dass Berichte mit nur partiellen Daten niemals an Endbenutzer des Systems gesendet werden können.

Die [!DNL data workbench server] nutzt Daten, die vom Sender gesendet werden, um die Ausführungszeit bereitzustellen, unabhängig davon, ob es sich um tatsächliche Daten handelt, die von der Website erfasst werden, oder um periodische Heartbeats, die von Ihrer [!DNL Sensors]Person gesendet werden. Diese Heartbeats dienen zwei Zwecken:

1. Um eine HTTP/1.1-persistente Verbindung zwischen dem [!DNL Sensor] und dem [!DNL data workbench server]zu halten.

1. Um die Ausführungszeit für den Fall, dass kein Website-Traffic erfasst und an den [!DNL data workbench server]Benutzer gesendet wird, auf dem neuesten Stand zu halten.

