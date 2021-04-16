---
description: Eine numerische Dimension besteht aus geordneten numerischen Elementen und hat eine Eins-zu-viele-Beziehung zu ihrer übergeordneten zählbaren Dimension.
title: Numerische Dimensionen
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 2%

---

# Numerische Dimensionen{#numeric-dimensions}

Eine numerische Dimension besteht aus geordneten numerischen Elementen und hat eine Eins-zu-viele-Beziehung zu ihrer übergeordneten zählbaren Dimension.

Sie können sich eine numerische Dimension als Darstellung der numerischen Eigenschaften der Elemente der übergeordneten Dimension vorstellen. Wenn Sie z. B. mit Webdaten arbeiten, können Sie die numerische Dimension Sitzungsumsatz definieren, die einen Umsatz in Dollar für jede Sitzung in der Sitzungsdimension definiert. Jede Sitzung hat einen einzigen Umsatzbetrag, aber mehrere Sitzungen können denselben Umsatzbetrag haben. Daher hat die Dimension &quot;Sitzungsumsatz&quot;eine Eins-zu-viele-Beziehung zur Dimension &quot;Sitzung&quot;.

Numerische Dimensionen werden häufig verwendet, um Metriken zu definieren, die Werte summieren, Vorkommen einer Bedingung zählen oder einen Mindest- oder Höchstwert ermitteln. Beispielsweise könnte eine Metrik namens &quot;Umsatz&quot;mithilfe der Dimension &quot;Sitzungsumsatz&quot;definiert werden: sum(Session_Revenue, Session). Auf diese Weise definiert, gibt die Umsatzmetrik den Gesamtumsatz für die ausgewählten Sitzungen an.

Numerische Dimensionen können keine übergeordneten Elemente anderer Dimensionen sein.

Numerische Dimensionen werden durch die folgenden Parameter definiert:

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col2"> Beschreibender Name der Dimension, wie er in Data Workbench angezeigt wird. Der Dimensionsname darf keinen Bindestrich (-) enthalten. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clip-Werte </td> 
   <td colname="col2"> Wahr oder falsch. Gibt an, ob der Eingabewert (nach Operation) zwischen den Werten Min. und Max abgeschnitten werden soll. Wenn "Clip-Werte"true ist, wird der Wert auf diesen Bereich gekürzt. Wenn "Clip-Werte"den Wert "false"hat, wird kein Wert für das Element der übergeordneten Dimension zurückgegeben. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur erweiterten Dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen das Eingabefeld zur Erstellung der numerischen Dimension beiträgt. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Feste Größe </td> 
   <td colname="col2"> Wahr oder falsch. Steuert die Anzahl der Elemente in einer Dimension (Kardinalität). Wenn "true", werden alle Elemente von "Min."bis "Max."in die Dimension einbezogen. Bei "false"wächst die Größe der Dimension, wenn Werte hinzugefügt werden. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Oberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false festgelegt. Wenn die Dimension beispielsweise nur als Grundlage für eine Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Datenbasis-Anzeige auszublenden. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> <p>Der Wert, der mit dem angegebenen Vorgang oder dem Eingabewert verwendet wird, für den Sie Vorfälle zählen möchten. </p> <p> Wenn dieses Feld ein Vektor von Zeichenfolgen ist, erfolgt die Auswertung für jedes Element im Vektor. Ein Vektor mit der Länge 3 und ein Vorgang des COUNT addieren zum Beispiel 3 zur Zählung. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> Untergrenze für das Endergebnis der Dimension. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max. </td> 
   <td colname="col2"> Obergrenze für das Endergebnis der Dimension. </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Versatz </td> 
   <td colname="col2"> Siehe Skalieren in dieser Tabelle. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Folgende Vorgänge stehen zur Verfügung: </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> COUNT: Es wird die Gesamtanzahl der nicht leeren Werte im Feld <span class="wintitle"> Eingabe</span> für alle Protokolleinträge verwendet, die die Bedingung der Dimension erfüllen. Wenn das Feld <span class="wintitle"> Eingabe</span> ein Vektor ist, wird die Gesamtzahl der nicht leeren Werte in jedem Protokolleintrag gezählt. </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> ERSTE NONBLANK: Der erste nicht-leere Eingabewert wird verwendet, unabhängig davon, ob er vom ersten Protokolleintrag stammt. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn der Wert keine Zahl ist, wird kein Wert verwendet. </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> ERSTE ZEILE: Der Wert für den ersten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag nicht der Bedingung der Dimension entspricht, wird kein Wert verwendet. </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> LETZTES NONBLANK: Der letzte nicht leere Eingabewert wird verwendet, unabhängig davon, ob er vom letzten Protokolleintrag stammt. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn der Wert keine Zahl ist, wird kein Wert verwendet. </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> LETZTE ZEILE: Der Wert für den letzten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag nicht der Bedingung der Dimension entspricht, wird kein Wert verwendet. </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SUM: Es wird die Summe aller numerischen Werte im Feld <span class="wintitle"> Eingabe</span> für alle Protokolleinträge verwendet, die die Bedingung der Dimension erfüllen. Wenn keine derartigen Protokolleinträge oder keine numerischen Werte gefunden wurden, wird der numerische Wert 0 verwendet. </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN oder MAX: Es wird der minimale oder maximale numerische Wert verwendet, der im Feld <span class="wintitle"> Eingabe</span> für alle Protokolleinträge gefunden wird, die die Bedingung der Dimension erfüllen. Wenn es keine derartigen Protokolleinträge oder keine numerischen Werte gibt, wird kein Wert verwendet. </li> 
     </ul> </p> <p> <p>Hinweis:  Sie sollten einen Vorgang angeben, um sicherzustellen, dass die Dimension wie gewünscht definiert ist. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skalierung </td> 
   <td colname="col2"> <p>Um den Ordinalwert der Dimension zu erhalten, wird das Ergebnis des Vorgangs wie folgt transformiert: </p> <p> (Eingabe skalieren *) + Offset </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Wenn [!DNL Operation] keinen Wert ergibt oder [!DNL Clip Values] den Wert false hat und der Wert nicht zwischen [!DNL Min] und [!DNL Max] liegt, ist kein Element der numerischen Dimension mit dem Element der übergeordneten Dimension verknüpft.

In diesem Beispiel wird die Definition einer numerischen Dimension anhand von Ereignis-Daten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Diese numerische Dimension mit dem Namen &quot;Anzeigenzähler&quot;zählt, wie oft der Besucher während einer bestimmten Ansicht eine Werbung sieht. Es wird davon ausgegangen, dass alle Werbemittel vom Webserver mit ad= als Teil der cs-uri-Abfrage angefordert werden. In diesem Beispiel ist die Anzahl der Male (COUNT), die dem Besucher eine Werbung präsentiert wird, der Wert des Interesses und nicht der tatsächliche Wert im Feld.

![](assets/cfg_Transformation_Dim_Numeric.png)
