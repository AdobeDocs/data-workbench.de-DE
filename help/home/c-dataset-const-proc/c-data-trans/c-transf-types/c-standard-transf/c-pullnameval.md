---
description: Die PullNameValues-Transformation ist ein spezieller Vorgang, bei dem die Werte im cs-uri-Abfragefeld verwendet werden und jedes Name-Wert-Paar in eine separate Zeichenfolge getrennt wird.
solution: Analytics
title: PullNameValues
topic: Data workbench
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# PullNameValues{#pullnamevalues}

Die PullNameValues-Transformation ist ein spezieller Vorgang, bei dem die Werte im cs-uri-Abfragefeld verwendet werden und jedes Name-Wert-Paar in eine separate Zeichenfolge getrennt wird.

Die gesamte Sammlung von Name-Wert-Paarzeichenfolgen wird im angegebenen Ausgabefeld als Vektor von Zeichenfolgen ausgegeben.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert im angegebenen Protokolleintrag nicht verfügbar ist. |  |
| Ausgabe | Der Name der Ausgabezeichenfolge. |  |

Die [!DNL PullNameValues] Transformation wird in diesem Beispiel verwendet, um die Verwendung des Suchformulars durch Besucher zu erfassen: Welche Schaltflächen wurden ausgewählt, welche Werte wurden im Formular eingegeben usw. Das Beispiel verwendet eine [!DNL String Match] Bedingung (siehe [Bedingungen](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), um die Verwendung dieser Transformation nur auf die Seite zu isolieren [!DNL /search.php]. Der Vektor der Name-Wert-Paare wird in die Werte des Felds x-search-names ausgegeben.

![](assets/cfg_TransformationType_PullNameValues.png)

Bei Verwendung der oben definierten Transformation, wenn das cs-uri-Stammfeld mit der Seite übereinstimmt [!DNL /search.php] und cs-uri-Abfrage Folgendes enthielt:

* SearchFor=Bob&amp;State=Virginia&amp;isMale=true

dann enthalten x-search-names-Werte einen Vektor, der die folgenden drei Zeichenfolgen enthält:

* search=Bob
* Bundesland=Virginia
* isMale=true

