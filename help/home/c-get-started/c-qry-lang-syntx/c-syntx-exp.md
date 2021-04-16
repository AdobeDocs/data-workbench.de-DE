---
description: Syntaxregeln für Formeln.
title: Grundsätzliche Syntax für Ausdrücke
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Grundsätzliche Syntax für Ausdrücke{#syntax-for-any-expression}

Syntaxregeln für Formeln.

* Bei Suchbegriffen wird die Groß-/Kleinschreibung beachtet und die Eingabe muss genau so erfolgen, wie sie angezeigt werden.
* Bei einer Formel müssen Metrik-, Dimensions- und Filternamen, die Leerzeichen enthalten, Unterstriche zwischen Wörtern verwenden. Beispiel: [!DNL Page_Views]
* Bei Zeichenfolgen innerhalb von Ausdrücken müssen Sie bestimmte einfache Anführungszeichen, Anführungszeichen für Dubletten und umgekehrte Schrägstriche entfernen. Beispiel:

   * [!DNL “can’t”] ist akzeptabel und muss nicht entgangen werden,  [!DNL ‘can’t’] ist aber inakzeptabel und muss als  [!DNL ‘can\’t’].

   * [!DNL c:\windows] muss mit einem Escapezeichen versehen werden  [!DNL c:\\windows].
