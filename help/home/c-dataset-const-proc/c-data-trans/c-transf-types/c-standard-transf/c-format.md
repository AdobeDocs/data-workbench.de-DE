---
description: Die Formatumwandlung benötigt eine Reihe von Eingaben und formatiert sie, um eine Ausgabe zu erstellen, die der angegebenen Struktur entspricht.
title: Format
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Format{#format}

{{eol}}

Die Formatumwandlung benötigt eine Reihe von Eingaben und formatiert sie, um eine Ausgabe zu erstellen, die der angegebenen Struktur entspricht.

Die Transformation arbeitet entweder mit einfachen Zeichenfolgen oder Zeichenfolgen-Vektoren und erzeugt eine Ausgabe, indem das angegebene Format auf jeden Eingabewert angewendet wird, bis alle Eingabewerte transformiert wurden.

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
   <td colname="col1"> Format </td> 
   <td colname="col2"> <p>Eine Formatierungszeichenfolge, die angibt, wie die Ausgabe aussehen wird. </p> <p> %1 % bezieht sich auf einen Wert aus dem ersten Eingabefvektor, %2 % auf einen Wert aus dem zweiten Eingabefvektor usw. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingaben </td> 
   <td colname="col2"> <p>Felder, die einfache Zeichenfolgen oder Zeichenfolgen-Vektoren enthalten. Bei Zeichenfolgenvektoren als Eingabe ist die Ausgabe auch ein Zeichenfolgenvektor, der aus der Anwendung der <span class="wintitle"> Format</span> auf jeden Satz von Eingabewerten fest. </p> <p> <p>Hinweis: Die Nummerierung der Eingaben beginnt bei 0, aber die Nummerierung der Formatersetzungswerte beginnt bei %1 %. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Felds, das die Ergebnisse der Umwandlung enthält. Wenn es sich bei den Eingaben um Zeichenfolgenvektoren handelt, ist die Länge des Ausgabestrategenvektors die Länge des längsten Eingabefelds. Wenn einige der Eingabezeichenfolgen-Vektoren kürzer sind, werden für ihre Position in der Formatzeichenfolge leere Zeichenfolgen verwendet, bis die Länge des Ausgabevektors erreicht ist. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel werden zwei Vektoren, eine Vektorgrafik von Zeichenfolgen, die Produktkategorien darstellen, und die andere ein entsprechender Zeichenfolgenvektor, der die Menge jedes gekauften Produkts darstellt, in einen einzigen Vektor äquivalenter Länge umgewandelt, der folgende Form aufweist: Produkt %1%, Menge %2%.

![](assets/cfg_TransformationType_Format.png)

Wenn die Eingabevektor Produktkategorien (683, 918) und Mengen (10, 4) enthielten, wäre das Ergebnis ein endgültiger Ausgabenvektor mit den folgenden beiden Zeichenfolgen: (&quot;Produkt 683, Menge 10&quot;, &quot;Produkt 918, Menge 4&quot;).
