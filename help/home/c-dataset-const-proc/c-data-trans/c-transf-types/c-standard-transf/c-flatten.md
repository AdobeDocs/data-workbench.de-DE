---
description: Die Flatten-Transformation nimmt einen Vektor von Zeichenfolgen und ordnet jeden Wert einem eigenen Feld zu.
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Flatten{#flatten}

Die Flatten-Transformation nimmt einen Vektor von Zeichenfolgen und ordnet jeden Wert einem eigenen Feld zu.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert für den Protokolleintrag nicht verfügbar ist. |  |
| Eingabe | Ein Vektor von Zeichenfolgenwerten, der den Ausgabefeld-Namen zugeordnet werden soll. |  |
| Ausgaben | Eine Gruppe von Ausgabefeld-Namen. |  |

Überlegungen zu [!DNL Flatten]

* Wenn der EingabekVektor mehr Werte enthält als definierte Ausgabefelder, werden die zusätzlichen Eingabewerte einfach abgelegt.
* Wenn der EingabekVektor weniger Werte enthält als definierte Ausgabefelder, erhalten die zusätzlichen Ausgabefelder den Standardwert (sofern definiert) oder eine leere Zeichenfolge, wenn kein Standardwert definiert ist.

Hier wird die [!DNL Flatten]-Transformation verwendet, um einen Vektor von Produkten (x-products) zu nehmen und sie in vier Felder zu unterteilen (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Wenn der Eingabewert die Zeichenfolgen B57481, C46355 und Z97123 enthielt, weisen die Ausgabefelder die folgenden Werte auf:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Leer (Es gibt mehr Eingaben als Ausgaben, und es ist kein Standardwert angegeben.)
