---
description: Die Umwandlung der Union nimmt eine Reihe von Eingaben auf und erzeugt einen Vektor von Zeichenfolgen als Ausgabe.
title: Union
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Vereinigung{#union}

{{eol}}

Die Umwandlung der Union nimmt eine Reihe von Eingaben auf und erzeugt einen Vektor von Zeichenfolgen als Ausgabe.

Wenn einer der Eingaben selbst ein Vektor ist, wird jedes Element im Eingabevektor mit einem Element im Ausgabekvektor verknüpft (d. h. die Transformation erstellt keinen Vektor von Vektoren).

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingaben | Ein oder mehrere Eingabewerte. |  |
| Ausgabe | Der Name des Ausgabefelds. |  |

In diesem Beispiel werden Datenfelder aus dem Website-Traffic verwendet, um eine Liste der Postleitzahlen zu erstellen, die mit den Besuchern der Website verknüpft sind (d. h. innerhalb jedes Protokolleintrags). Die Daten bieten zwei mögliche Quellen für diese Informationen: einen in der cs-uri-Abfrage und den anderen in einer [!DNL zipcode] -Feld des Cookies. Wenn keines dieser Felder eine Postleitzahl enthält, wird der Standardwert 0000 verwendet.

![](assets/cfg_TransformationType_Union.png)

Diese beiden Werte können zwar in einem einzigen Protokolleintrag verfügbar sein, Sie können aber festlegen, welcher Wert bei der Erstellung einer Dimension auf der Grundlage der Transformationsausgabe verwendet werden soll. In einem typischen Anwendungsfall würden Sie eine einfache Dimension erstellen, die entweder den ersten oder den letzten der aufgefundenen Werte annimmt. Informationen zum Erstellen einfacher Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
