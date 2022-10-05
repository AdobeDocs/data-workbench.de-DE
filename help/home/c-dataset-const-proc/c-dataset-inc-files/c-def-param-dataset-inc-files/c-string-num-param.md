---
description: Zeichenfolgen- und numerische Parameter nehmen als Wertzeichenfolgen bzw. Zahlen an.
title: Zeichenfolgen- und numerische Parameter
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Zeichenfolgen- und numerische Parameter{#string-and-numeric-parameters}

{{eol}}

Zeichenfolgen- und numerische Parameter nehmen als Wertzeichenfolgen bzw. Zahlen an.

Sie können sie austauschbar verwenden, numerische Parameter müssen jedoch so definiert sein, dass sie einen numerischen Wert aufweisen. Sie können beim Definieren von Umwandlungen, Bedingungen und erweiterten Dimensionen auf Zeichenfolgen und numerische Parameter verweisen und mehrere Parameter in derselben Zeile referenzieren.

Zeichenfolgen- und numerische Parameter können nicht referenziert werden in [!DNL Input] oder [!DNL Output] -Felder, Sie können jedoch einen Zeichenfolgenparameter verwenden, um ein konstantes Eingabefeld zu definieren. Darüber hinaus können Sie keine Zeichenfolgen- und numerischen Parameter in Decodern oder Decoder-Gruppen referenzieren.

Dieses Beispiel zeigt eine [!DNL Log Processing Dataset Include] -Datei, die einen Zeichenfolgenparameter und einen numerischen Parameter definiert. Beachten Sie, dass der Zeichenfolgenparameter mit dem Namen &quot;Value Lookups&quot;einen Dateispeicherort (Suchen\Werte) definiert, der relativ zum Installationsordner des Data Workbench-Servers ist.

![](assets/cfg_Parameters_StringNumeric.png)
