---
description: Die Formattransformation nimmt eine Reihe von Eingaben und Formaten, um eine Ausgabe zu erstellen, die der angegebenen Struktur entspricht.
title: Format
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Format{#format}

Die Formattransformation nimmt eine Reihe von Eingaben und Formaten, um eine Ausgabe zu erstellen, die der angegebenen Struktur entspricht.

Die Transformation funktioniert entweder mit einfachen Zeichenfolgen oder Zeichenfolgen-Vektoren und erzeugt eine Ausgabe, indem das angegebene Format auf jeden Eingabewert angewendet wird, bis alle Eingabewerte transformiert wurden.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col2"> <p>Felder, die einfache Zeichenfolgen oder Zeichenfolgen-Vektoren enthalten. Bei Zeichenfolgen-Vektoren als Eingabe ist die Ausgabe auch ein Zeichenfolgenvektor, der sich aus der Anwendung des Parameters <span class="wintitle"> Format</span> auf jeden Satz von Eingabewerten ergibt. </p> <p> <p>Hinweis:  Die Nummerierung der Eingaben Beginn bei 0, aber die Nummerierung der Formatsubstitutionswerte Beginn bei %1 %. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Felds, das für die Ergebnisse der Transformation erstellt wurde. Handelt es sich bei den Eingaben um Zeichenfolgen-Vektoren, ist die Länge des Ausgabestring-Vektors die Länge des längsten Eingabefelds. Wenn einige der Vektoren der Eingabestaste kürzer sind, werden für ihre Position in der Formatzeichenfolge leere Zeichenfolgen verwendet, bis die Länge des Ausgabekreises erreicht ist. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel werden zwei Vektoren, eine Vektorgrafik für Produktzeichenfolgen und die andere eine entsprechende Zeichenfolgen-Vektorgrafik, die die Kategorie der einzelnen gekauften Produkte darstellt, in einen einzigen Vektor mit gleicher Länge umgewandelt, der folgende Form annimmt: Produkt %1%, Menge %2%.

![](assets/cfg_TransformationType_Format.png)

Enthalten die Eingabevektor Kategorien von (683, 918) und Mengen von (10, 4), wäre ein Endausgabevektor mit den folgenden beiden Zeichenfolgen zu sehen: (&quot;Produkt 683, Menge 10&quot;, &quot;Produkt 918, Menge 4&quot;).
