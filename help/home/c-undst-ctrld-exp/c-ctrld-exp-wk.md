---
description: In einem Experiment können Sie zusätzlich zur Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.
solution: Analytics,Analytics
title: Wie funktionieren gesteuerte Experimente?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Wie funktionieren gesteuerte Experimente?{#how-do-controlled-experiments-work}

In einem Experiment können Sie zusätzlich zur Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.

Wenn ein Experiment ausgeführt wird, werden alle Besucher Ihrer Website Teil des Experiments, entweder als Teil einer Testgruppe oder der Kontrollgruppe, sobald sie auf eine am Experiment beteiligte Seite zugreifen. Die Besucher werden Ihren Experimentgruppen zufällig in den während der Experimentkonfiguration definierten Proportionen zugeordnet.

Kontrollierte Experimente werden mit der [!DNL Sensor]-Software implementiert, die auf jedem der Inhaltsserver in Ihrem Webcluster installiert ist. Während die Inhaltsserver Anforderungen empfangen, wählt [!DNL Sensor] zufällig Besucher für Ihre Testgruppen aus und leitet ihre Seitenanfragen an den experimentellen Inhalt weiter. Wenn [!DNL Sensor] einen Besucher auswählt, der den Testinhalt anzeigt, wird in der Adressleiste weiterhin der ursprünglich angeforderte URI aufgelistet, der Besucher wird jedoch zum Test-URI weitergeleitet. Da dieser Prozess intern in der Server-Anwendung stattfindet, wissen die Benutzer nicht, wann sie getestet werden. Dies ist eine wichtige Überlegung für unparteiische Experimente.

[!DNL Sensor] übergibt die Test-URIs, nicht den ursprünglichen URI, der dem Benutzer angezeigt wird, an die Protokolldateien, die in der Analyse verwendet werden sollen.

Die Ergebnisse der Experimente können einfach mit [!DNL Insight] analysiert werden, um festzustellen, ob die von Ihnen getestete Versuchshypothese korrekt ist.

>[!NOTE]
>
>Adobe empfiehlt dringend, dass kontrollierte Experimente mit Beiträgen von Personen in Ihrem Unternehmen koordiniert und durchgeführt werden, die für die Konfiguration und Verwaltung Ihrer Analysedatensätze zuständig sind.
