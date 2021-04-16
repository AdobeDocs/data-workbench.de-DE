---
description: Die Hash-Transformation erstellt eine nahezu eindeutige Zeichenfolge, die eine 64-Bit-Zahl aus den Eingabewerten darstellt.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 4%

---

# Hash{#hash}

Die Hash-Transformation erstellt eine nahezu eindeutige Zeichenfolge, die eine 64-Bit-Zahl aus den Eingabewerten darstellt.

Diese Transformation liefert denselben Hashwert, wenn dieselben Eingaben vorgenommen werden.

>[!NOTE]
>
>Der resultierende Wert ist fast eindeutig, da die Transformation eine 64-Bit-Zahl als Platz für mögliche Hash-Werte verwendet. Bei einer Million einzigartiger Eingaben zur [!DNL hash]-Transformation besteht eine Chance von 1:38.000.000, einen Duplikat-Hash-Wert zu erhalten.

| Parameter | Beschreibung | Standard |
|---|---|---|
| Name | Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. |  |
| Kommentare | Optional. Anmerkungen zur Transformation. |  |
| Bedingung | Die Bedingungen, unter denen diese Umwandlung angewendet wird. |  |
| Standard | Der Standardwert, der verwendet wird, wenn der Eingabewert nicht verfügbar ist. |  |
| Eingänge | Der Satz der Eingaben, die zum Erstellen des Hashwerts verwendet werden sollen. |  |
| Ausgabe | Der Name des Felds für die Ausgabe. |  |

In diesem Beispiel werden die Werte der Felder c-ip und cs(user-agent) verwendet, um eine Verfolgungs-ID zu erstellen, die im Feld x-trackingid gespeichert wird.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Dieses Beispiel stellt keine ideale Lösung zum Erstellen eindeutiger Tracking-IDs dar. In Fällen, in denen Archivprotokollinformationen verwendet werden, ist dies möglicherweise die beste Methode.
