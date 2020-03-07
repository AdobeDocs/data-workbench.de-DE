---
description: Bei der Unescape-URI-Transformation werden alle Zeichen in einer Zeichenfolge, die mit Escape-Zeichen versehen wurden, entschlüsselt.
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# UnescapeURI{#unescapeuri}

Bei der Unescape-URI-Transformation werden alle Zeichen in einer Zeichenfolge, die mit Escape-Zeichen versehen wurden, entschlüsselt.

>[!NOTE]
>
>Escapezeichen ersetzen die unsicheren Zeichen in einer URI-Zeichenfolge. Sie werden durch ein Dreieck dargestellt, das aus einem Prozentzeichen gefolgt von zwei hexadezimalen Ziffern besteht (z. B. %20).

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Die zu entschließende URI-Zeichenfolge. |  |
| Ausgabe | Der Name des Felds, in dem die Zeichenfolge ohne Escape gespeichert werden soll. |  |

Die folgende Transformation hebt die Escape-Escape-Sequenzen des Werts docname in einem HTTP-Header-Feld auf und speichert die Ausgabe im Feld x-docname-unescaped:

![](assets/cfg_TransformationType_UnescapeURI.png)

Wenn der Wert docname

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

der Wert von x-docname-unescape

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

