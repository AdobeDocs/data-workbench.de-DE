---
description: Die Formattransformation nimmt eine Reihe von Eingaben und Formaten, um eine Ausgabe zu erstellen, die der angegebenen Struktur entspricht.
solution: Analytics
title: Format
topic: Data workbench
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Format{#format}

Die Formattransformation nimmt eine Reihe von Eingaben und Formaten, um eine Ausgabe zu erstellen, die der angegebenen Struktur entspricht.

Die Transformation funktioniert entweder mit einfachen Zeichenfolgen oder Zeichenfolgen-Vektoren und erzeugt eine Ausgabe, indem das angegebene Format auf jeden Eingabewert angewendet wird, bis alle Eingabewerte transformiert wurden.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> Format </td> 
   <td colname="col2"> <p>Eine Formatierungszeichenfolge, die das Aussehen der Ausgabe angibt. </p> <p> %1% bezieht sich auf einen Wert aus dem ersten Eingabecvektor, %2% auf einen Wert aus dem zweiten Eingabecvektor usw. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingänge </td> 
   <td colname="col2"> <p>Felder, die einfache Zeichenfolgen oder Zeichenfolgen-Vektoren enthalten. Bei Zeichenfolgen-Vektoren als Eingabe ist die Ausgabe auch ein Zeichenfolgenvektor, der sich aus der Anwendung des Parameters <span class="wintitle"> Format</span> auf jeden Satz von Eingabewerten ergibt. </p> <p> <p>Hinweis:  Die Nummerierung der Eingaben beginnt bei 0, aber die Nummerierung der Formatsubstitutionswerte beginnt bei %1 %. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Felds, das für die Ergebnisse der Transformation erstellt wurde. Handelt es sich bei den Eingaben um Zeichenfolgen-Vektoren, ist die Länge des Ausgabestring-Vektors die Länge des längsten Eingabefelds. Wenn einige der Vektoren der Eingabestaste kürzer sind, werden für ihre Position in der Formatzeichenfolge leere Zeichenfolgen verwendet, bis die Länge des Ausgabekreises erreicht ist. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel werden zwei Vektoren, einer ein Vektor von Zeichenfolgen, die Produktkategorien darstellen, und der andere ein entsprechender Zeichenfolgenvektor, der die Menge jedes gekauften Produkts darstellt, in einen einzigen Vektor gleicher Länge umgewandelt, der folgende Form hat: Produkt %1%, Menge %2%.

![](assets/cfg_TransformationType_Format.png)

Enthalten die Eingabevektor die Produktkategorien (683, 918) und die Mengen (10, 4), wäre das Ergebnis ein finaler Ausgabenvektor, der die folgenden beiden Zeichenfolgen enthält: (&quot;Produkt 683, Menge 10&quot;, &quot;Produkt 918, Menge 4&quot;).
