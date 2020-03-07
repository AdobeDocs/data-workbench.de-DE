---
description: Die Bedingung "Neuer Besucher"ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher in den Datensatz aufgenommen werden sollen.
solution: Analytics
title: Neue Besucherbedingung
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Neue Besucherbedingung{#new-visitor-condition}

Die Bedingung &quot;Neuer Besucher&quot;ist ein Bedingungsvorgang, der mit Website-Daten verwendet wird, um zu bestimmen, welche Besucher in den Datensatz aufgenommen werden sollen.

Der Datensatz [!DNL New Visitor Condition] definiert den ersten (nach Zeit sortierten) Protokolleintrag für einen Besucher, der im Datensatz verwendet werden soll, und alle nachfolgenden Protokolleinträge für diesen Besucher werden in den Datensatz aufgenommen, unabhängig davon, ob diese Bedingung erfüllt ist. Da die Daten nach Besucher und Zeit geordnet werden [!DNL New Visitor Condition] müssen, werden sie nur während der Umwandlungsphase der Datensatzkonstruktion angewendet.

Mit dem in diesem Beispiel [!DNL New Visitor Condition] gezeigten Datensatz wird ein Datensatz erstellt, der nur die Protokolleinträge für Besucher enthält, die auf E-Mail-Kampagnen antworten. Dies wird erreicht, indem der [!DNL NotEmptyCondition] Test (siehe [Nicht leer](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) und das Feld als Eingabe für den regulären Ausdruck verwendet werden [!DNL x-campaign-email] . Nachdem die neuen Besucher, die die Bedingung erfüllen, identifiziert wurden, werden alle Protokolleinträge für diese Besucher erfasst.

![](assets/cfg_Transformation_NewVisitorCondition.png)

