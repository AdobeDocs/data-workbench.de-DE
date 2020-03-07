---
description: Der Zweck der Sensor-Filterfunktion ist es, die Speicherung und Verarbeitung von Informationen, die für Analysezwecke nicht nützlich sind, zu vermeiden.
solution: Analytics
title: Filtern nach Inhaltstyp
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtern nach Inhaltstyp{#filtering-by-content-type}

Der Zweck der Sensor-Filterfunktion ist es, die Speicherung und Verarbeitung von Informationen, die für Analysezwecke nicht nützlich sind, zu vermeiden.

Ein Großteil der Anforderungsdaten, die über die API eines Webservers verfügbar sind, ist bei der Geschäftsanalyse nicht hilfreich. Die Speicherung und Verarbeitung sind teuer, und mit der Filterung von [!DNL Sensor’s] Inhalten können Sie unnötige Speicherung und Verarbeitung vermeiden.

Um die Verarbeitungsleistung der Webprotokolldaten zu maximieren und die Menge der zu speichernden Messungsdaten zu reduzieren, werden [!DNL Site] Messungsdaten (Anforderungsdaten, Protokolleinträge, Protokolldaten usw.) für alle Webinhaltstypanforderungen erfasst, mit Ausnahme der speziell aufgeführten Inhaltstypen (wie Cascading Stylesheets, Bildanforderungen usw.), die herausgefiltert werden, bevor sie vom Data Workbench-Server an den Server übermittelt werden [!DNL Sensor]. Diese Filterung kann für einen gesamten Webserver deaktiviert werden. Sie kann auch für ein bestimmtes Inhaltsobjekt überschrieben werden, indem das Namens-Wert-Paar &quot;Log=1&quot;zur Abfragezeichenfolge eines bestimmten eingebetteten Objekts hinzugefügt wird (z. B. [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
