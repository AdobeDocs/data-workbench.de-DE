---
description: Reguläre Ausdrücke werden in allen Data Workbench-Suchfeldern verwendet, einschließlich der Bedienfelder für die Abfrageentität.
title: Reguläre Ausdrücke
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---

# Reguläre Ausdrücke{#regular-expressions}

Reguläre Ausdrücke werden in allen Data Workbench-Suchfeldern verwendet, einschließlich der Bedienfelder für die Abfrageentität.

* [Über reguläre Ausdrücke](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologie für reguläre Ausdrücke](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Über die Literalübereinstimmung](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Verwenden von Metazeichen](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Musterextraktion](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Über reguläre Ausdrücke {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Ein regulärer Ausdruck ist ein Textmuster, das aus einer Kombination aus alphanumerischen Zeichen und Sonderzeichen, die als Metazeichen bezeichnet werden, besteht und Muster lokalisiert und Teilzeichenfolgen aus Text extrahiert. Reguläre Ausdrücke werden häufig in der Computerprogrammierung verwendet und sind integraler Bestandteil von Sprachen wie Perl.

Um komplexe Zeichenfolgenmuster zu identifizieren und zu extrahieren, verwendet der Data Workbench-Server in einigen der Umwandlungen und Bedingungen reguläre Ausdrücke. Im Folgenden finden Sie eine kurze Anleitung zu regulären Ausdrücken.

Dieser Anhang ist keine umfassende Einführung in reguläre Ausdrücke. Ein besonders guter Hinweis ist die O&#39;Reilly-Veröffentlichung *Mastering Regular Expressions, 2nd Edition* von Jeffrey E. F. Friedl.

## Terminologie für reguläre Ausdrücke {#section-80b0d54f731e448391532ab3eb3c525c}

| Begriff | Definition |
|---|---|
| Literal | Ein Literal ist ein Zeichen, das wir in einem regulären Ausdruck verwenden, um eine bestimmte Folge von Zeichen zu finden. Um beispielsweise ein Produkt in [!DNL shop/products.html] zu finden, ist das String-Produkt ein Literal oder das, wonach wir buchstäblich in der Zeichenfolge suchen. |
| Metazeichen | Ein Metazeichen ist ein Sonderzeichen, das eine eindeutige Interpretation im Kontext regulärer Ausdrücke hat. Beispielsweise der Punkt (.) ist ein Metazeichen, mit dem ein beliebiges Zeichen abgeglichen wird. |
| Escape-Sequenz | Eine Escape-Sequenz ist einfach eine Möglichkeit, der Engine für reguläre Ausdrücke mitzuteilen, dass wir eines der Metazeichen als Literal verwenden möchten. Escape-Sequenzen beginnen immer mit dem umgekehrten Schrägstrich (`\`). Durch Platzierung des umgekehrten Schrägstrichs (bei dem es sich auch um ein Metazeichen handelt) vor einem Metazeichen interpretiert die Engine für reguläre Ausdrücke das maskierte Metazeichen als Literal. Wenn Sie beispielsweise den Metazeichenzeitraum (`.`) abgleichen möchten, müssen Sie eine Escape-Sequenz verwenden. Um jedoch einem der Punkte in der Zeichenfolge 168.196.0.11 zu entsprechen, können Sie den regulären Ausdruck verwenden, der aus einem umgekehrten Schrägstrich und einem Punkt (`\.`) besteht. |
| Muster | Dies ist eine kurze Terminologie für den regulären Ausdruck. Ein regulärer Ausdruck ist im Wesentlichen ein Muster, das Sie mit der Zielzeichenfolge abgleichen möchten. |
| Zielzeichenfolge | Dieser Begriff bezieht sich auf die Zeichenfolge, in der wir suchen, um das gewünschte Muster zu finden. |

## Über wörtliche Übereinstimmung {#section-ec4497e3160c47ba9b828d939761b3e0}

Die literale Übereinstimmung nimmt eine literale Zeichenfolge ohne Escape-Zeichen und sucht in der Zielzeichenfolge, um zu sehen, ob es sich um eine Teilzeichenfolge der Zielzeichenfolge handelt.

In diesem Beispiel sehen Sie, wie literale Übereinstimmung funktioniert. Stellen Sie sich eine Situation vor, in der Daten aus dem Website-Traffic erfasst werden und das Feld cs(referrer) den folgenden Wert enthält:

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Um festzustellen, ob der Referrer eine Person darstellt, die auf eine der Anzeigen geklickt hat, müssen Sie sehen, ob der Referrer die Zeichenfolgenanzeige enthält. Sie können einfach die Zeichenfolgenanzeige in Textform verwenden, um die Zielzeichenfolge zu durchsuchen und zu ermitteln, ob eine Anzeige verwendet wurde, um den Traffic zur Site zu leiten. Dies würde zwar mit der Zielzeichenfolge übereinstimmen, würde jedoch an zwei Stellen übereinstimmen und ist daher mehrdeutig und kann zu falsch-positiven Ergebnissen führen.

Die folgende URL enthält die Zeichenfolgenanzeige an zwei verschiedenen Stellen:

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Wenn Sie also herausfinden möchten, welche Sitzungen als Ergebnis einer bestimmten Werbekampagne gestartet wurden, reicht die einfache Verwendung der Literalanzeige als regulärer Ausdruck eindeutig nicht aus. Wenn Sie das Literal in &quot;ad=&quot;ändern, wird diese Uneindeutigkeit beseitigt und der Ausdruck führt dazu, dass nur eine Übereinstimmung erstellt wird. Selbst dies kann jedoch nicht ausreichen, um sicherzustellen, dass der Referrer Teil der Werbekampagne war. Betrachten Sie die folgende verweisende Stelle:

`http://www.xyz.com/hello.html?pad=something`

Sie haben keine Kontrolle über die URLs, die andere zum Erstellen von Links zur Site verwenden können. Die wörtliche Zuordnung ist zu einfach, um Sitzungen zu finden, die als Ergebnis der Werbekampagne gestartet wurden. Im folgenden Abschnitt wird erläutert, wie Sie Metazeichen für flexiblere und leistungsfähigere Abgleiche verwenden können.

## Verwenden von Metazeichen {#section-e29a804336304ea1ba33d40d60139aa2}

Ein Metazeichen ist ein Sonderzeichen in einem Programm- oder Datenfeld, das Informationen zu anderen Zeichen bereitstellt.

| metacharacter | Beschreibung |
|---|---|
|   (Punkt) | Entspricht einem einzelnen Zeichen, z. B.: `re:x.z` entspricht &quot;xyz&quot; oder &quot;xxz&quot;. |
| * (Stern) | Entspricht einem oder mehreren Zeichen, z. B.: `re:Z*` entspricht &quot;ZZZ&quot;. |
| ? (Platzhalter) | Stimmt mit 0 oder 1 des vorherigen Ausdrucks überein, um eine minimale Übereinstimmung zu erzwingen, z. B.: `xy?z` entspricht &quot;xy&quot;und &quot;xyz&quot;. |

Zusätzliche häufige reguläre Ausdrücke können auch verwendet werden, um komplexere Suchzeichenfolgen zu erstellen.

**Listen, Bereiche und ODER**

Bei der Literalzuordnung können Sie nach einer einzelnen Zeichenfolge suchen. Mit Klammern, Gedankenstrichen und senkrechten Strichen können Sie jedoch eine Liste der Elemente definieren, nach denen in der Zielzeichenfolge gesucht werden soll.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für dieses Metazeichen ... </th> 
   <th colname="col2" class="entry"> Der Prozessor für reguläre Ausdrücke ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Eckige Klammern ([ ]) </td> 
   <td colname="col2"> Ordnen Sie beliebige Zeichen innerhalb der Klammer mit einer einzelnen Zeichenposition zu. [AB] ist beispielsweise eine Anweisung, entweder den Buchstaben A oder B zuzuordnen, und [0123456789] sagt, dass er mit einem beliebigen Zeichen im Bereich von 0 bis 9 übereinstimmt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bindestrich (-) </td> 
   <td colname="col2"> <p>Übereinstimmung mit einem Zeichenbereich. Anstatt also [0123456789] zu schreiben, konnten wir einfach [0-9] schreiben. </p> <p> Dies kann auf Zeichenbereiche und mehrere Bereiche innerhalb eines Satzes von Klammern erweitert werden. Beispielsweise entspricht [0-9A-C] den Zeichen 0 bis 9 und A bis C. </p> <p> <p>Hinweis:  Um auf einen Bindestrich (-) als Literal innerhalb der Klammern zu testen, muss er zuerst oder zuletzt kommen. Beispielsweise [-0-9] Tests für - und 0 bis 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verkettungszeichen (|) </td> 
   <td colname="col2"> Ordnen Sie eine von zwei Optionen einer angegebenen Zielzeichenfolge zu. Beispielsweise entspricht "b|nat"entweder "bat"oder "nat". </td> 
  </tr> 
 </tbody> 
</table>

Sehen Sie sich folgende Beispiele an:

| Muster | Zeichenfolge | Übereinstimmung |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lesson`[A-Z]` | Lektion a | Keine Übereinstimmung, da der niedrigere a-Wert nicht im Bereich der oberen A bis Z liegt. |

**Negation**

Negation ist eine Möglichkeit zu sagen, dass Sie alles mit Ausnahme der angegebenen Zeichen vergleichen möchten. Das Negations-Metazeichen Zirkumflex oder Caret (`^`) wird als erstes Zeichen in Klammern verwendet, um zu sagen, dass die Übereinstimmung alles andere als die restlichen Zeichen in den Klammern sein soll. Um beispielsweise ein beliebiges Zeichen außer einem Semikolon (`;`) abzugleichen, würden Sie

[`^;`]

Dies würde mit allen Zeichen außer dem Semikolon übereinstimmen.

**Positionierung**

Um eine Übereinstimmung am Anfang oder Ende einer Zielzeichenfolge zu erzwingen, wird eines von zwei Metazeichen verwendet.

| Für dieses Metazeichen ... | Der Prozessor für reguläre Ausdrücke ... |
|---|---|
| Circumflex oder Caret (`^`) | Übereinstimmung mit dem Anfang der Zeichenfolge. Beispiel: ^`[Tt]`er würde mit der Zielzeichenfolge &quot;The Beginning&quot; übereinstimmen, aber nicht mit &quot;This is the Anfang&quot;. |
| Dollarzeichen (`$`) | Übereinstimmung mit dem Ende der Zeichenfolge Beispielsweise würde `[Ee]`nd$ mit &quot;This is the end&quot;übereinstimmen, jedoch nicht mit &quot;The end is a special time&quot;. |

>[!NOTE]
>
>Wenn der reguläre Ausdruck ^ am Anfang und $ am Ende enthält, muss die gesamte Zielzeichenfolge mit dem regulären Ausdruck übereinstimmen.

**Übereinstimmung**

Der Zeitraum (.) ist ein spezielles Metazeichen, das mit einem beliebigen Zeichen in der Zielzeichenfolge übereinstimmt. Beispielsweise entspricht der reguläre Ausdruck `^…$` jeder Zielzeichenfolge, die genau drei Zeichen lang ist. Der reguläre Ausdruck &quot;...&quot;stimmt mit jeder Zielzeichenfolge überein, die mindestens drei Zeichen enthält.

**Wiederholte Muster**

Mit Iterations-Metazeichen können Sie ein Muster mehrmals abgleichen.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für dieses Metazeichen ... </th> 
   <th colname="col2" class="entry"> Der Prozessor für reguläre Ausdrücke ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fragezeichen (?) </td> 
   <td colname="col2"> Ordnen Sie keine Instanzen oder eine Instanz des Zeichens unmittelbar vor dem Metazeichen (?) zu. Beispielsweise entspricht das Muster rea?d rot und gelesen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sternchen (*) </td> 
   <td colname="col2"> Übereinstimmung mit null oder mehr Vorkommen des Zeichens unmittelbar vor dem Metazeichen (*). Das Muster [0-9]* beispielsweise entspricht einer beliebigen Anzahl von Zeichen 0 bis 9 (beliebige Ganzzahl). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Übereinstimmung mit einem oder mehreren Vorkommen des vorangehenden Zeichens oder Bereichs. Beispielsweise würde das Muster Dre+ mit drei übereinstimmen, aber nicht mit durchgängig. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Passen Sie das wiederkehrende Zeichen oder den Bereich genau n Mal an. Das folgende Muster entspricht den Telefonnummern der USA: <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Obwohl dies kein optimales Muster ist, bestimmt es, ob die Zielzeichenfolge im richtigen Format vorliegt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Übereinstimmung mit dem vorangehenden Zeichen mindestens n Mal und höchstens m Mal Beispielsweise würde "fo{1,2}d"mit Lebensmitteln und Lebensmitteln übereinstimmen, jedoch nicht mit Lebensmitteln. </td> 
  </tr> 
 </tbody> 
</table>

## Musterextraktion {#section-4389779653b64f6cb7c47615b25c1a79}

Die Musterzuordnung ist nur ein Teil der Leistungsfähigkeit regulärer Ausdrücke. Reguläre Ausdrücke bieten auch einen Mechanismus zum Extrahieren von Schlüsselteilen einer Zielzeichenfolge. Dies geschieht mithilfe der linken und rechten Klammern. Diese Auszüge werden in der Regel als Eingabe in einen anderen Prozess verwendet und werden mithilfe von *%position%* aufgerufen, wobei die Position eine Ganzzahl ist, die auf die Anzahl der Klammern verweist, mit denen eine Übereinstimmung gefunden wurde.

Beachten Sie die folgenden Beispiele für die Musterextraktion:

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Muster </th> 
   <th colname="col2" class="entry"> Zeichenfolge </th> 
   <th colname="col3" class="entry"> Übereinstimmung </th> 
   <th colname="col4" class="entry"> Extraktion </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1 % = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2 % = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesson([A-Z]) </td> 
   <td colname="col2"> Lektion a </td> 
   <td colname="col3"> Keine Übereinstimmung, da niedrigere a nicht im Bereich der oberen A bis Z liegt </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>
