---
description: Die REMatch-Transformation ist eine pattern-Matching-Transformation, bei der reguläre Ausdrücke verwendet werden, um ein oder mehrere Muster anzugeben, nach denen gesucht und in der Eingabe erfasst werden soll.
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 4%

---

# REMatch{#rematch}

Die REMatch-Transformation ist eine pattern-Matching-Transformation, bei der reguläre Ausdrücke verwendet werden, um ein oder mehrere Muster anzugeben, nach denen gesucht und in der Eingabe erfasst werden soll.

Die Transformation erstellt ein Ausgabefeld für jedes erfasste Untermuster im regulären Ausdruck. Wenn der reguläre Ausdruck nicht mit dem Eingabefeld übereinstimmt, sind die Ausgaben leer, und wenn das Ausgabefeld bereits vorhanden ist, werden die Werte durch die leeren Werte ersetzt. Eine kurze Anleitung zur Verwendung regulärer Ausdrücke finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>Die Umwandlung von [!DNL REMatch] funktioniert ähnlich wie die Umwandlung von [!DNL RETransform] (siehe [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), bei der reguläre Ausdrücke verwendet werden, um eine Zeichenfolge zu erfassen und diese Zeichenfolge in einem einzigen Ausgabefeld zu speichern.

[!DNL REMatch] Analysiert eine Zeichenfolge effizienter als mehrere  [!DNL RETransform] Transformationen oder eine einzelne  [!DNL RETransform] Transformation, gefolgt von einer  [!DNL Flatten] Transformation. Siehe [Reduzieren](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2"> Wahr oder falsch. Gibt an, ob bei der Übereinstimmung zwischen Groß- und Kleinschreibung unterschieden wird. </td> 
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
   <td colname="col1"> Ausgaben </td> 
   <td colname="col2"> <p>Der Name der Ausgabezeichenfolge oder des Vektors. Bei Zeichenfolgen-Vektoren als Eingabe sind die Ausgaben auch Zeichenfolgen-Vektoren. </p> <p> Für jedes erfasste Untermuster im Ausdruck muss ein Ausgabefeld vorhanden sein. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] Transformationen können sehr langsam sein und einen Großteil der Datenverarbeitungszeit ausmachen.

In diesem Beispiel analysiert eine [!DNL REMatch] -Umwandlung ein Datum im Format JJJJ-MM-TT in die Felder x-Jahr, x-Monat und x-Tag. Für das Datum 2007-01-02 würden die Werte für x-Jahr, x-Monat und x-Tag 2007, 01 bzw. 02 betragen.

![](assets/cfg_TransformationType_REMatch.png)
