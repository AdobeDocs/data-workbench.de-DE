---
description: Die Aufspaltung teilt eine Zeichenfolge basierend auf einem angegebenen Trennzeichen in einen Vektor von Unterzeichenfolgen auf.
title: Split
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
exl-id: ea85b095-1306-4938-906d-35d421db6c98
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 3%

---

# Aufspaltung{#split}

{{eol}}

Die Aufspaltung teilt eine Zeichenfolge basierend auf einem angegebenen Trennzeichen in einen Vektor von Unterzeichenfolgen auf.

[!DNL Split] ist besonders nützlich, um einzelne Werte aus einer Sammlung von Werten zu extrahieren, die mit einem einzelnen URI-Abfragenamenwert verknüpft sind.

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
   <td colname="col2"> Deskriptiver Name der Transformation. Hier können Sie einen beliebigen Namen eingeben. </td> 
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
   <td colname="col2"> <p>Zeichenfolge, die zum Trennen der Eingabezeichenfolge in Unterzeichenfolgen verwendet wird. Muss ein einzelnes Zeichen in der Länge sein. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste im Trennzeichen-Parameter klicken, wird das Menü Einfügen angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Name des Felds, dessen Wert geteilt wird, um den Ausgabezeichenfolgenvektor zu erstellen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Ausgabefelds. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Stellen Sie sich eine Website vor, auf der die von einem Kunden gekauften Produkte als Teil des Abfragewerts &quot;cs-uri-Query&quot;aufgeführt werden, wenn auf die Bestätigungsseite zugegriffen wird, die mit einem erfolgreichen Kauf verknüpft ist. Im Folgenden finden Sie ein Beispiel für eine solche Zeichenfolge:

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

Das Feld &quot;cs-uri-stamm&quot;wird verwendet, um zu bestimmen, ob die vom Protokolleintrag angeforderte Seite die Bestätigungsseite ist. Die Codes für die Produkte, die der Kunde gekauft hat, werden in der cs-uri-Abfrage als kommagetrennte Werte für den Namen prod_selected aufgeführt. Die [!DNL Split] Die Umwandlung kann verwendet werden, um diese Informationen zu extrahieren, indem die Produktcodes am Komma aufgeteilt werden, wenn der Wert von cs-uri-stämmen mit dem in der [!DNL String Match] Bedingung. Siehe [Zeichenfolgenübereinstimmung](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). Die folgende Transformation beschreibt die Lösung dieses Problems.

![](assets/cfg_TransformationType_Split.png)

Hier ist das Ausgabefeld x-products , mit dem die gewünschte erweiterte Dimension erstellt wird, die die gekauften Produkte den Sitzungen zuordnet, in denen der Kauf getätigt wurde.
