---
description: Sie müssen Sensor auf jedem Webserver installieren und ausführen, der den Inhalt für Ihre Site bereitstellt, um alle Anfragen zu erfassen, die von diesen Servern angezeigt werden.
title: Wie lassen sich diese Daten erfassen?
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Wie lassen sich diese Daten erfassen?{#how-do-i-acquire-this-data}

Sie müssen Sensor auf jedem Webserver installieren und ausführen, der den Inhalt für Ihre Site bereitstellt, um alle Anfragen zu erfassen, die von diesen Servern angezeigt werden.

Auf diese Anfragen entfallen 90 % oder mehr der Anfragen an Ihre Site und 90 % oder mehr der Daten, die für die vollständige Analyse des Traffics auf Ihrer Site benötigt werden. [!DNL Page Tags] sollte dann verwendet werden, um die verbleibenden 10 % oder weniger der Traffic-Daten zu erfassen, die Ihren Webservern nicht bekannt sind. Die folgenden Konfigurationen sind jedoch für die Erfassung von Web-Anfragedaten von Ihrer Site basierend auf unserer betrieblichen Erfahrung in der bevorzugten Reihenfolge gültig:

1. [!DNL Sensor] wird auf jedem Webserver installiert, den Sie steuern und der Ihre Site unterstützt. Inhalte von Drittanbieter-Sites, aus dem Cache bereitgestellte Inhalte und bestimmte Arten dynamischer Inhalte sollten mit Tags versehen werden. Diese Seiten-Tags sollten die erfassten Daten an einen Webserver an Ihrem Speicherort senden, der [!DNL Sensor] ausführt. Sie können einen zusätzlichen Webserver hinzufügen, wenn der Traffic von Seiten-Tag-Anfragen dies rechtfertigt, oder in besonderen Fällen einen Webserver zur Erfassung dieser Seiten-Tag-Anforderungen zuweisen.
1. [!DNL Sensor] wird auf zwei Webservern installiert, die in diesem Handbuch auch als Datenerfassungs-Server bezeichnet werden und sich an Ihrem Standort befinden, der der Erfassung von Seiten-Tag-Anforderungsdaten von getaggten Seiten gewidmet ist. Alle Inhalte auf Ihrer Site sind mit Tags versehen und alle Seiten-Tags werden an die beiden Datenerfassungsserver weitergeleitet.
1. [!DNL Sensor’s] Datenerfassungsdienste werden von einem Outsourcer bereitgestellt, der Datenerfassungsserver ausführt, um alle Ihre Webanfragedaten zu erfassen. In diesem Fall werden alle Inhalte auf Ihrer Site mit Tags versehen und die Seiten-Tags senden ihre Daten an die ausgelagerten Datenerfassungsserver.

   Weitere Informationen zu [!DNL Sensor] finden Sie in der *Data Workbench [!DNL Sensor] Guide*.
