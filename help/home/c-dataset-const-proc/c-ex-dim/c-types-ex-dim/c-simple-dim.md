---
description: Eine einfache Dimension hat eine Eins-zu-viele-Beziehung zu ihrer übergeordneten zählbaren Dimension.
solution: Analytics
title: Einfache Dimensionen
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Einfache Dimensionen{#simple-dimensions}

Eine einfache Dimension hat eine Eins-zu-viele-Beziehung zu ihrer übergeordneten zählbaren Dimension.

Eine einfache Dimension ist immer ein untergeordnetes Element einer zählbaren Dimension. Sie können sich eine einfache Dimension als Darstellung einer Eigenschaft der Elemente in ihrer übergeordneten Dimension vorstellen. Wenn Sie z. B. mit Webdaten arbeiten, können Sie die Dimension &quot;Referrer&quot;des Besuchers definieren, bei der es sich um eine einfache Dimension mit einer übergeordneten Dimension des Besuchers handelt. Es stellt den ersten HTTP-Referrer für jeden Besucher in der Besucherdimension dar. Jeder Besucher in der Besucherdimension hat nur einen Referrer, aber viele Besucher können denselben Referrer haben. Die Dimension &quot;Referrer&quot;des Besuchers hat daher eine Eins-zu-viele-Beziehung zur Dimension &quot;Besucher&quot;.

Einfache Dimensionen werden durch die folgenden Parameter definiert:

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Beschreibender Name der Dimension, wie er in Data Workbench angezeigt wird. Der Dimensionsname darf keinen Bindestrich (-) enthalten. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur erweiterten Dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen die Beziehung zwischen dem übergeordneten Element und dem Wert des Eingabefelds erstellt werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Oberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false festgelegt. Wenn die Dimension beispielsweise nur als Grundlage für eine Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Datenbasis-Anzeige auszublenden. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Das Feld von Werten, das mit der übergeordneten Dimension (Übergeordnet) in Verbindung steht. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei laden </td> 
   <td colname="col2"> <p>Optional. Eine Datei mit verfügbaren Werten für die Beziehung. Sie verwenden eine Ladedatei, wenn einer der folgenden Punkte zutrifft: </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> Die Werte haben eine bestimmte Sortierreihenfolge, die Sie in der Data Workbench-Anzeige beibehalten möchten. Sie können beispielsweise eine Dimension "Quartal"erstellen, deren Elemente (die Quartale des Jahres) immer in chronologischer Reihenfolge angezeigt werden. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Sie möchten Platzhalter für Werte erstellen, die nicht in den Daten enthalten sind, aber in der Datenbasis angezeigt werden müssen. </li> 
     </ul> </p> <p> Wenn ein Wert gefunden wird, der nicht in der Datei vorhanden ist, wird er beim Anzeigen in Data Workbench am Ende der Werte hinzugefügt. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Folgende Vorgänge stehen zur Verfügung: </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> ERSTE NONBLANK: Der erste nicht-leere Eingabewert wird verwendet, unabhängig davon, ob er vom ersten Protokolleintrag stammt. Ist "Eingabe"ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> ERSTE ZEILE: Der Wert für den ersten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Ist "Eingabe"ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag nicht der Bedingung der Dimension entspricht, wird kein Wert verwendet. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> LETZTES NONBLANK: Der letzte nicht leere Eingabewert wird verwendet, unabhängig davon, ob er vom letzten Protokolleintrag stammt. Ist "Eingabe"ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> LETZTE ZEILE: Der Wert für den letzten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Ist "Eingabe"ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag nicht der Bedingung der Dimension entspricht, wird kein Wert verwendet. </li> 
     </ul> </p> <p> <p>Hinweis:  Ergibt der Vorgang für einen bestimmten Protokolleintrag keinen Wert oder einen leeren Wert, bezieht sich das entsprechende Element der übergeordneten Dimension auf das Element "Keine"der einfachen Dimension. </p> </p> <p> Sie sollten einen Vorgang angeben, um sicherzustellen, dass die Dimension wie gewünscht definiert ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird die Definition einer einfachen Dimension anhand von Ereignisdaten veranschaulicht, die aus dem Website-Traffic und einer Ladedatei erfasst wurden.

Betrachten Sie das Beispiel einer Umfrage zu den Lieblings-Girl-Scout-Cookies der Site-Besucher. Eine Webseite erfasst diese Abstimmung und gibt sie an den Webserver im Namen-Wert-Paar favoritecookie zurück. Es wird nur eine Stimme pro Besucher gezählt, aber Besucher können ihre Meinung ändern und bei Bedarf erneut abstimmen. Dies ist eine Eins-zu-viele-Beziehung: Ein Besucher kann viele Stimmen haben, aber jede Stimme ist nur mit einem Besucher verbunden. Daher ist das übergeordnete Element der Dimension Besucher (nur eine Stimme pro Besucher) und der Vorgang ist LAST ROW (sodass sie ihre Meinung ändern und erneut abstimmen können).

Platzhalter müssen für alle Cookie-Typen vorhanden sein, damit Cookie-Typen, die keine Stimmen erhalten, in der Data Workbench-Anzeige angezeigt werden. Aus diesen Gründen wurde eine Load-Datei definiert, die die Liste der möglicherweise ausgewählten Cookie-Typen enthält. Der Inhalt dieser Datei, der in einer Datei mit dem Namen [!DNL cookietypes.txt]gespeichert ist, sieht wie folgt aus:

Tierschätze

Karamelll-Delikte

Zitronenpfropfkrebse

Buttermuster für Erdnüsse

Shortbretter

Dünne Minzen

Die endgültige Dimension wird wie folgt definiert:

![](assets/cfg_Transformation_Dim_Simple.png)

