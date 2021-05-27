---
description: Die Tokenize-Transformation wendet iterativ einen regulären Ausdruck auf die Eingabezeichenfolge an.
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 5%

---

# Tokenize{#tokenize}

Die Tokenize-Transformation wendet iterativ einen regulären Ausdruck auf die Eingabezeichenfolge an.

Im Gegensatz zu [!DNL RETransform] muss [!DNL Tokenize] jedoch nicht mit der gesamten Zeichenfolge übereinstimmen: Der reguläre Ausdruck, der für die Umwandlung von [!DNL Tokenize] verwendet wird, kann mit einer Teilmenge der Eingabe übereinstimmen. Nachdem eine Übereinstimmung gefunden wurde, wendet [!DNL Tokenize] den regulären Ausdruck erneut an, beginnend mit dem Zeichen nach dem Ende der letzten Übereinstimmung.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Groß-/Kleinschreibung | Wahr oder falsch. Gibt an, ob bei der Übereinstimmung zwischen Groß- und Kleinschreibung unterschieden wird. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert entweder nicht verfügbar ist oder der reguläre Ausdruck nicht mit dem Eingabewert übereinstimmt. |  |
| Ausdruck | Der reguläre Ausdruck, der für die Zuordnung verwendet wird. |  |
| Ausgaben | Die Namen der Ausgabezeichenfolgen. Sie können für eine bestimmte Eingabezeichenfolge mehrere Ausgaben haben. Die Anzahl der Ausgaben muss der Anzahl der erfassten Untermuster im regulären Ausdruck entsprechen. |  |

Im folgenden Beispiel verwendet die Umwandlung [!DNL Tokenize] einen regulären Ausdruck, um die Namen der Abfragezeichenfolgen (in cs-uri-query) zu erfassen und das erfasste Untermuster (den Abfragenamen) in x-ull-query-name auszugeben.

![](assets/cfg_TransformationType_Tokenize.png)

Für die Abfragezeichenfolge &quot;a=b&amp;c=d&quot;wäre die Ausgabe ein Vektor, der &quot;a&quot;und &quot;c&quot;enthält.

Weitere Informationen zu regulären Ausdrücken finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
