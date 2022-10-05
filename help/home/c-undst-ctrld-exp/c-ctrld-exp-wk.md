---
description: In einem Experiment können Sie zusätzlich zur Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.
solution: Analytics
title: Wie funktionieren gesteuerte Experimente?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Wie funktionieren gesteuerte Experimente?{#how-do-controlled-experiments-work}

{{eol}}

In einem Experiment können Sie zusätzlich zur Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.

Wenn ein Experiment ausgeführt wird, werden alle Besucher Ihrer Website Teil des Experiments, entweder als Teil einer Testgruppe oder der Kontrollgruppe, sobald sie auf eine am Experiment beteiligte Seite zugreifen. Die Besucher werden Ihren Experimentgruppen zufällig in den während der Experimentkonfiguration definierten Proportionen zugeordnet.

Kontrollierte Experimente werden mit dem [!DNL Sensor] Software, die auf jedem der Inhaltsserver in Ihrem Webcluster installiert ist. Wenn die Inhaltsserver Anfragen erhalten, [!DNL Sensor] wählt zufällig Besucher für Ihre Testgruppen aus und leitet ihre Seitenanforderungen an den experimentellen Inhalt weiter. Wann [!DNL Sensor] wählt einen Besucher aus, um den Testinhalt anzuzeigen. Die Adressleiste listet weiterhin den ursprünglich angeforderten URI auf, der Besucher wird jedoch zum Test-URI weitergeleitet. Da dieser Prozess intern in der Server-Anwendung stattfindet, wissen die Benutzer nicht, wann sie getestet werden. Dies ist eine wichtige Überlegung für unparteiische Experimente.

[!DNL Sensor] übergibt die Test-URIs, nicht den ursprünglichen URI, der dem Benutzer angezeigt wird, an die Protokolldateien, die in der Analyse verwendet werden sollen.

Die Ergebnisse der Experimente lassen sich einfach analysieren, indem Sie [!DNL Insight] um festzustellen, ob die von Ihnen getestete experimentelle Hypothese korrekt ist.

>[!NOTE]
>
>Adobe empfiehlt dringend, dass kontrollierte Experimente mit Beiträgen von Personen in Ihrem Unternehmen koordiniert und durchgeführt werden, die für die Konfiguration und Verwaltung Ihrer Analysedatensätze zuständig sind.
