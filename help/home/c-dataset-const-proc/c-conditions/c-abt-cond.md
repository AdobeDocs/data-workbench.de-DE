---
description: Bei Transformationen und Dimensionen wird anhand von Bedingungen bestimmt, wann bestimmte Anweisungen oder Aktionen auf Protokollfelder angewendet werden.
solution: Analytics
title: Info zu Bedingungen
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Info zu Bedingungen{#about-conditions}

Bei Transformationen und Dimensionen wird anhand von Bedingungen bestimmt, wann bestimmte Anweisungen oder Aktionen auf Protokollfelder angewendet werden.

Der Parameter &quot;Log Entry Condition&quot;verwendet Bedingungen, um zu bestimmen, welche Protokolleinträge in den Dataset-Aufbau einbezogen werden sollen. In diesem Anhang werden die verschiedenen Bedingungstypen beschrieben, die auf dem Data Workbench-Server verfügbar sind.

Eine Bedingung fällt in eine von zwei Kategorien:

* **[!DNL Test Operations]:**Die[!DNL Compare],[!DNL Not Empty],[!DNL Range],[!DNL Regular Expression]und[!DNL String Match]Bedingungen werden zum Testen auf verschiedene Status in den verfügbaren Protokollfeldern verwendet.

* **[!DNL Boolean Operations]:**Die[!DNL And],[!DNL Or]und[!DNL Neither]Bedingungen werden verwendet, um die oben beschriebenen Prüfverfahren zu kombinieren. Wenn Sie zum Beispiel eine[!DNL Range]Bedingung und eine Bedingung haben, die beide falsch sein müssen, um die entsprechende Aktion durchzuführen, würden Sie diese beiden Vorgänge zu untergeordneten Elementen der[!DNL String Match][!DNL Neither]Bedingung machen. Beachten Sie, dass die[!DNL And]Bedingung als Stamm aller Bedingungstests im System verwendet wird.

