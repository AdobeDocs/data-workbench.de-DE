---
description: Der Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem er den Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, eliminiert.
title: Funktionsweise des Prozesses für die Datenerfassung
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Funktionsweise des Prozesses für die Datenerfassung{#how-does-the-data-collection-process-work}

{{eol}}

Der Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem er den Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, eliminiert.

In vielen Fällen kann mithilfe von [!DNL Sensor] kann den Datenverwaltungsprozess erheblich vereinfachen.

Die heutigen großen Internet-, Extranet- und Intranet-Sites laufen oft auf einer Vielzahl von Webservern. Die erzeugten Protokolle und Daten können sehr umfangreich und schwerfällig verwaltet werden. Wenn Ihre Site beispielsweise 30 Webserver betreibt, würde normalerweise ein Mitarbeiter (oder Mitarbeiter eines ausgelagerten Dienstleisters) jede Protokolldatei auf jedem der 30 Server abrufen und konsolidieren und anschließend Berichte zu diesen Servern ausführen. Installieren [!DNL Sensor] auf jedem Ihrer Webserver automatisiert diesen gesamten Prozess, reduziert Ihre Kosten und stellt Daten in Echtzeit zur Verfügung.

Um diesen Prozess zu automatisieren, [!DNL Sensor] erfasst Rohdaten zum Traffic auf einer Website direkt von jedem Webserver. Die Rohdaten, die [!DNL Sensor] erfasst Ereignisdaten und ähnelt dem Datentyp, den Ihr Webserver in seinen Protokolldateien aufzeichnet.

Um diese Daten zu erfassen, instrumentieren Sie in [!DNL Sensor] erfasst Informationen zu jeder HTTP-Anforderung, die Ihr Webserver verarbeitet. [!DNL Sensor] speichert dann die Informationen zum Schutz vor Netzwerkfehlern und sendet die Informationen sicher über HTTP/S an die [!DNL data workbench server] die Sie angeben.

Nach dem [!DNL data workbench server] empfängt die Daten, verarbeitet und speichert Ihre Protokolldateien in hochkomprimierter Form [!DNL .vsl] Dateien formatieren, sodass Sie sehr große Datenmengen einfach auf billiger Hardware verwalten können.

Informationen zu den Ereignisdatenfeldern, die von [!DNL Sensor] in [!DNL .vsl] -Dateien, siehe [Felder für Ereignisdatensätze](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
