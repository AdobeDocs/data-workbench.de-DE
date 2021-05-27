---
description: Die PullNameValues-Umwandlung ist ein spezieller Vorgang, der die Werte im Feld cs-uri-query übernimmt und jedes Name-Wert-Paar in eine separate Zeichenfolge trennt.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

Die PullNameValues-Umwandlung ist ein spezieller Vorgang, der die Werte im Feld cs-uri-query übernimmt und jedes Name-Wert-Paar in eine separate Zeichenfolge trennt.

Die gesamte Sammlung von Name-Wert-Paar-Zeichenfolgen wird im angegebenen Ausgabefeld als Vektor von Zeichenfolgen ausgegeben.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert im angegebenen Protokolleintrag nicht verfügbar ist. |  |
| Ausgabe | Der Name der Ausgabezeichenfolge. |  |

Die Umwandlung [!DNL PullNameValues] wird in diesem Beispiel verwendet, um die Verwendung des Suchformulars durch Besucher zu erfassen: welche Schaltflächen ausgewählt wurden, welche Werte im Formular eingegeben wurden usw. Das Beispiel verwendet eine [!DNL String Match] -Bedingung (siehe [Bedingungen](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), um die Verwendung dieser Umwandlung auf die Seite [!DNL /search.php] zu isolieren. Der Vektor von Name-Wert-Paaren wird in das Feld x-search-namvalues ausgegeben.

![](assets/cfg_TransformationType_PullNameValues.png)

Verwenden Sie die Umwandlung wie oben definiert, wenn das cs-uri-Stammfeld mit der Seite [!DNL /search.php] übereinstimmt und cs-uri-query Folgendes enthielt:

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

dann enthalten x-search-namvalues einen Vektor, der die folgenden drei Zeichenfolgen enthält:

* searchFor=Bob
* state=Virginia
* isMale=true
