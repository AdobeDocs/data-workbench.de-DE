---
description: Informationen zu Testoperationsbedingungen, einschließlich Vergleich, nicht leer, Bereich, regulärer Ausdruck und Zeichenfolgenübereinstimmung.
title: Bedingungen für Testoperationen
uuid: 6a117569-1372-4095-972b-76289a45f19e
exl-id: 6c1f521b-a6b9-4bb7-bdfa-56c615b0c916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 5%

---

# Bedingungen für Testoperationen{#test-operation-conditions}

{{eol}}

Informationen zu Testoperationsbedingungen, einschließlich Vergleich, nicht leer, Bereich, regulärer Ausdruck und Zeichenfolgenübereinstimmung.

* [Vergleichen](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [Nicht leer](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [Bereich](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [Regulärer Ausdruck](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [Zeichenfolgenübereinstimmung](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## Vergleichen {#section-fb2bdb3838504099b324b9838cdeeaac}

Die [!DNL Compare] -Bedingung vergleicht Zeichenfolge oder numerische Werte. Bei Vergleichen von Zeichenfolgenwerten können Sie angeben, ob die Groß-/Kleinschreibung berücksichtigt werden soll.

Die Parameter der [!DNL Compare] -Bedingung wird in der folgenden Tabelle beschrieben:

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2">True oder false. Wird nur verwendet, wenn der Typ <span class="wintitle"> LEXISCH</span>. Wenn der Wert auf "false"gesetzt ist, werden Groß- und Kleinbuchstaben als gleich betrachtet. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Hinweise zur Bedingung. </td> 
   <td colname="col3"> Kommentare </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe A </td> 
   <td colname="col2"> Der erste der beiden zu vergleichenden Werte. Dieser Wert stellt den linken Operanden in der Bedingung dar. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe B </td> 
   <td colname="col2"> Der zweite der beiden zu vergleichenden Werte. Dieser Wert stellt den richtigen Operand in der Bedingung dar. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Der Vergleichsvorgang. Die verfügbaren Vorgänge (und ihre Bedeutung) lauten wie folgt: 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> = oder == (Eingabe A entspricht Eingabe B) </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; oder != (Eingabe A ist nicht gleich Eingabe B) </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt; (Eingabe A ist kleiner als Eingabe B) </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;= (Eingabe A ist kleiner oder gleich Eingabe B) </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt; (Eingabe A ist größer als Eingabe B) </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;= (Eingabe A ist größer oder gleich Eingabe B) </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Typ </td> 
   <td colname="col2">Der Typ des vorzunehmenden Vergleichs. Verfügbare Typen <span class="wintitle"> LEXISCH</span>, <span class="wintitle"> NUMERISCH</span>und <span class="wintitle"> DATETIME</span>. Beschreibungen der Typen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> Testtypen für Testoperationen</a>. </td> 
   <td colname="col3"> <span class="wintitle"> LEXISCH</span> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird eine [!DNL Compare] -Bedingung, um die [!DNL Log Entry Condition]. Während der Data Workbench-Server jeden Ereignisdatensatz liest, werden die numerischen Werte x-age und 55 verglichen. Wenn für einen bestimmten Protokolleintrag x-age kleiner oder gleich 55 ist, wird der Protokolleintrag in den Prozess der Datensatzerstellung einbezogen.

![](assets/cfg_Condition_CompareCondition.png)

## Nicht leer {#section-1decb9d887894073a1b6b3d985729ac8}

Die [!DNL Not Empty] -Bedingung überprüft ein Feld, um festzustellen, ob es einen Wert enthält oder leer ist. Die Bedingung ist für jeden Protokolleintrag erfüllt, dessen Wert für die [!DNL Input] -Feld nicht leer ist.

Die Parameter der [!DNL Not Empty] -Bedingung wird in der folgenden Tabelle beschrieben:

| Parameter | Beschreibung | Standard |
|---|---|---|
| Kommentare | Optional. Hinweise zur Bedingung. | Kommentare |
| Eingabe | Der Name des Felds aus dem Protokolleintrag, das auf Inhalt überprüft werden soll. |  |

In diesem Beispiel wird als Eingabe-X-some-field geprüft, ob das Feld nicht leer ist. Die Bedingung ist erfüllt, wenn das Feld ausgefüllt wird.

![](assets/cfg_Condition_NotEmpty.png)

## Bereich {#section-1db31583bb09418b8f49481a897b08a6}

Die [!DNL Range] -Bedingung nimmt ein Eingabefeld und bestimmt, ob der Wert dieses Felds einschließlich innerhalb der angegebenen Mindest- (Min) und Maximalwerte (Maximal) liegt.

Die Parameter der [!DNL Range] -Bedingung wird in der folgenden Tabelle beschrieben:

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2">True oder false. Wird nur verwendet, wenn die Variable <span class="wintitle"> Typ</span> is <span class="wintitle"> LEXISCH</span>. Wenn der Wert auf "false"gesetzt ist, werden Groß- und Kleinbuchstaben als gleich betrachtet. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Hinweise zur Bedingung. </td> 
   <td colname="col3"> Kommentare </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Name des Felds aus dem Protokolleintrag, das als Eingabe verwendet werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> <p>Untergrenze des Bereichs. </p> <p> Der Wert dieses Parameters muss ein Literalwert oder eine Zeichenfolge sein - kein Feldname. Wenn Sie ein Datum für dieses Feld verwenden, müssen Sie eine Zeitzone angeben. Eine Liste der unterstützten Abkürzungen für Zeitzonen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes</a>. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max. </td> 
   <td colname="col2"> <p>Obergrenze des Bereichs. </p> <p> <p>Hinweis: Der Wert dieses Parameters muss ein Literalwert oder eine Zeichenfolge sein - kein Feldname. Wenn Sie ein Datum für dieses Feld verwenden, müssen Sie eine Zeitzone angeben. Eine Liste der unterstützten Abkürzungen für Zeitzonen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Zeitzonencodes</a>. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Typ </td> 
   <td colname="col2">Der Typ des vorzunehmenden Vergleichs. Verfügbare Typen <span class="wintitle"> LEXISCH</span>, <span class="wintitle"> NUMERISCH</span>und <span class="wintitle"> DATETIME</span>. Beschreibungen der Typen finden Sie unter <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> Testtypen für Testoperationen</a>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird eine [!DNL Range] -Bedingung, um die [!DNL Log Entry Condition]. Wenn der Data Workbench-Server jede [!DNL event data] -Datensatz, werden die numerischen Werte x-age und 55 verglichen. Wenn für einen bestimmten Protokolleintrag x-age mindestens 55 ist, ist der Protokolleintrag im Prozess der Datensatzerstellung enthalten. In diesem Beispiel wird dieselbe Funktion wie bei der [!DNL Compare] -Bedingungsbeispiel. Siehe [Vergleichen](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac).

>[!NOTE]
>
>Wenn der Parameter Min oder Max leer gelassen wird, ersetzt der Data Workbench-Server die verfügbaren minimalen oder maximalen ganzzahligen Werte. Der Mindestwert ist null (0) und der Höchstwert unendlich.

![](assets/cfg_Condition_RangeCondition.png)

## Regulärer Ausdruck {#section-ae9c016502cb44128760c58f2d2d5297}

Die [!DNL Regular Expression] Bedingungstest verwendet die Übereinstimmung von regulären Ausdrücken (siehe [Reguläre Ausdrücke](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)), um zu bestimmen, ob der Wert des angegebenen Eingabefelds eine Zeichenfolge enthält, die mit einem der im Parameter Übereinstimmung angegebenen Muster übereinstimmt.

Wenn die Eingabe ein Vektor von Zeichenfolgen ist, wird nur der erste Wert im Vektor für den Test verwendet. Die [!DNL Regular Expression] -Bedingung führt vollständige Zeichenfolgenvergleiche durch. Wenn Sie Unterzeichenfolgen identifizieren möchten, müssen Sie &quot;&quot;voranstellen und anhängen.&#42;&quot; in die Zeichenfolge ein.

Die Parameter der [!DNL Regular Expression] -Bedingung wird in der folgenden Tabelle beschrieben:

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2"> True oder false. Wenn der Wert auf "false"gesetzt ist, werden Groß- und Kleinbuchstaben als gleich betrachtet. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Hinweise zur Bedingung. </td> 
   <td colname="col3"> Kommentare </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Name des Felds aus dem Protokolleintrag, das als Eingabe verwendet werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stimmt überein mit </td> 
   <td colname="col2"> <p>Die Muster für reguläre Ausdrücke, die mit dem Wert des Eingabefelds abgeglichen werden sollen. </p> <p> <b> So fügen Sie ein Muster für reguläre Ausdrücke hinzu</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">Rechtsklick <span class="uicontrol"> Stimmt überein mit</span>. </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">Klicken <span class="uicontrol"> Neu hinzufügen</span> &gt; <span class="uicontrol"> Regulärer Ausdruck</span>. </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">Geben Sie den gewünschten regulären Ausdruck in das Textfeld ein. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Dieses Beispiel veranschaulicht die Verwendung des [!DNL Regular Expression] -Bedingung, um ein Feld mit Daten abzugleichen, die aus dem Website-Traffic erfasst wurden. Die Bedingung gibt &quot;true&quot;nur zurück, wenn das Feld cs(referrer-query) eine Zeichenfolge enthält, die mit dem regulären Ausdruck übereinstimmt `campaign=C[1-9][0-9]{4}`. Dieser reguläre Ausdruck entspricht allen Zeichenfolgen, die `campaign=C12345`. Das Muster entsprach jedoch nicht der Zeichenfolge `campaign=C0123&` weil das erste Zeichen nach dem `C` nicht im Bereich liegt `1-9`.

![](assets/cfg_Condition_RegularExpression.png)

## Zeichenfolgenübereinstimmung {#section-f8d132085c6b4500bfbe4515b848142f}

Die [!DNL String Match] Bedingungstests für die Zeichenfolgengleichheit. Es nimmt ein bestimmtes Feld als Eingabe und testet den Wert dieses Felds in jedem Protokolleintrag anhand der im Parameter Matches des Vorgangs angegebenen Zeichenfolgen. Wenn eine dieser übereinstimmenden Zeichenfolgen, bei denen zwischen Groß- und Kleinschreibung unterschieden wird, mit dem Wert im bereitgestellten Eingabefeld übereinstimmt, gibt der Vorgang &quot;true&quot;zurück. In dem Ereignis wird die [!DNL StringCondition] keine Übereinstimmungszeichenfolgen enthält, gibt die Bedingung &quot;false&quot;zurück. Wenn die Eingabe ein Vektor von Zeichenfolgen ist, wird nur der erste Wert (Zeichenfolge) im Vektor für den Test verwendet.

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2"> True oder false. Wenn der Wert auf "false"gesetzt ist, werden Groß- und Kleinbuchstaben als gleich betrachtet. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Hinweise zur Bedingung. </td> 
   <td colname="col3"> Kommentare </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Name des Felds aus dem Protokolleintrag, das als Eingabe verwendet werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stimmt überein mit </td> 
   <td colname="col2"> <p>Die Zeichenfolge(n), die mit dem Wert des Eingabefelds abgeglichen werden soll(en). </p> <p> <b>So fügen Sie eine Zeichenfolge hinzu</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE">Rechtsklick <span class="uicontrol"> Stimmt überein mit</span>. </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">Klicken <span class="uicontrol"> Neu hinzufügen</span> &gt; <span class="uicontrol"> Zeichenfolge</span>. </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">Geben Sie die gewünschte Zeichenfolge in das Textfeld ein. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel werden Daten aus dem Website-Traffic verwendet, um die Verwendung der [!DNL String Match] Bedingung. Die Bedingung testet, ob das Eingabefeld (cs-uri-stamm) mit einer der beiden im Parameter Matches angegebenen Zeichenfolgen übereinstimmt, und es ist erfolgreich, wenn das Feld cs-uri-stamm entweder die exakte Zeichenfolge ist [!DNL /navigation/footer.asp] oder der exakten Zeichenfolge [!DNL /navigation/header.asp].

![](assets/cfg_Condition_StringMatch.png)
