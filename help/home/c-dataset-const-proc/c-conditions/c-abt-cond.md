---
description: Bei Transformationen und Dimensionen wird anhand von Bedingungen bestimmt, wann bestimmte Anweisungen oder Aktionen auf Protokollfelder angewendet werden.
title: Über Bedingungen
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Über Bedingungen{#about-conditions}

Bei Transformationen und Dimensionen wird anhand von Bedingungen bestimmt, wann bestimmte Anweisungen oder Aktionen auf Protokollfelder angewendet werden.

Der Parameter &quot;Log Entry Condition&quot;verwendet Bedingungen, um zu bestimmen, welche Protokolleinträge in den Dataset-Aufbau einbezogen werden sollen. In diesem Anhang werden die verschiedenen Bedingungstypen beschrieben, die auf dem Data Workbench-Server verfügbar sind.

Eine Bedingung fällt in eine von zwei Kategorien:

* **[!DNL Test Operations]:** [!DNL Compare],  [!DNL Not Empty],  [!DNL Range],  [!DNL Regular Expression]und  [!DNL String Match] Bedingungen werden zum Testen auf verschiedene Status in den verfügbaren Protokollfeldern verwendet.

* **[!DNL Boolean Operations]:** Die oben beschriebenen Prüfvorgänge werden mit  [!DNL And],  [!DNL Or]und  [!DNL Neither] Bedingungen kombiniert. Wenn Sie beispielsweise eine Bedingung von [!DNL Range] und eine Bedingung von [!DNL String Match] haben, die beide &quot;false&quot;sein müssen, um die entsprechende Aktion durchzuführen, würden Sie diese beiden Vorgänge zu untergeordneten Elementen der Bedingung [!DNL Neither] machen. Beachten Sie, dass die Bedingung [!DNL And] als Stamm aller Bedingungstests im System verwendet wird.
