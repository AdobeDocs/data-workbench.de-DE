---
description: Die Hash-Transformation erstellt eine fast eindeutige Zeichenfolge, die eine 64-Bit-Zahl aus den Eingabewerten darstellt.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 4%

---

# Hash{#hash}

Die Hash-Transformation erstellt eine fast eindeutige Zeichenfolge, die eine 64-Bit-Zahl aus den Eingabewerten darstellt.

Diese Umwandlung liefert denselben Hash-Wert, wenn dieselben Eingaben vorgenommen werden.

>[!NOTE]
>
>Der resultierende Wert ist fast eindeutig, da die Transformation eine 64-Bit-Zahl als Platz für mögliche Hash-Werte verwendet. Für eine Million einmaliger Eingaben zur [!DNL hash]-Umwandlung besteht eine Chance von 1:38.000.000, einen doppelten Hash-Wert zu erhalten.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn der Eingabewert nicht verfügbar ist. |  |
| Eingaben | Die Eingaben, die zum Erstellen des Hash-Werts verwendet werden sollen. |  |
| Ausgabe | Der Name des Felds für die Ausgabe. |  |

In diesem Beispiel werden die Werte der Felder c-ip und cs (user-agent) verwendet, um eine Tracking-ID zu erstellen, die im Feld x-trackingid gespeichert ist.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Dieses Beispiel stellt keine ideale Lösung zum Erstellen eindeutiger Tracking-IDs dar. In Situationen, in denen Archivierungsprotokollinformationen verwendet werden, kann dies jedoch die beste Methode sein.
