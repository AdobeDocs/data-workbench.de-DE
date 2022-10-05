---
description: Die ReplaceURI-Transformation ändert den Wert in der internen URI-Dimension in einen neuen Wert.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

{{eol}}

Die ReplaceURI-Transformation ändert den Wert in der internen URI-Dimension in einen neuen Wert.

Wenn [!DNL URI Prefix] angegeben ist, ist der resultierende Wert einfach das mit dem bereitgestellten Eingabewert verkettete URI-Präfix.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Wert, der den URI ersetzen soll. |  |
| URI-Präfix | Der Wert (Zeichenfolge), der dem Wert im [!DNL Input] -Feld. |  |

>[!NOTE]
>
>Vor der Anwendung [!DNL ReplaceURI] Transformationen erstellen, sollten Sie eine neue einfache Dimension mit einem übergeordneten Element von [!DNL Page View]von einer Kopie des cs-uri-Stamms oder cs-uri. Wenden Sie sich für Unterstützung an die Adobe.

Dieses Beispiel zeigt die Verwendung von [!DNL ReplaceURI] , um &quot;page=&quot;zu ersetzen.*pageid*&quot;Abfragezeichenfolgen mit &quot; [!DNL homepage.html]immer *pageid* gibt an, dass die Homepage der Website angezeigt wurde. Das Endergebnis ist eine benutzerfreundlichere Ansicht des URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Für die angezeigte Umwandlung wird die Seite

* [!DNL www.examplesite.com/info.html?page=1550]

geändert werden

* [!DNL www.examplesite.com/homepage.html]
