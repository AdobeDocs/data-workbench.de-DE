---
description: Mit der Filterfunktion für Inhaltstypen von Sensor soll vermieden werden, Informationen zu speichern und zu verarbeiten, die für Analysezwecke nicht nützlich sind.
title: Filtern nach Content-Typ
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtern nach Content-Typ{#filtering-by-content-type}

Mit der Filterfunktion für Inhaltstypen von Sensor soll vermieden werden, Informationen zu speichern und zu verarbeiten, die für Analysezwecke nicht nützlich sind.

Ein Großteil der Anfragedaten, die über die API eines Webservers verfügbar sind, ist bei der Geschäftsanalyse nicht nützlich. Die Speicherung und Verarbeitung sind teuer, und die [!DNL Sensor’s] Inhaltsfilterung ermöglicht es Ihnen, unnötige Speicherung und Verarbeitung zu vermeiden.

Um die Leistung der Webprotokolldatenverarbeitung zu maximieren und die Menge der zu speichernden Messdaten zu reduzieren, erfasst [!DNL Site] Messdaten (Anfragedaten, Protokolleinträge, Protokolldaten usw.) für alle Webinhaltstypanfragen, mit Ausnahme von speziell aufgelisteten Inhaltstypen (wie Cascading Style Sheets, Bildanforderungen usw.), die herausgefiltert werden, bevor sie an den Data Workbench-Server gesendet werden. [!DNL Sensor] Diese Filterung kann für einen gesamten Webserver deaktiviert werden und auch für ein bestimmtes Inhaltsobjekt überschrieben werden, indem das Name-Wert-Paar &quot;Log=1&quot; zur Abfragezeichenfolge eines bestimmten eingebetteten Objekts hinzugefügt wird (z. B. [!DNL https://www.mysite.com/advertisement.gif?Log=1]).
