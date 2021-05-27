---
description: Mit Insight Server können Sie zählbare, einfache, viele-zu-viele, numerische, denormale und Zeitdimensionen definieren, die in Ihren Datensatz aufgenommen werden können.
title: Typen von erweiterten Dimensionen
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# Typen von erweiterten Dimensionen{#types-of-extended-dimensions}

Mit Insight Server können Sie zählbare, einfache, viele-zu-viele, numerische, denormale und Zeitdimensionen definieren, die in Ihren Datensatz aufgenommen werden können.

Jeder Dimensionstyp verfügt über einen Satz von Parametern, deren Werte Sie bearbeiten, um spezielle Anweisungen für den Insight Server bereitzustellen, um die Dimensionen während der Transformationsphase der Datensatzerstellung zu erstellen.

Zwar unterscheiden sich einige Parameter zwischen den Dimensionstypen, doch erfordern alle Parameter die Spezifikation einer übergeordneten Dimension (den übergeordneten Parameter). Die übergeordnete Dimension bestimmt, welche Protokolleinträge aus den Protokollquellen als Eingabe für die neue Dimension bereitgestellt werden. Mit anderen Worten: Die mit den Elementen der übergeordneten Dimension verknüpften Protokolleinträge sind diejenigen, die mit der neuen Dimension verknüpft sind, bevor eine Filterung angewendet wird. Die übergeordnete Dimension bestimmt auch die Position der neuen Dimension in der Hierarchie des Datensatzes, das so genannte Datensatzschema. Informationen zur Schnittstelle, die das Datensatzschema anzeigt, finden Sie unter [Tools für die Datensatzkonfiguration](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Nachdem der Insight Server die übergeordnete Dimension verwendet hat, um zu bestimmen, welche Protokolleinträge bei der Erstellung der Dimension berücksichtigt werden sollen, wendet er die angegebenen Bedingungen (den Bedingungsparameter) an, um die Protokolleinträge zu leeren, die die Bedingung nicht erfüllen. Der Server identifiziert dann den Wert des angegebenen Eingabefelds (den Eingabeparameter) für jeden Protokolleintrag und wendet ggf. den angegebenen Vorgang (den Aktionsparameter) an.

>[!NOTE]
>
>Wenn ein Protokolleintrag die Bedingung einer erweiterten Dimension nicht erfüllt, ersetzt der Insight Server leere Werte für alle Felder im Protokolleintrag. Der tatsächliche Protokolleintrag ist weiterhin vorhanden und der angegebene Vorgang bestimmt, ob der leere Wert des Felds [!DNL Input] verwendet wird.
