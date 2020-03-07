---
description: Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Vorgänge fungieren.
solution: Analytics
title: Boolesche Vorgänge
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Boolesche Vorgänge{#boolean-operations}

Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Vorgänge fungieren.

Informationen zu den Testvorgängen finden Sie unter [Testvorgänge](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Wenn Sie einen [!DNL boolean] Vorgang definieren, können Sie null oder mehr untergeordnete Elemente für den Vorgang definieren.

**So fügen Sie einer booleschen Operation eine untergeordnete Bedingung hinzu**

1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Nummer, die dem [!DNL Boolean] Vorgang entspricht.
1. Klicken Sie auf **[!UICONTROL Add new child]** und wählen Sie einen der verfügbaren Bedingungstypen, die hinzugefügt werden sollen.
1. Wiederholen Sie die Schritte 1 und 2, bis Sie alle gewünschten untergeordneten Bedingungen für den [!DNL Boolean] Vorgang hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn Sie mit der rechten Maustaste auf den Namen oder die Zahl klicken, die einem [!DNL Boolean] Vorgang entspricht, wird die [!DNL Add new sibling] Menüoption angezeigt. Ein Geschwisterelement ist eine weitere Bedingung, die sich an derselben relativen Position in der Bedingungshierarchie befindet wie der [!DNL Boolean] Vorgang, auf den Sie mit der rechten Maustaste geklickt haben. Das Hinzufügen eines neuen Geschwisters für einen [!DNL Boolean] Vorgang ist dasselbe wie das Hinzufügen einer neuen Bedingung durch Rechtsklicken auf den [!DNL Condition] oder [!DNL Log Entry Condition] -Parameter.

**So entfernen Sie eine untergeordnete Bedingung aus einer booleschen Operation:**

1. Klicken Sie mit der rechten Maustaste auf den Namen der untergeordneten Bedingung oder die Zahl, die der untergeordneten Bedingung entspricht, die Sie aus der [!DNL Boolean] Operation entfernen möchten.
1. Klicken Sie auf **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei number die Zahl ist, die der zu entfernenden untergeordneten Bedingung entspricht.

In diesem Abschnitt werden die folgenden Bedingungen behandelt:

* [Und](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Keiner](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Oder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Und {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Die [!DNL And] Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn keiner ihrer untergeordneten Knoten &quot;false&quot;zurückgibt.

Die [!DNL And] Bedingung bildet den Stammvorgang aller Bedingungstests innerhalb des Data Workbench-Servers. Wenn die [!DNL And] Bedingung keine untergeordneten Elemente enthält, wird die Bedingung als &quot;true&quot;ausgewertet und der zugehörige Vorgang wird fortgesetzt. Dies ist der Grund, warum Aktionen, die nur die [!DNL And] Bedingung haben, da der Bedingungstest immer ausgeführt wird, und warum sie als Stamm für alle Bedingungstests verwendet werden.

Dieses Beispiel zeigt, wie eine [!DNL And] Bedingung verwendet wird, um sicherzustellen, dass die [!DNL Copy] Transformation erfolgt, wenn sowohl das Datum des Protokolleintrags im Jahr 2006 als auch die angeforderte Seite [!DNL /products/purchase.asp]auftrat.

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

Die [!DNL Neither] Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;false&quot;zurück, wenn eine ihrer untergeordneten Bedingungen &quot;true&quot;ergibt. Wenn die [!DNL Neither] Bedingung keine untergeordneten Elemente enthält, kann keiner der untergeordneten Elemente &quot;true&quot;zurückgeben. Daher wird die [!DNL Neither] Bedingung als &quot;true&quot;ausgewertet.

Das folgende Beispiel zeigt eine [!DNL Neither] Bedingung mit zwei [!DNL Range] Bedingungen als untergeordnete Elemente. Wie definiert schließt die [!DNL Neither] Bedingung Protokolleinträge aus, die zwischen dem 1. Januar 2007 und dem 10. Januar 2007 oder dem 12. Januar 2007 bis zum 14. Januar 2007 stattgefunden haben. Eine solche Bedingung kann als Grundlage für die Beseitigung von Transaktionen aus einem Datensatz in Zeiträumen verwendet werden, in denen ein bekanntes Problem mit den erfassten Daten aufgetreten ist. [!DNL Log Entry Condition]

![](assets/cfg_Condition_NeitherCondition.png)

## Oder {#section-a3aa0f56b6234f2680fa81939228326b}

Die [!DNL Or] Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn mindestens eine ihrer untergeordneten Bedingungen &quot;true&quot;ergibt. Wenn die [!DNL Or] Bedingung keine untergeordneten Elemente enthält, kann keiner der untergeordneten Elemente &quot;true&quot;zurückgeben. Daher wird die [!DNL Or] Bedingung als &quot;false&quot;ausgewertet.

Dieses Beispiel zeigt die [!DNL Or] Bedingung mit einer [!DNL String Match] Bedingung und einer [!DNL Range] Bedingung als untergeordnete Elemente. Die [!DNL Or] Bedingung ist nur erfüllt, wenn der Protokolleintrag den [!DNL x-hasproblem] Wert yes hat oder der Protokolleintrag im Zeitraum vom 1. Januar 2007 bis zum 10. Januar 2007 stattgefunden hat.

![](assets/cfg_Condition_OrCondition.png)

