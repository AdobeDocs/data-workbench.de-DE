---
description: Der Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem er den Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, eliminiert.
title: Funktionsweise des Prozesses für die Datenerfassung
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Funktionsweise des Prozesses für die Datenerfassung{#how-does-the-data-collection-process-work}

Der Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem er den Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, eliminiert.

In vielen Fällen kann die Verwendung von [!DNL Sensor] den Datenverwaltungsprozess erheblich vereinfachen.

Die heutigen großen Internet-, Extranet- und Intranet-Sites laufen oft auf einer Vielzahl von Webservern. Die erzeugten Protokolle und Daten können sehr umfangreich und schwerfällig verwaltet werden. Wenn Ihre Site beispielsweise 30 Webserver betreibt, würde normalerweise ein Mitarbeiter (oder Mitarbeiter eines ausgelagerten Dienstleisters) jede Protokolldatei auf jedem der 30 Server abrufen und konsolidieren und anschließend Berichte zu diesen Servern ausführen. Durch die Installation von [!DNL Sensor] auf jedem Ihrer Webserver wird dieser gesamte Prozess automatisiert, sodass Ihre Kosten reduziert und Daten in Echtzeit zur Verfügung gestellt werden.

Um diesen Prozess zu automatisieren, sammelt [!DNL Sensor] Rohdaten zum Traffic auf einer Website direkt von jedem Webserver. Die Rohdaten, die [!DNL Sensor] erfasst, werden Ereignisdaten genannt und ähneln dem Datentyp, den Ihr Webserver in seinen Protokolldateien aufzeichnet.

Um diese Daten zu erfassen, zeichnet die Instrumentierung in [!DNL Sensor] Informationen zu jeder HTTP-Anforderung auf, die Ihr Webserver verarbeitet. [!DNL Sensor] speichert dann die Informationen zum Schutz vor Netzwerkfehlern und sendet die Informationen sicher über HTTP/S an die von  [!DNL data workbench server] Ihnen angegebene.

Nachdem die [!DNL data workbench server] die Daten erhalten hat, werden Ihre Protokolldateien in hochkomprimierten [!DNL .vsl] -Dateien verarbeitet und gespeichert, sodass Sie sehr große Datenmengen auf kostengünstiger Hardware verwalten können.

Informationen zu den Ereignisdatenfeldern, die von [!DNL Sensor] in [!DNL .vsl]-Dateien erfasst werden, finden Sie unter [Ereignisdatensatzfelder](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
