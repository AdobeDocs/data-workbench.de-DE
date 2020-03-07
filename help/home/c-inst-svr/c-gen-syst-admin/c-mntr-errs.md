---
description: Um System- und Anwendungsfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignisprotokolle regelmäßig überwachen.
solution: Insight
title: Ereignisse für Fehler überwachen
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ereignisse für Fehler überwachen{#monitoring-events-for-errors}

Um System- und Anwendungsfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignisprotokolle regelmäßig überwachen.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Zur Überwachung Ihrer Adobe-Serversoftware-Produkte kann Ihr automatisiertes Verwaltungstool so eingestellt werden, dass das Ereignisprotokoll mit der Quelle &quot;Adobe&quot;auf Fehler hin überwacht wird. Anschließend werden die entsprechenden Mitarbeiter auf Probleme hingewiesen, die möglicherweise eine Intervention erfordern.

Unter Windows werden Anwendungsfehlermeldungen an das Anwendungsereignisprotokoll in Windows ausgegeben, auf das Sie mit der Windows-Ereignisanzeige zugreifen können. Unter Unix werden Anwendungsfehlermeldungen mithilfe der Funktion LOG_DAEMON an das Unix-Syslog ausgegeben.

**So öffnen Sie die Windows-Ereignisanzeige**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

