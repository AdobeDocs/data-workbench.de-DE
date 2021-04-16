---
description: Die Bedingung "Neuer Besucher"ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher in den Datensatz aufgenommen werden sollen.
title: Bedingung für neuen Besucher
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Bedingung für neuen Besucher{#new-visitor-condition}

Die Bedingung &quot;Neuer Besucher&quot;ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher in den Datensatz aufgenommen werden sollen.

Das [!DNL New Visitor Condition] definiert den ersten Protokolleintrag (sortiert nach Uhrzeit) für einen Besucher, der im Datensatz verwendet werden soll, und alle nachfolgenden Protokolleinträge für diesen Besucher werden in den Datensatz aufgenommen, unabhängig davon, ob sie diese Bedingung erfüllen. Da das [!DNL New Visitor Condition] erfordert, dass die Daten nach Besucher und Uhrzeit sortiert werden, werden sie nur während der Umwandlungsphase der Datensatzkonstruktion angewendet.

Das in diesem Beispiel dargestellte [!DNL New Visitor Condition] erstellt ein Dataset, das nur die Protokolleinträge für Besucher enthält, die auf E-Mail-Kampagnen reagieren. Dies wird erreicht, indem der [!DNL NotEmptyCondition]-Test (siehe [Nicht leer](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) und das [!DNL x-campaign-email]-Feld als Eingabe für den regulären Ausdruck verwendet werden. Nachdem die neuen Besucher, die die Bedingung erfüllen, identifiziert wurden, werden alle Protokolleinträge für diese Besucher erfasst.

![](assets/cfg_Transformation_NewVisitorCondition.png)
