---
description: Die ReplaceURI-Transformation ändert den Wert in der internen URI-Dimension in einen neuen Wert.
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

Die ReplaceURI-Transformation ändert den Wert in der internen URI-Dimension in einen neuen Wert.

Wenn [!DNL URI Prefix] angegeben wird, ist der resultierende Wert einfach das URI-Präfix, das mit dem bereitgestellten Eingabewert verkettet ist.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Wert, der den URI ersetzen soll. |  |
| URI-Präfix | Der Wert (Zeichenfolge), der dem Wert im [!DNL Input] Feld vorangestellt werden soll. |  |

>[!NOTE]
>
>Bevor Sie [!DNL ReplaceURI] Transformationen anwenden, sollten Sie eine neue einfache Dimension mit einem übergeordneten Element [!DNL Page View]aus einer Kopie des cs-uri-Stammes oder cs-uri erstellen. Wenden Sie sich zwecks Unterstützung an Adobe.

In diesem Beispiel wird die Verwendung von [!DNL ReplaceURI] zum Ersetzen der Abfragezeichenfolgen &quot;page=*pageid*&quot;durch &quot; [!DNL homepage.html]&quot;veranschaulicht, wenn *pageid* anzeigt, dass die Homepage der Website angezeigt wurde. Das Endergebnis ist eine benutzerfreundlichere Ansicht des URIs.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Für die angezeigte Transformation wird die Seite

* [!DNL www.examplesite.com/info.html?page=1550]

geändert werden

* [!DNL www.examplesite.com/homepage.html]

