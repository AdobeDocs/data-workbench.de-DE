---
description: Umwandlungen und Dimensionen verwenden Bedingungen, um zu bestimmen, wann bestimmte Anweisungen oder Aktionen auf Protokollfelder angewendet werden.
title: Über Bedingungen
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Über Bedingungen{#about-conditions}

{{eol}}

Umwandlungen und Dimensionen verwenden Bedingungen, um zu bestimmen, wann bestimmte Anweisungen oder Aktionen auf Protokollfelder angewendet werden.

Der Parameter Log Entry Condition verwendet Bedingungen, um zu bestimmen, welche Protokolleinträge in den Prozess der Datensatzerstellung einbezogen werden sollen. In diesem Anhang werden die verschiedenen Typen von Bedingungen beschrieben, die auf dem Data Workbench-Server verfügbar sind.

Eine Bedingung fällt in eine von zwei Kategorien:

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]und [!DNL String Match] -Bedingungen werden verwendet, um in den verfügbaren Protokollfeldern auf unterschiedliche Status zu testen.

* **[!DNL Boolean Operations]:** Die [!DNL And], [!DNL Or]und [!DNL Neither] -Bedingungen verwendet werden, um die oben beschriebenen Testoperationen zu kombinieren. Wenn Sie beispielsweise eine [!DNL Range] und eine [!DNL String Match] -Bedingung, die beide falsch sein muss, um die entsprechende Aktion durchzuführen, würden Sie diese beiden Vorgänge untergeordnete Elemente der [!DNL Neither] Bedingung. Beachten Sie Folgendes: [!DNL And] -Bedingung wird als Stamm aller Bedingungstests im System verwendet.
