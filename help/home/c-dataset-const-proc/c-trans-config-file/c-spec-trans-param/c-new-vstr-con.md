---
description: Die Bedingung für neue Besucher ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher für die Aufnahme in den Datensatz berücksichtigt werden.
title: Bedingung für neuen Besucher
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Bedingung für neuen Besucher{#new-visitor-condition}

{{eol}}

Die Bedingung für neue Besucher ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher für die Aufnahme in den Datensatz berücksichtigt werden.

Die [!DNL New Visitor Condition] definiert den ersten Protokolleintrag (geordnet nach Zeit) für einen Besucher, der im Datensatz verwendet werden soll, und alle nachfolgenden Protokolleinträge für diesen Besucher werden in den Datensatz aufgenommen, unabhängig davon, ob sie diese Bedingung erfüllen. Da die [!DNL New Visitor Condition] erfordert, dass die Daten nach Besucher und Uhrzeit sortiert werden, wird sie nur während der Transformationsphase der Datensatzerstellung angewendet.

Die [!DNL New Visitor Condition] In diesem Beispiel wird ein Datensatz erstellt, der nur die Protokolleinträge für Besucher enthält, die auf E-Mail-Kampagnen reagieren. Dies wird durch die Verwendung von [!DNL NotEmptyCondition] Test (siehe [Nicht leer](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) und der [!DNL x-campaign-email] als Eingabe für den regulären Ausdruck. Nachdem die neuen Besucher identifiziert wurden, die die Bedingung erfüllen, werden alle Protokolleinträge für diese Besucher erfasst.

![](assets/cfg_Transformation_NewVisitorCondition.png)
