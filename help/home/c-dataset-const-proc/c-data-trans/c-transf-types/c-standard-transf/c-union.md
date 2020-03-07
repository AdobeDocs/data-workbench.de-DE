---
description: Die Unionstransformation nimmt eine Reihe von Inputs und erstellt einen Vektor von Zeichenfolgen als Ausgabe.
solution: Analytics
title: Vereinigung
topic: Data workbench
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Vereinigung{#union}

Die Unionstransformation nimmt eine Reihe von Inputs und erstellt einen Vektor von Zeichenfolgen als Ausgabe.

Wenn einer der Eingaben selbst ein Vektor ist, wird jedes Element im Eingabe-Vektor mit einem Element im Ausgabevektor verknüpft (d. h., die Transformation erstellt keinen Vektor von Vektoren).

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingänge | Ein oder mehrere Eingabewerte. |  |
| Ausgabe | Der Name des Ausgabefelds. |  |

In diesem Beispiel werden Datenfelder aus dem Website-Traffic verwendet, um eine Liste der Postleitzahlen zu erstellen, die mit den Besuchern der Website verknüpft sind (d. h. innerhalb jedes Protokolleintrags). Die Daten bieten zwei mögliche Quellen für diese Informationen: eine in cs-uri-query und die andere in einem [!DNL zipcode] Feld des Cookies. Wenn keines dieser Felder eine Postleitzahl enthält, wird der Standardwert 00000 verwendet.

![](assets/cfg_TransformationType_Union.png)

Es ist zwar möglich, dass beide Werte in einem einzigen Protokolleintrag verfügbar sind, Sie können jedoch festlegen, welcher Wert verwendet werden soll, wenn Sie eine Dimension basierend auf der Ausgabe der Transformation erstellen. In einem typischen Anwendungsfall erstellen Sie eine einfache Dimension, die entweder den ersten oder den letzten der gefundenen Werte akzeptiert. Informationen zum Erstellen einfacher Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
