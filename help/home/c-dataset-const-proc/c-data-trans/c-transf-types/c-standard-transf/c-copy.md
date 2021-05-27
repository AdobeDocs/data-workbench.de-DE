---
description: Die Kopierumwandlung kopiert einfach den Wert im Eingabefeld in das angegebene Ausgabefeld. Wenn das Eingabefeld ein Vektor von Zeichenfolgen sein könnte, muss das Ausgabefeld mit "x-"beginnen.
title: Kopieren
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# Kopieren{#copy}

Die Kopierumwandlung kopiert einfach den Wert im Eingabefeld in das angegebene Ausgabefeld. Wenn das Eingabefeld ein Vektor von Zeichenfolgen sein könnte, muss das Ausgabefeld mit &quot;x-&quot;beginnen.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Wird verwendet, wenn der Bedingungstest wahr ist und der Eingabewert im angegebenen Protokolleintrag nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, aus dem kopiert werden soll. |  |
| Ausgabe | Der Name des Ausgabefelds. |  |

In diesem Beispiel, das Felder von Daten verwendet, die aus dem Website-Traffic erfasst wurden, wird das Ausgabefeld x-purchase-success den Literalwert &quot;1&quot;erhält, sobald cs-uri-Stamm [!DNL /checkout/confirmed.php] entspricht. Wenn das [!DNL Condition] nicht erfüllt ist (d. h., der cs-uri-Stamm stimmt nicht mit [!DNL /checkout/confirmed.php] überein), wird x-purchase-success nicht geändert.

![](assets/cfg_TransformationType_Copy.png)
