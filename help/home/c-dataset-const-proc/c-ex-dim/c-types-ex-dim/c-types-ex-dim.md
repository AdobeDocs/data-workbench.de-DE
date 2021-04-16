---
description: Mit dem Insight-Server können Sie zählbare, einfache, viele-zu-viele, numerische, denormale und Zeitdimensionen definieren, die in Ihren Datensatz aufgenommen werden sollen.
title: Typen von erweiterten Dimensionen
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# Typen von erweiterten Dimensionen{#types-of-extended-dimensions}

Mit dem Insight-Server können Sie zählbare, einfache, viele-zu-viele, numerische, denormale und Zeitdimensionen definieren, die in Ihren Datensatz aufgenommen werden sollen.

Jeder Dimensionstyp verfügt über einen Satz von Parametern, deren Werte Sie bearbeiten, um spezielle Anweisungen für den Insight-Server bereitzustellen, die Dimensionen während der Transformationsphase der Datensatzkonstruktion zu erstellen.

Während sich einige Parameter von Dimensionstyp zu Dimensionstyp unterscheiden, erfordern alle die Angabe einer übergeordneten Dimension (der übergeordnete Parameter). Die übergeordnete Dimension bestimmt, welche Protokolleinträge aus den Protokollquellen als Eingabe für die neue Dimension bereitgestellt werden. Mit anderen Worten, die mit den Elementen der übergeordneten Dimension verknüpften Protokolleinträge sind die Einträge, die mit der neuen Dimension verknüpft sind, bevor eine Filterung angewendet wird. Die übergeordnete Dimension bestimmt auch die Position der neuen Dimension in der Hierarchie des Datensatzes, das als Schema des Datensatzes bezeichnet wird. Weitere Informationen zur Oberfläche, auf der das Schema des Datensatzes angezeigt wird, finden Sie unter [Datenkonfigurationstools](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Nachdem der Insight-Server die übergeordnete Dimension verwendet hat, um zu bestimmen, welche Protokolleinträge bei der Erstellung der Dimension berücksichtigt werden sollen, wendet er die angegebene(n) Bedingung(en) (den Bedingungsparameter) an, um die Protokolleinträge zu leeren, die die Bedingung nicht erfüllen. Der Server identifiziert dann den Wert des angegebenen Eingabefelds (den Eingabeparameter) für jeden Protokolleintrag und wendet ggf. den angegebenen Vorgang (den Vorgangsparameter) an.

>[!NOTE]
>
>Wenn ein Protokolleintrag die Bedingung einer erweiterten Dimension nicht erfüllt, ersetzt der Insight-Server leere Werte für alle Felder im Protokolleintrag. Der tatsächliche Protokolleintrag ist noch vorhanden, und der angegebene Vorgang bestimmt, ob der leere Wert des Felds [!DNL Input] verwendet wird.
