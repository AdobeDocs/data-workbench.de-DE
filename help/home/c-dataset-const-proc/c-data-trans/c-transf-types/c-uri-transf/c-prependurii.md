---
description: Ähnlich wie bei der AppendURI-Transformation wirkt sich die PrependURI-Transformation auf das interne Feld aus, das vom Data Workbench-Server zum Erstellen der URI-Dimension verwendet wird.
solution: Analytics
title: PrependURI
topic: Data workbench
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# PrependURI{#prependuri}

Ähnlich wie bei der AppendURI-Transformation wirkt sich die PrependURI-Transformation auf das interne Feld aus, das vom Data Workbench-Server zum Erstellen der URI-Dimension verwendet wird.

Die [!DNL PrependURI] Transformation funktioniert, indem der Wert im identifizierten Eingabefeld an der Vorderseite des Werts hinzugefügt wird, der sich derzeit im URI befindet.

| Parameter | Beschreibung | Standardeinstellung |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standardeinstellung | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, dessen Wert dem URI vorangestellt wird. |  |

Im folgenden Beispiel wird dem URI einfach das Feld s-dns vorangestellt, wodurch die Darstellung der URI-Dimension auf die vom Client-Gerät angeforderte Domäne erweitert wird.

![](assets/cfg_TransformationType_PrependURI.png)

In diesem Beispiel wird dem URI das s-dns-Feld vorangestellt

* [!DNL /modelview.asp&id=login]

ergibt die folgende URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Jetzt wird der URI um die angeforderte Domäne erweitert.
