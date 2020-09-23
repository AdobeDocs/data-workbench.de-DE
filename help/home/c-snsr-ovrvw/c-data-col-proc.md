---
description: Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem der Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, wegfällt.
solution: Analytics
title: Funktionsweise des Prozesses für die Datenerfassung
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---


# Funktionsweise des Prozesses für die Datenerfassung{#how-does-the-data-collection-process-work}

Sensor automatisiert die Erfassung von Daten aus Ihrem Internet-Kanal, indem der Großteil der menschlichen Arbeit, die traditionell an der Datenerfassung beteiligt ist, wegfällt.

In vielen Fällen [!DNL Sensor] kann die Verwendung Ihren Data Management-Prozess erheblich vereinfachen.

Die heutigen großen Internet-, Extranet- und Intranet-Sites laufen oft auf einer Vielzahl von Webservern. Die erzeugten Protokolle und Daten können sehr groß und schwerfällig zu verwalten sein. Wenn auf Ihrer Site beispielsweise 30 Webserver ausgeführt werden, würde normalerweise ein Mitarbeiter (oder Mitarbeiter eines ausgelagerten Dienstleisters) jede Protokolldatei auf jedem der 30 Server abrufen und konsolidieren und dann Berichte darauf ausführen. Die Installation [!DNL Sensor] auf jedem Ihrer Webserver automatisiert diesen gesamten Prozess, reduziert Ihre Kosten und stellt Daten in Echtzeit bereit.

Zur Automatisierung dieses Prozesses werden Rohdaten über den Traffic auf einer Website direkt von jedem Webserver erfasst. [!DNL Sensor] Die Rohdaten, die [!DNL Sensor] erfasst werden, werden als Ereignis-Daten bezeichnet und ähneln dem Datentyp, den der Webserver in seinen Protokolldateien aufzeichnet.

Um diese Daten zu erfassen, wird die Instrumentierung in [!DNL Sensor] Datensätzen zu jeder HTTP-Anforderung ausgeführt, die Ihr Webserver verarbeitet. [!DNL Sensor] speichert dann die Informationen zum Schutz vor Netzwerkausfällen und sendet die Informationen sicher über HTTP/S an die von Ihnen angegebene [!DNL data workbench server] .

Nach dem [!DNL data workbench server] Empfang der Daten werden Ihre Protokolldateien in hochkomprimierten [!DNL .vsl] Formaten verarbeitet und gespeichert, sodass Sie sehr große Datenmengen problemlos auf preiswerter Hardware verwalten können.

Informationen zu den Datenfeldern für Ereignisse, die von [!DNL Sensor] in [!DNL .vsl] Dateien erfasst werden, finden Sie unter Datendatensatzfelder für [Ereignisse](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
