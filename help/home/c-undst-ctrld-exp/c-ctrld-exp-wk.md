---
description: In einem Experiment können Sie neben der Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.
solution: Insight,Analytics
title: Wie funktionieren kontrollierte Experimente?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Wie funktionieren kontrollierte Experimente?{#how-do-controlled-experiments-work}

In einem Experiment können Sie neben der Kontrollgruppe eine beliebige Anzahl von Testgruppen definieren.

Wenn ein Experiment ausgeführt wird, werden alle Besucher Ihrer Website Teil des Experiments, entweder als Teil einer Testgruppe oder der Kontrollgruppe, sobald sie auf eine Seite zugreifen, die am Experiment beteiligt ist. Besucher werden Ihren Experimentgruppen zufällig in den während der Experimentkonfiguration festgelegten Proportionen zugeordnet.

Kontrollierte Experimente werden mit der [!DNL Sensor] Software implementiert, die auf jedem Inhaltsserver im Web-Cluster installiert ist. Während die Inhaltsserver Anforderungen erhalten, wählt [!DNL Sensor] sie nach dem Zufallsprinzip Besucher für Ihre Testgruppen aus und leitet ihre Seitenanforderungen an den experimentellen Inhalt weiter. Wenn ein Besucher zum Anzeigen des Testinhalts [!DNL Sensor] ausgewählt wird, wird in der Adressleiste weiterhin der ursprünglich angeforderte URI aufgeführt, der Besucher wird jedoch zum Test-URI weitergeleitet. Da dieser Prozess intern in der Serveranwendung stattfindet, sind sich die Benutzer nicht bewusst, wann sie getestet werden. Dies ist ein wichtiger Aspekt für eine unvoreingenommene Experimentierung.

[!DNL Sensor] übergibt die Test-URIs, nicht den ursprünglichen URI, der dem Benutzer angezeigt wird, an die Protokolldateien, die für die Analyse verwendet werden sollen.

Die Ergebnisse der Experimente können leicht analysiert werden, [!DNL Insight] um festzustellen, ob die Versuchshypothese, die Sie getestet haben, korrekt ist.

>[!NOTE]
>
>Adobe empfiehlt dringend, dass kontrollierte Experimente mit Eingaben von Personen in Ihrem Unternehmen koordiniert und durchgeführt werden, die für die Konfiguration und Verwaltung Ihrer Analysedatensätze zuständig sind.

