---
description: Die ReplaceURI-Transformation ändert den Wert in der internen URI-Dimension in einen neuen Wert.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

Die ReplaceURI-Transformation ändert den Wert in der internen URI-Dimension in einen neuen Wert.

Wenn [!DNL URI Prefix] angegeben ist, wird lediglich das mit dem bereitgestellten Eingabewert verkettete URI-Präfix zurückgegeben.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Wert, der den URI ersetzen soll. |  |
| URI-Präfix | Der Wert (Zeichenfolge), der dem Wert im Feld [!DNL Input] vorangestellt werden soll. |  |

>[!NOTE]
>
>Bevor Sie [!DNL ReplaceURI]-Transformationen anwenden, sollten Sie eine neue einfache Dimension mit einem übergeordneten Element von [!DNL Page View]aus einer Kopie des cs-uri-Stammes oder cs-uri erstellen. Wenden Sie sich zwecks Hilfe an die Adobe.

In diesem Beispiel wird die Verwendung von [!DNL ReplaceURI] zum Ersetzen der Abfrage-Zeichenfolgen &quot;page=*pageid*&quot;durch [!DNL homepage.html]&quot;veranschaulicht, wenn *pageid* angibt, dass die Homepage der Website angezeigt wurde. Das Endergebnis ist eine benutzerfreundlichere Ansicht des URIs.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Für die angezeigte Transformation wird die Seite

* [!DNL www.examplesite.com/info.html?page=1550]

geändert werden

* [!DNL www.examplesite.com/homepage.html]
