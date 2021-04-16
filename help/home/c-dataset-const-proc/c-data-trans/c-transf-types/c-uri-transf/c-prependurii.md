---
description: Ähnlich wie bei der AppendURI-Transformation wirkt sich die PrependURI-Transformation auf das interne Feld aus, das vom Data Workbench-Server zum Erstellen der URI-Dimension verwendet wird.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

Ähnlich wie bei der AppendURI-Transformation wirkt sich die PrependURI-Transformation auf das interne Feld aus, das vom Data Workbench-Server zum Erstellen der URI-Dimension verwendet wird.

Die [!DNL PrependURI]-Transformation funktioniert, indem der Wert im angegebenen Eingabefeld an der Vorderseite des Werts, der sich derzeit im URI befindet, hinzugefügt wird.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, dessen Wert dem URI vorangestellt wird. |  |

Im folgenden Beispiel wird dem URI einfach das Feld s-dns vorangestellt, wodurch die Darstellung der URI-Dimension auf die vom Client-Gerät angeforderte Domäne erweitert wird.

![](assets/cfg_TransformationType_PrependURI.png)

In diesem Beispiel wird dem URI das s-dns-Feld vorangestellt

* [!DNL /modelview.asp&id=login]

ergibt die folgende URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Jetzt wird der URI um die angeforderte Domäne erweitert.
