---
description: String- und numerische Parameter werden als ihre Werte Zeichenfolgen bzw. Zahlen verwendet.
solution: Analytics
title: String und numerische Parameter
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# String und numerische Parameter{#string-and-numeric-parameters}

String- und numerische Parameter werden als ihre Werte Zeichenfolgen bzw. Zahlen verwendet.

Sie können sie austauschbar verwenden, aber numerische Parameter müssen definiert werden, um einen numerischen Wert zu haben. Sie können beim Definieren von Transformationen, Bedingungen und erweiterten Dimensionen auf Zeichenfolgen und numerische Parameter verweisen und mehrere Parameter in derselben Zeile referenzieren.

Sie können nicht auf Zeichenfolgen und numerische Parameter in [!DNL Input] oder [!DNL Output] Feldern verweisen, aber Sie können einen Zeichenfolgenparameter verwenden, um ein konstantes Eingabefeld zu definieren. Darüber hinaus können Sie keine Zeichenfolgen und numerischen Parameter in Decoder- oder Decoder-Gruppen referenzieren.

Dieses Beispiel zeigt eine [!DNL Log Processing Dataset Include] Datei, die einen Zeichenfolgenparameter und einen numerischen Parameter definiert. Beachten Sie, dass der Zeichenfolgenparameter &quot;Value Lookups&quot;einen Dateispeicherort (Suchen\Werte) relativ zum Installationsordner des Data Workbench-Servers definiert.

![](assets/cfg_Parameters_StringNumeric.png)

