---
description: Die Kopiertransformation kopiert den Wert im Eingabefeld einfach in das angegebene Ausgabefeld. Wenn das Eingabefeld ein Vektor von Zeichenfolgen sein könnte, muss das Ausgabefeld mit "x-"Beginn werden.
title: Kopieren
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# Kopieren{#copy}

Die Kopiertransformation kopiert den Wert im Eingabefeld einfach in das angegebene Ausgabefeld. Wenn das Eingabefeld ein Vektor von Zeichenfolgen sein könnte, muss das Ausgabefeld mit &quot;x-&quot;Beginn werden.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Wird verwendet, wenn der Bedingungstest &quot;true&quot;ist und der Eingabewert im angegebenen Protokolleintrag nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, aus dem kopiert werden soll. |  |
| Ausgabe | Der Name des Ausgabefelds. |  |

In diesem Beispiel, in dem Felder von Daten verwendet werden, die aus Website-Traffic gesammelt wurden, erhält das Ausgabefeld x-purchase-success den Literalwert &quot;1&quot;, sobald cs-uri-stamm [!DNL /checkout/confirmed.php] entspricht. Wenn das [!DNL Condition] nicht zufrieden ist (d. h., der cs-uri-Stamm stimmt nicht mit [!DNL /checkout/confirmed.php] überein), wird x-purchase-success nicht geändert.

![](assets/cfg_TransformationType_Copy.png)
