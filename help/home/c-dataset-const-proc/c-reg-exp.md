---
description: Reguläre Ausdrücke werden in allen Data Workbench-Suchfeldern einschließlich der Abfrageentitätsbedienfelder verwendet.
solution: Analytics
title: Reguläre Ausdrücke
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Regular Expressions{#regular-expressions}

Reguläre Ausdrücke werden in allen Data Workbench-Suchfeldern einschließlich der Abfrageentitätsbedienfelder verwendet.

* [Über reguläre Ausdrücke](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologie regulärer Ausdrücke](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Grundlagen zur Literalübereinstimmung](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Metazeichen verwenden](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Musterextrahierung](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Über reguläre Ausdrücke {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Ein regulärer Ausdruck ist ein Textmuster, das aus einer Kombination aus alphanumerischen Zeichen und Sonderzeichen, so genannten Metazeichen, besteht, die Muster suchen und Unterzeichenfolgen aus Text extrahieren. Reguläre Ausdrücke werden in der Computerprogrammierung weit verbreitet und sind integraler Bestandteil von Sprachen wie Perl.

Zur Identifizierung und Extrahierung komplexer Zeichenfolgenmuster verwendet der Data Workbench-Server in einigen der Transformationen und Bedingungen reguläre Ausdrücke. Im Folgenden finden Sie eine kurze Anleitung zu regulären Ausdrücken.

Dieser Anhang ist keine umfassende Einführung in reguläre Ausdrücke. Eine besonders gute Referenz ist die O&#39;Reilly Veröffentlichung *Mastering Regular Expressions, 2. Ausgabe* von Jeffrey E. F. Friedl.

## Terminologie regulärer Ausdrücke {#section-80b0d54f731e448391532ab3eb3c525c}

| Begriff | Definition |
|---|---|
| Literal | Ein Literal ist ein Zeichen, das wir in einem regulären Ausdruck verwenden, um eine bestimmte Zeichenfolge zu finden. Um zum Beispiel ein Produkt in zu finden, [!DNL shop/products.html]ist das String-Produkt ein Literal oder was wir buchstäblich in der Zeichenfolge suchen. |
| Metazeichen | Ein Metazeichen ist ein Sonderzeichen mit einer eindeutigen Interpretation im Kontext regulärer Ausdrücke. Beispiel: Der Zeitraum (.) ist ein Metazeichen, mit dem einem beliebigen Zeichen entsprochen wird. |
| Escape-Sequenz | Eine Escape-Sequenz ist einfach eine Möglichkeit, der Engine für reguläre Ausdrücke zu sagen, dass wir eines der Metazeichen als Literal verwenden möchten. Escape-Sequenzen beginnen immer mit dem umgekehrten Schrägstrich (`\`). Durch Platzierung des Backslash (der auch ein Metazeichen ist) vor einem Metazeichen interpretiert die Engine für reguläre Ausdrücke das mit Escapezeichen versehene Metazeichen als Literal. Wenn Sie beispielsweise den Metazeichenzeitraum (`.`) einhalten möchten, müssen Sie eine Escape-Sequenz verwenden. Um jedoch einem der Punkte in der Zeichenfolge 168.196.0.11 zu entsprechen, können Sie den regulären Ausdruck verwenden, der aus einem umgekehrten Schrägstrich und einem Punkt (`\.`) besteht. |
| Muster | Dies ist eine kurze Terminologie für den regulären Ausdruck. Ein regulärer Ausdruck ist im Wesentlichen ein Muster, das Sie mit der Zielzeichenfolge abgleichen möchten. |
| Zielzeichenfolge | Dieser Begriff bezieht sich auf die Zeichenfolge, in der wir nach dem gewünschten Muster suchen. |

## Grundlagen zur Literalübereinstimmung {#section-ec4497e3160c47ba9b828d939761b3e0}

Bei der Literalübereinstimmung wird eine Zeichenfolge ohne Escape-Zeichen verwendet und in der Zielzeichenfolge wird geprüft, ob es sich um eine Unterzeichenfolge der Zielzeichenfolge handelt.

In diesem Beispiel sehen Sie, wie wörtliche Übereinstimmung funktioniert. Betrachten Sie eine Situation, in der Daten aus dem Website-Traffic erfasst werden und das Feld cs(referrer) den folgenden Wert enthält:

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Um festzustellen, ob die verweisende Stelle eine Person darstellt, die auf eine der Anzeigen geklickt hat, müssen Sie sehen, ob die verweisende Stelle die Zeichenfolgenanzeige enthält. Sie können die Zeichenfolgenanzeige einfach dazu verwenden, die Zielzeichenfolge zu durchsuchen und festzustellen, ob eine Werbung verwendet wurde, um den Traffic zur Site zu leiten. Obwohl dies mit der Zielzeichenfolge übereinstimmen würde, würde sie an zwei Stellen übereinstimmen und ist daher mehrdeutig und kann zu Falsch-Positiv-Werten führen.

Die folgende URL enthält die Zeichenfolgenanzeige an zwei verschiedenen Stellen:

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Wenn Sie also versuchen, festzustellen, welche Sitzungen als Ergebnis einer bestimmten Werbekampagne gestartet wurden, reicht die einfache Verwendung der wörtlichen Anzeige als regulärer Ausdruck eindeutig nicht aus. Wenn Sie das Literal in &quot;ad=&quot;ändern, wird diese Unklarheit beseitigt, sodass der Ausdruck nur eine Übereinstimmung ergibt. Auch dies reicht möglicherweise nicht aus, um sicherzustellen, dass die verweisende Stelle Teil der Werbekampagne war. Betrachten Sie die folgende verweisende Stelle:

`http://www.xyz.com/hello.html?pad=something`

Sie haben keine Kontrolle über die URLs, die andere zum Erstellen von Links zur Site verwenden. Die wörtliche Zuordnung ist zu einfach, um Sitzungen zu finden, die als Ergebnis der Werbekampagne gestartet wurden. Im folgenden Abschnitt wird erläutert, wie Sie Metazeichen für flexiblere und leistungsfähigere Übereinstimmungen verwenden können.

## Metazeichen verwenden {#section-e29a804336304ea1ba33d40d60139aa2}

Ein Metazeichen ist ein Sonderzeichen in einem Programm- oder Datenfeld, das Informationen zu anderen Zeichen bereitstellt.

| Metazeichen | Beschreibung |
|---|---|
| . (Punkt) | Entspricht einem einzelnen Zeichen, z. B.: Entspricht `re:x.z` &quot;xyz&quot;oder &quot;xxz&quot;. |
| * (Stern) | Entspricht einem oder mehreren Zeichen, z. B.: Spiele `re:Z*` &quot;ZZZ&quot;. |
| ? (Platzhalter) | Sucht nach 0 oder 1 des vorherigen Ausdrucks, um eine minimale Übereinstimmung zu erzwingen, z. B.: Entspricht `xy?z` &quot;xy&quot;und &quot;xyz&quot;. |

Zusätzliche reguläre Ausdrücke können auch verwendet werden, um komplexere Suchzeichenfolgen zu erstellen.

**Listen, Bereiche und ODER**

Bei der Literalzuordnung können Sie nach einer einzelnen Zeichenfolge suchen. Mit Klammern, Bindestrichen und Rohren können Sie jedoch eine Liste der Elemente definieren, nach denen in der Zielzeichenfolge gesucht werden soll.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für dieses Metazeichen... </th> 
   <th colname="col2" class="entry"> Der Prozessor für reguläre Ausdrücke... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eckige Klammern ([ ]) </td> 
   <td colname="col2"> Ordnen Sie einem beliebigen Zeichen in der Klammer eine einzelne Zeichenposition zu. Beispielsweise ist [AB] eine Anweisung, entweder den Buchstaben A oder B zuzuordnen, und [0123456789] sagt, dass eine Übereinstimmung mit einem beliebigen Zeichen im Bereich von 0 bis 9 vorliegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Strich (-) </td> 
   <td colname="col2"> <p>Stimmt mit einem Zeichenbereich überein. Anstatt also [0123456789] zu schreiben, konnten wir einfach [0-9] schreiben. </p> <p> Dies kann auf Zeichenbereiche und mehrere Bereiche innerhalb eines Satzes von Klammern erweitert werden. [0-9A-C] entspricht beispielsweise den Zeichen 0 bis 9 und A bis C. </p> <p> <p>Hinweis:  Um einen Bindestrich (-) als Literal in den Klammern zu testen, muss er an erster oder letzter Stelle stehen. Beispiel: [-0-9] Tests für - und 0 bis 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verkettungszeichen (|) </td> 
   <td colname="col2"> Ordnen Sie eine der beiden Optionen einer angegebenen Zielzeichenfolge zu. Beispiel: "b|nat"entspricht entweder "bat"oder "nat". </td> 
  </tr> 
 </tbody> 
</table>

Sehen Sie sich folgende Beispiele an:

| Muster | Zeichenfolge | Übereinstimmung |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lektion`[A-Z]` | Lektion a | Keine Übereinstimmung, da a in der unteren Leiste nicht im Bereich der oberen Leiste A bis Z liegt. |

**Negation**

Negation ist eine Möglichkeit, zu sagen, dass Sie alles mit Ausnahme der angegebenen Zeichen übereinstimmen möchten. Das Negations-Metazeichen Zirkumflex oder Caret (`^`) wird als erstes Zeichen in Klammern verwendet, um zu sagen, dass es sich bei der Übereinstimmung um alles andere als die restlichen Zeichen in den Klammern handeln soll. Wenn Sie beispielsweise ein beliebiges Zeichen außer einem Semikolon (`;`) abgleichen möchten, schreiben Sie

[`^;`]

Dies würde mit allen Zeichen außer dem Semikolon übereinstimmen.

**Positionierung**

Um eine Übereinstimmung am Anfang oder am Ende einer Zielzeichenfolge zu erzwingen, wird eines von zwei Metazeichen verwendet.

| Für dieses Metazeichen... | Der Prozessor für reguläre Ausdrücke... |
|---|---|
| Circumflex oder Caret (`^`) | Übereinstimmung mit dem Anfang der Zeichenfolge. Beispiel: ^`[Tt]`er würde mit der Zielzeichenfolge &quot;Der Anfang&quot;übereinstimmen, aber nicht mit &quot;Dies ist der Anfang&quot;. |
| Dollarzeichen (`$`) | Übereinstimmung mit dem Ende der Zeichenfolge. So würde `[Ee]`nd$ z. B. mit &quot;This is the end&quot;übereinstimmen, aber nicht mit &quot;The end is a special time&quot;. |

>[!NOTE]
>
>Wenn der reguläre Ausdruck ^ am Anfang und $ am Ende enthält, muss die gesamte Zielzeichenfolge mit dem regulären Ausdruck übereinstimmen.

**Übereinstimmung mit allem**

Der Zeitraum (.) ist ein spezielles Metazeichen, das mit jedem beliebigen Zeichen in der Zielzeichenfolge übereinstimmt. Der reguläre Ausdruck `^…$` stimmt beispielsweise mit jeder Zielzeichenfolge überein, die genau drei Zeichen lang ist. Der reguläre Ausdruck &quot;...&quot;stimmt mit jeder Zielzeichenfolge überein, die mindestens drei Zeichen enthält.

**Wiederholte Muster**

Mit Metazeichen für Iterationen können Sie ein Muster mehrmals abgleichen.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für dieses Metazeichen... </th> 
   <th colname="col2" class="entry"> Der Prozessor für reguläre Ausdrücke... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fragezeichen (?) </td> 
   <td colname="col2"> Ordnen Sie keine Instanzen oder eine Instanz des Zeichens unmittelbar vor dem Metazeichen (?) zu. Das Muster "rea?d"entspricht beispielsweise Rot und Lesen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sternchen (*) </td> 
   <td colname="col2"> Sucht nach null oder mehreren Vorkommen des Zeichens unmittelbar vor dem Metazeichen (*). Das Muster [0-9]* entspricht beispielsweise einer beliebigen Zahl der Zeichen 0 bis 9 (beliebige Ganzzahl). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Entspricht einem oder mehreren Vorkommen des vorherigen Zeichens oder Bereichs. Das Muster dre+ würde beispielsweise mit drei übereinstimmen, jedoch nicht mit der Durchmusterung. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Ordnen Sie dem Zeichen oder Bereich des Vorgangs exakt n Male zu. Das folgende Muster stimmt mit den Telefonnummern in den USA überein: [0-9]{3}-[0-9]{3}-[0-9]{4}. </p> <p> Es ist zwar kein optimales Muster, bestimmt aber, ob die Zielzeichenfolge im richtigen Format vorliegt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Ordnen Sie das vorhergehende Zeichen mindestens n- und höchstens m-mal zu. So würde z. B. "fo{1,2}d"mit Lebensmitteln und Lebensmitteln übereinstimmen, jedoch nicht mit Lebensmitteln. </td> 
  </tr> 
 </tbody> 
</table>

## Musterextrahierung {#section-4389779653b64f6cb7c47615b25c1a79}

Die Musterübereinstimmung ist nur ein Teil der Stärke von regulären Ausdrücken. Reguläre Ausdrücke bieten auch einen Mechanismus zum Extrahieren wichtiger Teile einer Zielzeichenfolge. Dies geschieht mithilfe der Klammern links und rechts. Diese Extraktionen werden in der Regel als Eingabe in einen anderen Prozess verwendet und über die Verwendung von *%position%* aufgerufen, wobei die Position eine Ganzzahl ist, die auf die Anzahl der Klammern verweist, die übereinstimmen.

Betrachten Sie die folgenden Beispiele für die Musterextraktion:

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
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lektion([A-Z]) </td> 
   <td colname="col2"> Lektion a </td> 
   <td colname="col3"> Keine Übereinstimmung, da a mit niedrigerem Gehäuse nicht im Bereich der oberen A bis Z liegt </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

