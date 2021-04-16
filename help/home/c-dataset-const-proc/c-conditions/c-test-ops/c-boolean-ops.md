---
description: Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Vorgänge fungieren.
title: Boolesche Operationen
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Boolesche Operationen{#boolean-operations}

Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Vorgänge fungieren.

Weitere Informationen zu den Testvorgängen finden Sie unter [Testvorgänge](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Wenn Sie einen [!DNL boolean]-Vorgang definieren, können Sie null oder mehr untergeordnete Elemente für den Vorgang definieren.

**So fügen Sie einer booleschen Operation eine untergeordnete Bedingung hinzu**

1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Zahl, die dem Vorgang [!DNL Boolean] entspricht.
1. Klicken Sie auf **[!UICONTROL Add new child]** und wählen Sie einen der verfügbaren Bedingungstypen, die hinzugefügt werden sollen.
1. Wiederholen Sie die Schritte 1 und 2, bis Sie alle gewünschten untergeordneten Bedingungen für den Vorgang [!DNL Boolean] hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn Sie mit der rechten Maustaste auf den Namen oder die Zahl klicken, die einem [!DNL Boolean]-Vorgang entspricht, sehen Sie die Menüoption [!DNL Add new sibling]. Ein Geschwisterelement ist eine weitere Bedingung, die sich an derselben relativen Position in der Bedingungshierarchie befindet wie der Vorgang [!DNL Boolean], auf den Sie mit der rechten Maustaste geklickt haben. Das Hinzufügen eines neuen Geschwisters für einen [!DNL Boolean]-Vorgang ist dasselbe wie das Hinzufügen einer neuen Bedingung durch Rechtsklicken auf den Parameter [!DNL Condition] oder [!DNL Log Entry Condition].

**So entfernen Sie eine untergeordnete Bedingung aus einer booleschen Operation:**

1. Klicken Sie mit der rechten Maustaste auf den Namen der untergeordneten Bedingung oder die Zahl, die der untergeordneten Bedingung entspricht, die Sie aus dem [!DNL Boolean]-Vorgang entfernen möchten.
1. Klicken Sie auf **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei Zahl die Zahl ist, die der zu entfernenden untergeordneten Bedingung entspricht.

In diesem Abschnitt werden die folgenden Bedingungen behandelt:

* [Und](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Keiner](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Oder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Und {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Die [!DNL And]-Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn keiner ihrer untergeordneten Knoten &quot;false&quot;zurückgibt.

Die Bedingung [!DNL And] bildet den Stammvorgang aller Bedingungstests innerhalb des Data Workbench-Servers. Wenn die Bedingung [!DNL And] keine untergeordneten Elemente enthält, wird die Bedingung als &quot;true&quot;ausgewertet und der zugehörige Vorgang wird fortgesetzt. Dies ist der Grund, warum Aktionen, die nur die Bedingung [!DNL And] haben, da der Bedingungstest immer ausgeführt wird, und warum sie als Stamm für alle Bedingungstests verwendet werden.

Dieses Beispiel zeigt, wie eine [!DNL And]-Bedingung verwendet wird, um sicherzustellen, dass die [!DNL Copy]-Transformation erfolgt, wenn nur das Datum des Protokolleintrags im Jahr 2006 und die angeforderte Seite [!DNL /products/purchase.asp] auftrat.

![](assets/cfg_Condition_AndCondition.png)

## Weder {#section-7e48b61266aa43ecbc48b979bf5e939b}

Die [!DNL Neither]-Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;false&quot;zurück, wenn eine ihrer untergeordneten Bedingungen &quot;true&quot;ergibt. Wenn die [!DNL Neither]-Bedingung keine untergeordneten Elemente enthält, kann keiner der untergeordneten Elemente &quot;true&quot;zurückgeben. Die Bedingung [!DNL Neither] wird daher als &quot;true&quot;ausgewertet.

Das folgende Beispiel zeigt eine [!DNL Neither]-Bedingung mit zwei [!DNL Range]-Bedingungen als untergeordnete Elemente. Wie definiert schließt die Bedingung [!DNL Neither] Protokolleinträge aus, die zwischen dem 1. Januar 2007 und dem 10. Januar 2007 oder dem 12. Januar 2007 bis zum 14. Januar 2007 stattgefunden haben. Eine solche Bedingung kann als [!DNL Log Entry Condition] verwendet werden, um Transaktionen aus einem Datensatz in Zeiträumen zu entfernen, in denen ein bekanntes Problem mit den erfassten Daten aufgetreten ist.

![](assets/cfg_Condition_NeitherCondition.png)

## Oder {#section-a3aa0f56b6234f2680fa81939228326b}

Die Bedingung [!DNL Or] kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn mindestens eine ihrer untergeordneten Bedingungen &quot;true&quot;ergibt. Wenn die [!DNL Or]-Bedingung keine untergeordneten Elemente enthält, kann keiner der untergeordneten Elemente &quot;true&quot;zurückgeben. Die Bedingung [!DNL Or] wird daher als &quot;false&quot;ausgewertet.

Dieses Beispiel zeigt die Bedingung [!DNL Or] mit einer Bedingung [!DNL String Match] und einer Bedingung [!DNL Range] als untergeordnete Bedingung. Die Bedingung [!DNL Or] ist nur dann erfüllt, wenn der Protokolleintrag den Wert [!DNL x-hasproblem] auf yes gesetzt hat oder der Protokolleintrag im Zeitraum vom 1. Januar 2007 bis zum 10. Januar 2007 stattgefunden hat.

![](assets/cfg_Condition_OrCondition.png)
