---
description: Wenn Sie mit Web-Daten arbeiten, können Sie die Transformation ExtractValue verwenden, um einen Wert aus einer Abfragezeichenfolge, einem Cookie oder einem ähnlich kodierten Feld in Ihren Website-Daten zu extrahieren.
title: ExtractValue
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
exl-id: 5bafe64f-081a-49ec-997e-68e8f6915a71
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# ExtractValue{#extractvalue}

Wenn Sie mit Web-Daten arbeiten, können Sie die Transformation ExtractValue verwenden, um einen Wert aus einer Abfragezeichenfolge, einem Cookie oder einem ähnlich kodierten Feld in Ihren Website-Daten zu extrahieren.

Beachten Sie, dass die Namen, die dem zu extrahierenden Wert entsprechen, in jedem Protokolleintrag unterschiedlich sein können.

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col1"> Input Name </td> 
   <td colname="col2"> <p>Die Namen der Felder, die aus der Abfrage extrahiert werden sollen. </p> <p> <p>Hinweis:  Wenn der Eingabename ein Vektor ist (d. h. mehrere Namen vorhanden sind), wird nur ein Wert extrahiert. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abfrage </td> 
   <td colname="col2"> Die kodierte Zuordnung (Abfragezeichenfolge, Cookie usw.), aus der der Wert extrahiert werden soll. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabewert </td> 
   <td colname="col2"> Der Name des Felds, das zum Erfassen des extrahierten dekodierten Werts verwendet wird. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Wenn Sie einen Suchbegriff extrahieren möchten, können Sie den gesamten Satz extrahieren und ihn bei Bedarf mithilfe einer [!DNL Tokenize] -Umwandlung in Suchbegriffe aufteilen. Weitere Informationen zur Umwandlung von [!DNL Tokenize] finden Sie unter [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

In diesem Beispiel wird eine [!DNL ExtractValue]-Umwandlung konfiguriert, um Werte des Felds x-v-search-querynames aus cs (referrer-query) zu extrahieren und im Feld x-search-Satz zu speichern.

![](assets/cfg_TransformationType_ExtractValue.png)
