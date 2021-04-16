---
description: Bei der PullNameValues-Transformation handelt es sich um einen speziellen Vorgang, bei dem die Werte im Feld cs-uri-Abfrage übernommen werden und jedes Name-Wert-Paar in eine separate Zeichenfolge getrennt wird.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

Bei der PullNameValues-Transformation handelt es sich um einen speziellen Vorgang, bei dem die Werte im Feld cs-uri-Abfrage übernommen werden und jedes Name-Wert-Paar in eine separate Zeichenfolge getrennt wird.

Die gesamte Sammlung von Name-Wert-Paarzeichenfolgen wird im angegebenen Ausgabefeld als Vektor von Zeichenfolgen ausgegeben.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert im angegebenen Protokolleintrag nicht verfügbar ist. |  |
| Ausgabe | Der Name der Ausgabezeichenfolge. |  |

Die [!DNL PullNameValues]-Transformation wird in diesem Beispiel verwendet, um die Verwendung des Suchformulars durch Besucher zu erfassen: Welche Schaltflächen wurden ausgewählt, welche Werte wurden im Formular eingegeben usw. Im Beispiel wird eine [!DNL String Match]-Bedingung (siehe [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) verwendet, um die Verwendung dieser Transformation nur auf die Seite [!DNL /search.php] zu isolieren. Der Vektor der Name-Wert-Paare wird in die Werte des Felds x-search-names ausgegeben.

![](assets/cfg_TransformationType_PullNameValues.png)

Bei Verwendung der oben definierten Transformation, wenn das cs-uri-Stammfeld mit der Seite [!DNL /search.php] und der cs-uri-Abfrage übereinstimmt, die Folgendes enthält:

* SearchFor=Bob&amp;State=Virginia&amp;isMale=true

dann enthalten x-search-names-Werte einen Vektor, der die folgenden drei Zeichenfolgen enthält:

* search=Bob
* Bundesland=Virginia
* isMale=true
