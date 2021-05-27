---
description: Die RETransform-Transformation (regulärer Ausdruck) ist eine pattern-Matching-Transformation, die mithilfe regulärer Ausdrücke ein Muster angibt, nach dem gesucht und erfasst werden soll, und die erfasste Zeichenfolge in einem dafür vorgesehenen Ausgabefeld speichert.
title: RETransform
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
exl-id: 2595f782-0efb-4a2a-84bd-fdb04baf0852
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 3%

---

# RETransform{#retransform}

Die RETransform-Transformation (regulärer Ausdruck) ist eine pattern-Matching-Transformation, die mithilfe regulärer Ausdrücke ein Muster angibt, nach dem gesucht und erfasst werden soll, und die erfasste Zeichenfolge in einem dafür vorgesehenen Ausgabefeld speichert.

Reguläre Ausdrücke werden mit der gesamten Eingabezeichenfolge ausgewertet. Wenn die Eingabe nicht dem im regulären Ausdruck angegebenen Muster entspricht, werden keine Daten erfasst. Eine kurze Anleitung zur Verwendung regulärer Ausdrücke finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>Die Umwandlung von [!DNL RETransform] funktioniert ähnlich wie die Umwandlung von [!DNL REMatch] (siehe [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), die ein Ausgabefeld für jedes erfasste Untermuster im regulären Ausdruck erstellt. [!DNL RETransform] können Sie sich [!DNL REMatch] als eine Kombination aus  und [!DNL Format] Transformationen vorstellen. Wenn der Aktionsparameter (siehe Aktion in der folgenden Tabelle) auf &quot;ERGEBNISSE&quot;festgelegt ist, funktioniert [!DNL RETransform] wie eine Kombination aus [!DNL REMatch] und [!DNL Union] Transformationen.

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert entweder nicht verfügbar ist oder der reguläre Ausdruck nicht mit dem Eingabewert übereinstimmt. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aktion </td> 
   <td colname="col2"> <p>Gibt an, wie das Ergebnis behandelt wird. Die Standardeinstellung von RESULTS übernimmt einfach die übereinstimmenden Muster und erstellt einen Vektor von Zeichenfolgen aus den extrahierten Mustern. </p> <p> Alternativ kann die Aktion eine Formatierungszeichenfolge sein, um eine einfache Zeichenfolgenausgabe eines bestimmten Formats zu erstellen. Bei dieser Technik geben Sie die Zahl an, die der Position jedes übereinstimmenden Musters zwischen Prozentzeichen entspricht. Beispielsweise wäre das erste übereinstimmende Muster %1 % und das dritte passende Muster %3 %. Sie würden in der Formatierungszeichenfolge wörtlich andere Zeichen angeben. </p> </td> 
   <td colname="col3"> ERGEBNISSE </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausdruck </td> 
   <td colname="col2"> Der reguläre Ausdruck, der für die Zuordnung verwendet wird. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Das Feld, mit dem der reguläre Ausdruck ausgewertet wird. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name der Ausgabezeichenfolge. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] Transformationen können sehr langsam sein und einen Großteil der Datenverarbeitungszeit ausmachen.

Dieses Beispiel isoliert die Version des Windows-Betriebssystems, das ein Website-Besucher verwendet, und erstellt eine Feld x-windows-Version von diesem Wert. Der Ausgabewert wäre in diesem Fall einfach die Versionsnummer.

![](assets/cfg_TransformationType_RegularExpression.png)

Wenn Sie die Zeichenfolge &quot;Version&quot;vor der Versionsnummer einbeziehen möchten, um die Lesbarkeit zu gewährleisten, ändern Sie den Aktionsparameter von &quot;ERGEBNISSE&quot;in &quot;Version %1%&quot;. Wenn Sie ein literales Prozentzeichen (%) in Ihre Ausgabe aufnehmen möchten, müssen Sie dieses mit einem zweiten Prozentzeichen als &quot;%%&quot;ausdrücken.
