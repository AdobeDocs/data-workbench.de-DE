---
description: Die Kopiertransformation kopiert den Wert im Eingabefeld einfach in das angegebene Ausgabefeld. Wenn das Eingabefeld ein Vektor von Zeichenfolgen sein könnte, muss das Ausgabefeld mit "x-"beginnen.
solution: Analytics
title: Kopieren
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Kopieren{#copy}

Die Kopiertransformation kopiert den Wert im Eingabefeld einfach in das angegebene Ausgabefeld. Wenn das Eingabefeld ein Vektor von Zeichenfolgen sein könnte, muss das Ausgabefeld mit &quot;x-&quot;beginnen.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Wird verwendet, wenn der Bedingungstest &quot;true&quot;ist und der Eingabewert im angegebenen Protokolleintrag nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, aus dem kopiert werden soll. |  |
| Ausgabe | Der Name des Ausgabefelds. |  |

In diesem Beispiel, in dem Felder von Daten verwendet werden, die aus Website-Traffic gesammelt wurden, erhält das Ausgabefeld x-purchase-success den Literalwert &quot;1&quot;, sobald cs-uri-stamm übereinstimmt [!DNL /checkout/confirmed.php]. Wenn das [!DNL Condition] nicht zufrieden ist (d. h., dass cs-uri-stamm nicht übereinstimmt), wird der x-purchase-success nicht geändert [!DNL /checkout/confirmed.php].

![](assets/cfg_TransformationType_Copy.png)

