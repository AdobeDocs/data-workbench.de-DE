---
description: Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem der Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, wegfällt.
title: Funktionsweise des Prozesses für die Datenerfassung
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Funktionsweise des Prozesses für die Datenerfassung{#how-does-the-data-collection-process-work}

Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem der Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, wegfällt.

In vielen Fällen kann die Verwendung von [!DNL Sensor] den Data Management-Prozess erheblich vereinfachen.

Die heutigen großen Internet-, Extranet- und Intranet-Sites laufen oft auf einer Vielzahl von Webservern. Die erzeugten Protokolle und Daten können sehr groß und schwerfällig zu verwalten sein. Wenn auf Ihrer Site beispielsweise 30 Webserver ausgeführt werden, würde normalerweise ein Mitarbeiter (oder Mitarbeiter eines ausgelagerten Dienstleisters) jede Protokolldatei auf jedem der 30 Server abrufen und konsolidieren und dann Berichte darauf ausführen. Durch die Installation von [!DNL Sensor] auf jedem Ihrer Webserver wird dieser gesamte Prozess automatisiert, wodurch Ihre Kosten gesenkt und Daten in Echtzeit zur Verfügung gestellt werden.

Zur Automatisierung dieses Prozesses sammelt [!DNL Sensor] Rohdaten zum Traffic auf einer Website direkt von jedem Webserver. Die Rohdaten, die von [!DNL Sensor] erfasst werden, werden Ereignis-Daten genannt und ähneln dem Datentyp, den der Webserver in seinen Protokolldateien aufzeichnet.

Um diese Daten zu erfassen, zeichnet die Instrumentierung in [!DNL Sensor] Informationen zu jeder HTTP-Anforderung auf, die Ihr Webserver verarbeitet. [!DNL Sensor] puffert dann die Informationen zum Schutz vor Netzwerkausfällen und sendet die Informationen sicher über HTTP/S an  [!DNL data workbench server] die angegebenen Daten.

Nachdem die [!DNL data workbench server] die Daten erhalten haben, werden Ihre Protokolldateien in hochkomprimierten Dateien im Format [!DNL .vsl] verarbeitet und gespeichert, sodass Sie sehr große Datenmengen auf preiswerter Hardware problemlos verwalten können.

Informationen zu den von [!DNL Sensor] in [!DNL .vsl]-Ereignis erfassten Datenfeldern finden Sie unter [Ereignis Data Record Fields](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
