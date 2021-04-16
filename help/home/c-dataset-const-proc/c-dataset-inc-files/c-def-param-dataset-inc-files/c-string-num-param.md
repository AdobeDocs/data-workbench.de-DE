---
description: String- und numerische Parameter werden als ihre Werte Zeichenfolgen bzw. Zahlen verwendet.
title: Zeichenfolgen- und numerische Parameter
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Zeichenfolgen- und numerische Parameter{#string-and-numeric-parameters}

String- und numerische Parameter werden als ihre Werte Zeichenfolgen bzw. Zahlen verwendet.

Sie können sie austauschbar verwenden, aber numerische Parameter müssen definiert werden, um einen numerischen Wert zu haben. Sie können beim Definieren von Transformationen, Bedingungen und erweiterten Dimensionen auf Zeichenfolgen und numerische Parameter verweisen und mehrere Parameter in derselben Zeile referenzieren.

Sie können in den Feldern [!DNL Input] oder [!DNL Output] nicht auf Zeichenfolgen und numerische Parameter verweisen. Sie können jedoch einen Zeichenfolgenparameter verwenden, um ein konstantes Eingabefeld zu definieren. Darüber hinaus können Sie keine Zeichenfolgen und numerischen Parameter in Decoder- oder Decoder-Gruppen referenzieren.

Dieses Beispiel zeigt eine [!DNL Log Processing Dataset Include]-Datei, die einen Zeichenfolgenparameter und einen numerischen Parameter definiert. Beachten Sie, dass der Zeichenfolgenparameter &quot;Value Lookups&quot;einen Dateispeicherort (Suchen\Werte) relativ zum Installationsordner des Data Workbench-Servers definiert.

![](assets/cfg_Parameters_StringNumeric.png)
