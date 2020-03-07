---
description: Die Tokenize-Transformation wendet iterativ einen regulären Ausdruck gegen die Eingabestring an.
solution: Analytics
title: Tokenize
topic: Data workbench
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tokenize{#tokenize}

Die Tokenize-Transformation wendet iterativ einen regulären Ausdruck gegen die Eingabestring an.

Anders als [!DNL RETransform]bei [!DNL Tokenize] der gesamten Zeichenfolge müssen Sie jedoch Folgendes beachten: der für die [!DNL Tokenize] Transformation verwendete reguläre Ausdruck kann mit einer Teilmenge der Eingabe übereinstimmen. Nachdem eine Übereinstimmung gefunden wurde, [!DNL Tokenize] wendet den regulären Ausdruck erneut an, beginnend mit dem Zeichen nach dem Ende der letzten Übereinstimmung.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Groß-/Kleinschreibung | True oder false. Gibt an, ob bei der Übereinstimmung die Groß-/Kleinschreibung beachtet wird. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert entweder nicht verfügbar ist oder der reguläre Ausdruck nicht mit dem Eingabewert übereinstimmt. |  |
| Ausdruck | Der reguläre Ausdruck, der für die Übereinstimmung verwendet wird. |  |
| Ausgaben | Die Namen der Ausgabezeichenfolgen. Sie können mehrere Ausgaben für eine angegebene Eingabestaste haben. Die Anzahl der Ausgaben muss der Anzahl der erfassten Submuster im regulären Ausdruck entsprechen. |  |

Im folgenden Beispiel verwendet die [!DNL Tokenize] Transformation einen regulären Ausdruck, um die Namen der Abfragezeichenfolgen (in cs-uri-query) zu erfassen und das erfasste Submuster (den Abfragenamen) an den x-ull-query-name auszugeben.

![](assets/cfg_TransformationType_Tokenize.png)

Für die Abfragezeichenfolge &quot;a=b&amp;c=d&quot;wäre die Ausgabe ein Vektor, der &quot;a&quot;und &quot;c&quot;enthält.

Weitere Informationen zu regulären Ausdrücken finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
