---
description: Die Tokenize-Transformation wendet iterativ einen regulären Ausdruck auf die Eingabestring an.
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 5%

---

# Tokenize{#tokenize}

Die Tokenize-Transformation wendet iterativ einen regulären Ausdruck auf die Eingabestring an.

Im Gegensatz zu [!DNL RETransform] muss [!DNL Tokenize] jedoch nicht mit der gesamten Zeichenfolge übereinstimmen: Der reguläre Ausdruck, der für die [!DNL Tokenize]-Transformation verwendet wird, kann mit einer Untergruppe der Eingabe übereinstimmen. Nachdem eine Übereinstimmung gefunden wurde, wendet [!DNL Tokenize] den regulären Ausdruck erneut an, beginnend mit dem Zeichen nach dem Ende der letzten Übereinstimmung.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Groß-/Kleinschreibung | Wahr oder falsch. Gibt an, ob bei der Übereinstimmung die Groß-/Kleinschreibung beachtet wird. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert entweder nicht verfügbar ist oder der reguläre Ausdruck nicht mit dem Eingabewert übereinstimmt. |  |
| Ausdruck | Der reguläre Ausdruck, der für die Übereinstimmung verwendet wird. |  |
| Ausgaben | Die Namen der Ausgabezeichenfolgen. Sie können mehrere Ausgaben für eine angegebene Eingabestaste haben. Die Anzahl der Ausgaben muss der Anzahl der erfassten Untermuster im regulären Ausdruck entsprechen. |  |

Im folgenden Beispiel verwendet die Transformation einen regulären Ausdruck, um die Namen der Abfragen-Zeichenfolgen (in cs-uri-Abfrage) zu erfassen und das erfasste Untermuster (den Namen der Abfrage) in x-ull-Abfrage-name auszugeben.[!DNL Tokenize]

![](assets/cfg_TransformationType_Tokenize.png)

Für die Abfrage-Zeichenfolge &quot;a=b&amp;c=d&quot;wäre die Ausgabe ein Vektor, der &quot;a&quot;und &quot;c&quot;enthält.

Informationen zu regulären Ausdrücken finden Sie unter [Reguläre Ausdruck](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
