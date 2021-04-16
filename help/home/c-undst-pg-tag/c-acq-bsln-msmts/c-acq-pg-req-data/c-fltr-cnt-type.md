---
description: Die Filterfunktion von Sensor für Inhaltstypen soll verhindern, dass Informationen gespeichert und verarbeitet werden müssen, die für die Analyse nicht nützlich sind.
title: Filtern nach Content-Typ
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtern nach Content-Typ{#filtering-by-content-type}

Die Filterfunktion von Sensor für Inhaltstypen soll verhindern, dass Informationen gespeichert und verarbeitet werden müssen, die für die Analyse nicht nützlich sind.

Ein Großteil der Anforderungsdaten, die über die API eines Webservers verfügbar sind, ist bei der geschäftlichen Analyse nicht hilfreich. Datenspeicherung und Verarbeitung sind teuer, und mit der [!DNL Sensor’s]-Inhaltsfilter können Sie unnötige Datenspeicherung und Verarbeitung vermeiden.

Um die Verarbeitungsleistung der Webprotokolldaten zu maximieren und die Menge der zu speichernden Messdaten zu reduzieren, erfasst [!DNL Site] Messungsdaten (Anforderungsdaten, Protokolleinträge, Protokolldaten usw.) für alle Webinhalt-Typ-Anforderungen, mit Ausnahme der speziell aufgeführten Inhaltstypen (wie Cascading Style Sheets, Image-Anforderungen usw.), die herausgefiltert werden, bevor sie von [!DNL Sensor] an den Data Workbench-Server übermittelt werden. Diese Filterung kann für einen gesamten Webserver deaktiviert werden. Sie kann auch für ein bestimmtes Inhaltsobjekt überschrieben werden, indem das Namens-Wert-Paar &quot;Log=1&quot;zur Abfrage-Zeichenfolge eines bestimmten eingebetteten Objekts hinzugefügt wird (z. B. [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
