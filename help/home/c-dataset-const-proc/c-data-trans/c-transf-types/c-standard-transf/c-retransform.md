---
description: Bei der Transform (Regulärer Ausdruck) handelt es sich um eine Transformation, bei der reguläre Ausdrücke verwendet werden, um ein Muster für die Suche und Erfassung in der Eingabe festzulegen und die erfasste Zeichenfolge in einem angegebenen Ausgabefeld zu speichern.
solution: Analytics
title: RETransform
topic: Data workbench
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RETransform{#retransform}

Bei der Transform (Regulärer Ausdruck) handelt es sich um eine Transformation, bei der reguläre Ausdrücke verwendet werden, um ein Muster für die Suche und Erfassung in der Eingabe festzulegen und die erfasste Zeichenfolge in einem angegebenen Ausgabefeld zu speichern.

Reguläre Ausdrücke werden mit der gesamten Eingabestaste ausgewertet. Wenn die Eingabe nicht dem im regulären Ausdruck angegebenen Muster entspricht, werden keine Daten erfasst. Eine kurze Anleitung zur Verwendung regulärer Ausdrücke finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>Die [!DNL RETransform] Transformation funktioniert ähnlich wie die [!DNL REMatch] Transformation (siehe [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), die ein Ausgabefeld für jedes erfasste Submuster im regulären Ausdruck erstellt. Man kann sich [!DNL RETransform] als eine Kombination aus [!DNL REMatch] und [!DNL Format] Transformationen vorstellen. Wenn der Parameter &quot;Aktion&quot;(siehe Aktion in der folgenden Tabelle) auf &quot;ERGEBNISSE&quot;gesetzt ist, funktioniert er [!DNL RETransform] wie eine Kombination aus [!DNL REMatch] und [!DNL Union] Transformationen.

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standardeinstellung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. </td> 
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
   <td colname="col1"> Standardeinstellung </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und der Eingabewert entweder nicht verfügbar ist oder der reguläre Ausdruck nicht mit dem Eingabewert übereinstimmt. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aktion </td> 
   <td colname="col2"> <p>Gibt an, wie das Ergebnis behandelt wird. Die Standardeinstellung von "ERGEBNISSE"nimmt einfach die entsprechenden Muster an und erstellt einen Vektor von Zeichenfolgen aus den extrahierten Mustern. </p> <p> Alternativ kann es sich bei der Aktion um eine Formatierungszeichenfolge handeln, um eine einfache Zeichenfolgenausgabe eines bestimmten Formats zu erstellen. Bei dieser Methode geben Sie die Zahl an, die der Position jedes übereinstimmenden Musters zwischen %-Zeichen entspricht. Das erste übereinstimmende Muster wäre z. B. %1 % und das dritte Muster %3 %. Sie würden in der Formatierungszeichenfolge wörtlich andere Zeichen angeben. </p> </td> 
   <td colname="col3"> ERGEBNISSE </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausdruck </td> 
   <td colname="col2"> Der reguläre Ausdruck, der für die Übereinstimmung verwendet wird. </td> 
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

Dieses Beispiel isoliert die Version des Windows-Betriebssystems, die ein Website-Besucher verwendet, und erstellt eine field x-windows-Version von diesem Wert. Der Ausgabewert wäre in diesem Fall einfach die Versionsnummer.

![](assets/cfg_TransformationType_RegularExpression.png)

Wenn Sie die Zeichenfolge &quot;Version&quot;zur Lesbarkeit vor der Versionsnummer einfügen möchten, ändern Sie den Parameter Aktion von &quot;ERGEBNISSE&quot;in &quot;Version %1%&quot;. Wenn Sie ein Prozentzeichen (%) in die Ausgabe einschließen möchten, müssen Sie dieses mit einem zweiten Prozentzeichen (%%) ausschließen.
