---
description: Um System- und Anwendungsfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignis-Protokolle regelmäßig überwachen.
solution: Analytics
title: Überwachen von Ereignissen zum Ausmachen von Fehlern
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---


# Überwachen von Ereignissen zum Ausmachen von Fehlern{#monitoring-events-for-errors}

Um System- und Anwendungsfehler so schnell wie möglich zu erkennen und zu beheben, bevor sie zu größeren Problemen oder Ausfällen führen, sollten Sie Ihre Ereignis-Protokolle regelmäßig überwachen.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Zur Überwachung Ihrer Adobe-Server-Softwareprodukte kann Ihr automatisiertes Management-Tool so eingestellt werden, dass Ihr Ereignis-Protokoll auf Fehler mit der Quell-&quot;Adobe&quot; überwacht und dann entsprechende Mitarbeiter auf Probleme aufmerksam gemacht werden, die möglicherweise eine Intervention erfordern.

Unter Windows werden Anwendungsfehlermeldungen an das Application Ereignis Log in Windows ausgegeben, auf das Sie mit dem Windows Ereignis Viewer zugreifen können. Unter Unix werden Anwendungsfehlermeldungen mithilfe der Funktion LOG_DAEMON an das Unix-Syslog ausgegeben.

**So öffnen Sie den Windows Ereignis Viewer**

* Klicken Sie auf **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

