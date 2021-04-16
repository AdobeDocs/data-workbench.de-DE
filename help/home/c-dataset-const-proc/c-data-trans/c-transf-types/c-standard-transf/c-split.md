---
description: Bei der Transformation "Teilen"wird eine Zeichenfolge basierend auf einem gegebenen Trennzeichen in einen Vektor von Unterzeichenfolgen unterteilt.
title: Split
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
exl-id: ea85b095-1306-4938-906d-35d421db6c98
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 3%

---

# Split{#split}

Bei der Transformation &quot;Teilen&quot;wird eine Zeichenfolge basierend auf einem gegebenen Trennzeichen in einen Vektor von Unterzeichenfolgen unterteilt.

[!DNL Split] ist besonders hilfreich, um einzelne Werte aus einer Wertsammlung zu extrahieren, die mit einem einzelnen URI-Abfragen-Namenswert verknüpft ist.

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>String, der zum Trennen der Eingabestruktur in Teilzeichenfolgen verwendet wird. Muss ein einzelnes Zeichen lang sein. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste in den Trennzeichner-Parameter klicken, wird ein Menü "Einfügen"angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Name des Felds, dessen Wert geteilt wird, um den Ausgabezeichenfolgen-Vektor zu erstellen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Ausgabefelds. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Betrachten Sie eine Website, auf der die von einem Kunden erworbenen Produkte als Teil des Werts &quot;cs-uri-Abfrage&quot;aufgeführt werden, wenn auf die Bestätigungsseite für einen erfolgreichen Kauf zugegriffen wird. Die folgende Tabelle zeigt ein Beispiel für eine solche Zeichenfolge:

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

Das cs-uri-Stammfeld wird verwendet, um zu bestimmen, ob die vom Protokolleintrag angeforderte Seite die Bestätigungsseite ist. Die Produktcodes für die vom Kunden erworbenen Produkte werden als kommagetrennte Werte des Typs &quot;prod_selected&quot;in der Abfrage &quot;cs-uri&quot;aufgeführt. Die [!DNL Split]-Transformation kann verwendet werden, um diese Informationen zu extrahieren, indem die Produktcodes am Komma aufgeteilt werden, wenn der Wert des cs-uri-Stammes mit dem in der Bedingung [!DNL String Match] angegebenen Wert übereinstimmt. Siehe [String Match](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). Die folgende Transformation beschreibt die Lösung dieses Problems.

![](assets/cfg_TransformationType_Split.png)

Hier ist das Ausgabefeld x-products, das verwendet wird, um die gewünschte erweiterte Dimension zu erstellen, die die gekauften Produkte den Sitzungen zuordnet, während denen der Kauf erfolgte.
