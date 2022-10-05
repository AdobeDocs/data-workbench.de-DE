---
description: Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Operationen funktionieren.
title: Boolesche Operationen
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Boolesche Operationen{#boolean-operations}

{{eol}}

Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Operationen funktionieren.

Informationen zu den Testvorgängen finden Sie unter [Testoperationen](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Wenn Sie eine [!DNL boolean] -Vorgang können Sie null oder mehr untergeordnete Elemente für den Vorgang definieren.

**Hinzufügen einer untergeordneten Bedingung zu einem booleschen Vorgang**

1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Nummer, die dem [!DNL Boolean] Vorgang.
1. Klicken **[!UICONTROL Add new child]** und wählen Sie einen der verfügbaren Bedingungstypen aus, die hinzugefügt werden sollen.
1. Wiederholen Sie die Schritte 1 und 2, bis Sie alle gewünschten untergeordneten Bedingungen für die [!DNL Boolean] Vorgang.

   >[!NOTE]
   >
   >Wenn Sie mit der rechten Maustaste auf den Namen oder die Nummer klicken, die einem [!DNL Boolean] -Vorgang, sehen Sie die [!DNL Add new sibling] Menüoption. Ein Geschwister ist eine weitere Bedingung, die sich an derselben relativen Position in der Bedingungshierarchie befindet wie die [!DNL Boolean] -Vorgang, auf den Sie mit der rechten Maustaste geklickt haben. Hinzufügen eines neuen gleichrangigen Links für eine [!DNL Boolean] entspricht dem Hinzufügen einer neuen Bedingung durch Rechtsklick auf die [!DNL Condition] oder [!DNL Log Entry Condition] Parameter.

**So entfernen Sie eine untergeordnete Bedingung aus einem booleschen Vorgang:**

1. Klicken Sie mit der rechten Maustaste auf den Namen der untergeordneten Bedingung oder die Zahl, die der untergeordneten Bedingung entspricht, die Sie aus der [!DNL Boolean] Vorgang.
1. Klicken **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei number die Zahl ist, die der zu entfernenden untergeordneten Bedingung entspricht.

In diesem Abschnitt werden die folgenden Bedingungen behandelt:

* [Und](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Keines](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Oder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Und {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Die [!DNL And] -Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn keiner der untergeordneten Knoten &quot;false&quot;zurückgibt.

Die [!DNL And] -Bedingung bildet den Stammvorgang aller Bedingungstests auf dem Data Workbench-Server. Wenn die Variable [!DNL And] -Bedingung keine untergeordneten Elemente enthält, wird die Bedingung als &quot;true&quot;ausgewertet und der zugehörige Vorgang wird fortgesetzt. Dies ist der Grund, warum Aktionen, die nur die [!DNL And] -Bedingung, da der Bedingungstest immer ausgeführt wird und warum er als Stamm für alle Bedingungstests verwendet wird.

In diesem Beispiel wird gezeigt, wie [!DNL And] -Bedingung verwendet wird, um sicherzustellen, dass die [!DNL Copy] eine Umwandlung eintritt, wenn nur das Datum des Protokolleintrags im Jahr 2006 eintrat und die angeforderte Seite [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Keines {#section-7e48b61266aa43ecbc48b979bf5e939b}

Die [!DNL Neither] -Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und &quot;false&quot;zurückgeben, wenn eine ihrer untergeordneten Bedingungen als &quot;true&quot;ausgewertet wird. Wenn die Variable [!DNL Neither] -Bedingung enthält keine untergeordneten Elemente, keines ihrer untergeordneten Elemente kann &quot;true&quot;zurückgeben. Daher wird die [!DNL Neither] wird als &quot;true&quot;ausgewertet.

Das folgende Beispiel zeigt eine [!DNL Neither] Bedingung mit zwei [!DNL Range] Bedingungen als untergeordnete Elemente. Die Variable [!DNL Neither] Die Bedingung schließt Protokolleinträge aus, die zwischen dem 1. Januar 2007 und dem 10. Januar 2007 oder dem 12. Januar 2007 bis zum 14. Januar 2007 stattgefunden haben. Eine solche Bedingung kann als [!DNL Log Entry Condition] zur Beseitigung von Transaktionen aus einem Datensatz in Zeiträumen, in denen ein bekanntes Problem mit den erfassten Daten aufgetreten ist.

![](assets/cfg_Condition_NeitherCondition.png)

## Oder {#section-a3aa0f56b6234f2680fa81939228326b}

Die [!DNL Or] -Bedingung kann null oder mehr untergeordnete Bedingungen aufweisen und &quot;true&quot;zurückgeben, wenn mindestens eine ihrer untergeordneten Bedingungen als &quot;true&quot;ausgewertet wird. Wenn die Variable [!DNL Or] -Bedingung enthält keine untergeordneten Elemente, keines ihrer untergeordneten Elemente kann &quot;true&quot;zurückgeben. Daher wird die [!DNL Or] wird als false ausgewertet.

Dieses Beispiel zeigt die [!DNL Or] -Bedingung mit einer [!DNL String Match] und eine [!DNL Range] als untergeordnete Elemente. Die [!DNL Or] -Bedingung ist nur erfüllt, wenn der Protokolleintrag die [!DNL x-hasproblem] auf &quot;Ja&quot;gesetzt oder der Protokolleintrag trat im Zeitraum vom 1. Januar 2007 bis zum 10. Januar 2007 auf.

![](assets/cfg_Condition_OrCondition.png)
