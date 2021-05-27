---
description: Syntaxregeln für Formeln.
title: Grundsätzliche Syntax für Ausdrücke
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Grundsätzliche Syntax für Ausdrücke{#syntax-for-any-expression}

Syntaxregeln für Formeln.

* Bei Suchbegriffen wird zwischen Groß- und Kleinschreibung unterschieden und die Eingabe muss genau so erfolgen, wie sie erscheinen.
* Bei einer Formel müssen Metrik-, Dimensions- und Filternamen, die Leerzeichen enthalten, Unterstriche zwischen Wörtern verwenden. Beispiel: [!DNL Page_Views]
* Bei Zeichenfolgen in Ausdrücken müssen Sie bestimmte einfache Anführungszeichen, doppelte Anführungszeichen und Backslashes als Escape-Zeichen verwenden. Beispiel:

   * [!DNL “can’t”] ist akzeptabel und muss nicht entkommen,  [!DNL ‘can’t’] ist jedoch inakzeptabel und muss als  [!DNL ‘can\’t’]entkommen.

   * [!DNL c:\windows] muss als  [!DNL c:\\windows] maskiert werden.
