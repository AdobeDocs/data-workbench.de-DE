---
description: Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Operationen funktionieren.
title: Boolesche Operationen
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Boolesche Operationen{#boolean-operations}

Die booleschen Vorgänge kombinieren die Ergebnisse der Testoperationen, die als untergeordnete Elemente der booleschen Operationen funktionieren.

Weitere Informationen zu den Testvorgängen finden Sie unter [Testoperationen](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Wenn Sie einen [!DNL boolean]-Vorgang definieren, können Sie null oder mehr untergeordnete Elemente für den Vorgang definieren.

**Hinzufügen einer untergeordneten Bedingung zu einem booleschen Vorgang**

1. Klicken Sie mit der rechten Maustaste auf den Namen oder die Nummer, die dem Vorgang [!DNL Boolean] entspricht.
1. Klicken Sie auf **[!UICONTROL Add new child]** und wählen Sie einen der verfügbaren Bedingungstypen aus, die hinzugefügt werden sollen.
1. Wiederholen Sie die Schritte 1 und 2, bis Sie alle gewünschten untergeordneten Bedingungen für den Vorgang [!DNL Boolean] hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn Sie mit der rechten Maustaste auf den Namen oder die Zahl klicken, die einem [!DNL Boolean]-Vorgang entspricht, wird die Menüoption [!DNL Add new sibling] angezeigt. Ein Geschwister ist eine weitere Bedingung an derselben relativen Position in der Bedingungshierarchie wie der [!DNL Boolean]-Vorgang, auf den Sie mit der rechten Maustaste geklickt haben. Das Hinzufügen eines neuen gleichrangigen Elements für einen [!DNL Boolean]-Vorgang entspricht dem Hinzufügen einer neuen Bedingung durch Rechtsklick auf den Parameter [!DNL Condition] oder [!DNL Log Entry Condition] .

**So entfernen Sie eine untergeordnete Bedingung aus einem booleschen Vorgang:**

1. Klicken Sie mit der rechten Maustaste auf den Namen der untergeordneten Bedingung oder die Zahl, die der untergeordneten Bedingung entspricht, die Sie aus dem [!DNL Boolean]-Vorgang entfernen möchten.
1. Klicken Sie auf **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, wobei number die Zahl ist, die der zu entfernenden untergeordneten Bedingung entspricht.

In diesem Abschnitt werden die folgenden Bedingungen behandelt:

* [Und](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Keines](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Oder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Und {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Die Bedingung [!DNL And] kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn keiner der untergeordneten Knoten &quot;false&quot;zurückgibt.

Die Bedingung [!DNL And] bildet den Stammvorgang aller Bedingungstests innerhalb des Data Workbench-Servers. Wenn die Bedingung [!DNL And] keine untergeordneten Elemente enthält, wird die Bedingung als &quot;true&quot;ausgewertet und der zugehörige Vorgang wird fortgesetzt. Dies ist der Grund, warum Aktionen, die nur die Bedingung [!DNL And] aufweisen, da der Bedingungstest immer ausgeführt wird, und warum er als Stamm für alle Bedingungstests verwendet wird.

In diesem Beispiel wird gezeigt, wie eine [!DNL And]-Bedingung verwendet wird, um sicherzustellen, dass die [!DNL Copy]-Umwandlung erfolgt, wenn nur das Datum des Protokolleintrags im Jahr 2006 eintrat und die angeforderte Seite [!DNL /products/purchase.asp] war.

![](assets/cfg_Condition_AndCondition.png)

## Keine {#section-7e48b61266aa43ecbc48b979bf5e939b}

Die Bedingung [!DNL Neither] kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;false&quot;zurück, wenn eine ihrer untergeordneten Bedingungen &quot;true&quot;ergibt. Wenn die Bedingung [!DNL Neither] keine untergeordneten Elemente enthält, kann keines der untergeordneten Elemente &quot;true&quot;zurückgeben. Daher wird die Bedingung [!DNL Neither] als &quot;true&quot;ausgewertet.

Das folgende Beispiel zeigt eine [!DNL Neither] -Bedingung mit zwei [!DNL Range] -Bedingungen als untergeordneten Elementen. Wie definiert, schließt die Bedingung [!DNL Neither] Protokolleinträge aus, die zwischen dem 1. Januar 2007 und dem 10. Januar 2007 oder im Zeitraum vom 12. Januar 2007 bis zum 14. Januar 2007 stattgefunden haben. Eine solche Bedingung kann als [!DNL Log Entry Condition] verwendet werden, um Transaktionen aus einem Datensatz in Zeiträumen zu eliminieren, in denen ein bekanntes Problem mit den erfassten Daten aufgetreten ist.

![](assets/cfg_Condition_NeitherCondition.png)

## Oder {#section-a3aa0f56b6234f2680fa81939228326b}

Die Bedingung [!DNL Or] kann null oder mehr untergeordnete Bedingungen aufweisen und gibt &quot;true&quot;zurück, wenn mindestens eine ihrer untergeordneten Bedingungen als &quot;true&quot;ausgewertet wird. Wenn die Bedingung [!DNL Or] keine untergeordneten Elemente enthält, kann keines der untergeordneten Elemente &quot;true&quot;zurückgeben. Daher wird die Bedingung [!DNL Or] als &quot;false&quot;ausgewertet.

In diesem Beispiel wird die [!DNL Or] -Bedingung mit einer [!DNL String Match] -Bedingung und einer [!DNL Range] -Bedingung als untergeordnete Elemente dargestellt. Die Bedingung [!DNL Or] ist nur dann erfüllt, wenn für den Protokolleintrag der Wert [!DNL x-hasproblem] auf &quot;Ja&quot;gesetzt ist oder der Protokolleintrag im Zeitraum vom 1. Januar 2007 bis zum 10. Januar 2007 stattgefunden hat.

![](assets/cfg_Condition_OrCondition.png)
