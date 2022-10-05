---
description: Um System- und Anwendungsfehler so bald wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignisprotokolle regelmäßig überwachen.
title: Überwachen von Ereignissen zum Ausmachen von Fehlern
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---

# Überwachen von Ereignissen zum Ausmachen von Fehlern{#monitoring-events-for-errors}

{{eol}}

Um System- und Anwendungsfehler so bald wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignisprotokolle regelmäßig überwachen.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Um Ihre Adobe Server-Softwareprodukte zu überwachen, kann Ihr automatisiertes Management-Tool so eingerichtet sein, dass es Ihr Ereignisprotokoll auf Fehler mit der &quot;Adobe&quot;überwacht und dann geeignete Mitarbeiter auf Probleme aufmerksam macht, die möglicherweise bekämpft werden müssen.

Unter Windows werden Anwendungsfehlermeldungen an das Application Event Log in Windows ausgegeben, auf das Sie über die Windows Event Viewer zugreifen können. In Unix werden Anwendungsfehlermeldungen mithilfe der LOG_DAEMON-Funktion an das Unix-Syslog ausgegeben.

**So öffnen Sie den Windows Event Viewer**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
