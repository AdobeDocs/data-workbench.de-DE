---
description: Sie müssen Sensor auf jedem Webserver installieren und ausführen, der den Inhalt für Ihre Site bereitstellt, um alle Anforderungen zu erfassen, die von diesen Servern angesehen werden.
title: Wie lassen sich diese Daten erfassen?
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Wie lassen sich diese Daten erfassen?{#how-do-i-acquire-this-data}

Sie müssen Sensor auf jedem Webserver installieren und ausführen, der den Inhalt für Ihre Site bereitstellt, um alle Anforderungen zu erfassen, die von diesen Servern angesehen werden.

Auf diese Anforderungen entfallen 90 % oder mehr der Anfragen an Ihre Site und 90 % oder mehr der Daten, die für die vollständige Analyse des Traffics auf Ihrer Site erforderlich sind. [!DNL Page Tags] sollten dann zur Erfassung der verbleibenden 10 % oder weniger der Traffic-Daten verwendet werden, die Ihren Webservern nicht bekannt sind. Die folgenden Konfigurationen sind jedoch für die Erfassung von Webanforderungsdaten von Ihrer Site gültig, wobei die Reihenfolge der Voreinstellungen auf unserer betrieblichen Erfahrung basiert:

1. [!DNL Sensor] auf jedem Webserver installiert ist, den Sie steuern und der Ihre Site unterstützt. Inhalte von Drittanbieter-Sites, aus dem Cache bereitgestellte Inhalte und bestimmte Arten von dynamischen Inhalten sollten mit Tags versehen werden. Solche Seiten-Tags sollten die erfassten Daten an einen Webserver an Ihrem Speicherort senden, auf dem [!DNL Sensor] ausgeführt wird. Sie können einen zusätzlichen Webserver hinzufügen, wenn der Anforderungstransfer auf der Ebene der Seiten-Tag-Anforderung dies rechtfertigt, oder in besonderen Fällen einen Webserver zur Erfassung dieser Seiten-Tag-Anforderungen zuweisen.
1. [!DNL Sensor] auf zwei Webservern installiert ist, die in diesem Handbuch auch als Datenerfassungsserver bezeichnet werden und die zum Sammeln von Seiten-Tag-Anforderungsdaten aus getaggten Seiten bestimmt sind. Der gesamte Inhalt auf Ihrer Site ist mit Tags versehen und alle Seiten-Tags werden an die beiden Datenerfassungsserver weitergeleitet.
1. [!DNL Sensor’s] Datenerfassungsdienste werden von einem Outsourcer bereitgestellt, der Datenerfassungsserver ausführt, um alle Webanforderungsdaten zu erfassen. In diesem Fall werden alle Inhalte auf Ihrer Site mit Tags versehen und die Seiten-Tags senden ihre Daten an die ausgelagerten Datenerfassungsserver.

   Weitere Informationen zu [!DNL Sensor] finden Sie in der *Data Workbench [!DNL Sensor] Guide*.
