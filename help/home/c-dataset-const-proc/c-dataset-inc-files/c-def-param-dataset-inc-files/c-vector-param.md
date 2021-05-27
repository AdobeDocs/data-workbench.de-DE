---
description: Vektorparameter enthalten mehrere Werte für eine einzelne Variable.
title: Vektorparameter
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
exl-id: c6140bdf-dcd9-4fa9-a6e0-34cbc45414d0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%

---

# Vektorparameter{#vector-parameters}

Vektorparameter enthalten mehrere Werte für eine einzelne Variable.

Sie können Vektorparameter nur als einziges Element eines Vektors referenzieren. Dieses Beispiel zeigt eine [!DNL Transformation Dataset Include]-Datei, die einen Vektorparameter definiert. Der Vektorparameter &quot;Interne Domänen&quot;besteht aus drei Werten.

![](assets/cfg_WebParameters_InternalDomains.png)

Beachten Sie, dass der Vektorparameter das einzige Element ist, das für den Vektor [!DNL Matches] in der Bedingung [!DNL String Match] aufgeführt ist.

![](assets/cfg_Parameters_InternalDomains_Ref.png)

Weitere Informationen zu internen Domänen finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519). Weitere Informationen zur Bedingung [!DNL String Match] finden Sie unter [Bedingungen](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
