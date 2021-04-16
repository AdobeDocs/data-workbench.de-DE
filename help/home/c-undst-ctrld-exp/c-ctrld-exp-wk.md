---
description: Bei einem Experiment können Sie zusätzlich zur Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.
solution: Analytics,Analytics
title: Wie funktionieren gesteuerte Experimente?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Wie funktionieren gesteuerte Experimente?{#how-do-controlled-experiments-work}

Bei einem Experiment können Sie zusätzlich zur Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.

Wenn ein Experiment ausgeführt wird, werden alle Besucher Ihrer Website Teil des Experiments, entweder als Teil einer Testgruppe oder der Kontrollgruppe, sobald sie auf eine der am Experiment beteiligten Seiten zugreifen. Besucher werden Ihren Experimentgruppen zufällig in den während der Experimentkonfiguration festgelegten Proportionen zugeordnet.

Kontrollierte Experimente werden mit der [!DNL Sensor]-Software implementiert, die auf jedem der Inhaltsserver im Web-Cluster installiert ist. Während die Inhaltsserver Anforderungen empfangen, wählt [!DNL Sensor] zufällig Besucher für Ihre Testgruppen aus und leitet ihre Seitenanforderungen an den experimentellen Inhalt weiter. Wenn [!DNL Sensor] einen Besucher zur Ansicht des Testinhalts auswählt, wird in der Adressleiste weiterhin der ursprünglich angeforderte URI Liste, der Besucher wird jedoch an den Test-URI weitergeleitet. Da dieser Prozess intern in der Serveranwendung stattfindet, sind sich die Benutzer nicht bewusst, wann sie getestet werden. Dies ist ein wichtiger Aspekt für unvoreingenommene Experimente.

[!DNL Sensor] übergibt die Test-URIs, nicht den ursprünglichen URI, der dem Benutzer angezeigt wird, an die Protokolldateien, die in der Analyse verwendet werden sollen.

Die Testergebnisse lassen sich einfach mit [!DNL Insight] analysieren, um festzustellen, ob die experimentelle Hypothese, die Sie getestet haben, korrekt ist.

>[!NOTE]
>
>Adobe empfiehlt dringend, dass kontrollierte Experimente mit Eingaben von Personen in Ihrem Unternehmen koordiniert und durchgeführt werden, die für die Konfiguration und Pflege Ihrer Analyse-Datensätze zuständig sind.
