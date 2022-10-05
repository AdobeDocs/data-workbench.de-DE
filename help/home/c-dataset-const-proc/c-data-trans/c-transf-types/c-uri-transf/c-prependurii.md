---
description: Ähnlich wie bei der AppendURI-Transformation wirkt sich die PrependURI-Transformation auf das interne Feld aus, das vom Data Workbench-Server zum Erstellen der URI-Dimension verwendet wird.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

{{eol}}

Ähnlich wie bei der AppendURI-Transformation wirkt sich die PrependURI-Transformation auf das interne Feld aus, das vom Data Workbench-Server zum Erstellen der URI-Dimension verwendet wird.

Die [!DNL PrependURI] Die Umwandlung funktioniert, indem der Wert im Feld Identifizierte Eingabe an die Vorderseite des Werts eingefügt wird, der sich derzeit im URI befindet.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert nicht verfügbar ist. |  |
| Eingabe | Der Name des Felds, dessen Wert dem URI vorangestellt wird. |  |

Im folgenden Beispiel wird einfach das Feld s-dns auf den URI vorangestellt, wodurch die Darstellung der URI-Dimension um die vom Client-Gerät angeforderte Domäne erweitert wird.

![](assets/cfg_TransformationType_PrependURI.png)

In diesem Beispiel wird das s-dns-Feld dem URI vorangestellt

* [!DNL /modelview.asp&id=login]

führt zu der folgenden URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Jetzt wird der URI um die angeforderte Domäne erweitert.
