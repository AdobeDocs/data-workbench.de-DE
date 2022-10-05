---
description: Syntaxregeln für Formeln.
title: Grundsätzliche Syntax für Ausdrücke
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Grundsätzliche Syntax für Ausdrücke{#syntax-for-any-expression}

{{eol}}

Syntaxregeln für Formeln.

* Bei Suchbegriffen wird zwischen Groß- und Kleinschreibung unterschieden und die Eingabe muss genau so erfolgen, wie sie erscheinen.
* Bei einer Formel müssen Metrik-, Dimensions- und Filternamen, die Leerzeichen enthalten, Unterstriche zwischen Wörtern verwenden. Beispiel: [!DNL Page_Views]
* Bei Zeichenfolgen in Ausdrücken müssen Sie bestimmte einfache Anführungszeichen, doppelte Anführungszeichen und Backslashes als Escape-Zeichen verwenden. Beispiel:

   * [!DNL “can’t”] ist akzeptabel und muss nicht maskiert werden, aber [!DNL ‘can’t’] ist inakzeptabel und muss als [!DNL ‘can\’t’].

   * [!DNL c:\windows] muss als [!DNL c:\\windows].
