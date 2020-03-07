---
description: Syntaxregeln für Formeln.
solution: Analytics
title: Syntax für beliebige Ausdrücke
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax für beliebige Ausdrücke{#syntax-for-any-expression}

Syntaxregeln für Formeln.

* Bei Suchbegriffen wird die Groß-/Kleinschreibung beachtet und die Eingabe muss genau so erfolgen, wie sie angezeigt werden.
* Bei einer Formel müssen Metrik-, Dimensions- und Filternamen, die Leerzeichen enthalten, Unterstriche zwischen Wörtern verwenden. Beispiel: [!DNL Page_Views]
* Bei Zeichenfolgen innerhalb von Ausdrücken müssen Sie bestimmte einfache Anführungszeichen, doppelte Anführungszeichen und Backslashes entfernen. Beispiel:

   * [!DNL “can’t”] ist akzeptabel und muss nicht entgangen werden, aber [!DNL ‘can’t’] ist inakzeptabel und muss als entkommen [!DNL ‘can\’t’].

   * [!DNL c:\windows] muss mit einem Escapezeichen versehen werden [!DNL c:\\windows].

