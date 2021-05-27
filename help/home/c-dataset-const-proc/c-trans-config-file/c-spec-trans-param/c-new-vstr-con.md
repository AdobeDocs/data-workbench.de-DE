---
description: Die Bedingung für neue Besucher ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher für die Aufnahme in den Datensatz berücksichtigt werden.
title: Bedingung für neuen Besucher
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Bedingung für neuen Besucher{#new-visitor-condition}

Die Bedingung für neue Besucher ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher für die Aufnahme in den Datensatz berücksichtigt werden.

Der [!DNL New Visitor Condition] definiert den ersten Protokolleintrag (geordnet nach Uhrzeit) für einen Besucher, der im Datensatz verwendet werden soll, und alle nachfolgenden Protokolleinträge für diesen Besucher werden in den Datensatz aufgenommen, unabhängig davon, ob sie diese Bedingung erfüllen. Da [!DNL New Visitor Condition] erfordert, dass Daten nach Besucher und Uhrzeit sortiert werden, werden sie nur während der Umwandlungsphase der Datensatzerstellung angewendet.

Der in diesem Beispiel dargestellte [!DNL New Visitor Condition] erstellt einen Datensatz, der nur die Protokolleinträge für Besucher enthält, die auf E-Mail-Kampagnen reagieren. Dies wird durch die Verwendung des Tests [!DNL NotEmptyCondition] (siehe [Nicht leer](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) und des Felds [!DNL x-campaign-email] als Eingabe für den regulären Ausdruck erreicht. Nachdem die neuen Besucher identifiziert wurden, die die Bedingung erfüllen, werden alle Protokolleinträge für diese Besucher erfasst.

![](assets/cfg_Transformation_NewVisitorCondition.png)
