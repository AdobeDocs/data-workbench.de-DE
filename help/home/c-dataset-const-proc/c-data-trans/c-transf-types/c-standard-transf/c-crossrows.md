---
description: Wie andere Transformationen wird auch die CrossRows-Transformation auf die Datenzeilen (Protokolleinträge) in Ihren Protokollquellen angewendet.
title: CrossRows
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# CrossRows{#crossrows}

Wie andere Transformationen wird auch die CrossRows-Transformation auf die Datenzeilen (Protokolleinträge) in Ihren Protokollquellen angewendet.

Für jede Datenzeile nimmt die Transformation den Wert des angegebenen Eingabefelds, führt eine Reihe von Verarbeitungsschritten aus und zeichnet das Ergebnis im angegebenen Ausgabefeld auf. Wenn die [!DNL CrossRows]-Konvertierung jedoch für eine Datenzeile funktioniert (diese Zeile wird als Ausgabezeile bezeichnet), berücksichtigt sie diese Zeile sowie eine oder mehrere andere Datenzeilen (diese Zeilen werden als Eingabezeilen bezeichnet), die mit derselben Tracking-ID verknüpft sind. Daher basiert der Wert des Ausgabefelds für jede Ausgabezeile für eine bestimmte Tracking-ID auf den Werten des Eingabefelds für eine oder mehrere Eingabelzeilen.

Die Transformation bietet mehrere Bedingungen und Einschränkungen, mit denen Sie die Eingabezeilen für die Transformation einschränken können. Sie können diese Beschränkungen in Bezug auf die Bedingungen des Data Workbench-Servers (siehe [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), einen Bereich von Eingabezeilen relativ zur Ausgabezeile oder einen Zeitbereich im Verhältnis zur Zeit der Ausgabezeile angeben. Für die Eingabereilen, die die Bedingungen und Einschränkungen der Transformation erfüllen, können Sie einen Vorgang (z. B. SUM) anwenden, der den Wert des Ausgabefelds bestimmt.

>[!NOTE]
>
>Für die Umwandlung von [!DNL CrossRows] ist es erforderlich, dass die Daten in der Zeit angeordnet und nach der Tracking-ID in den Quelldaten gruppiert werden. [!DNL CrossRows] funktioniert daher nur, wenn sie in der Datei [!DNL Transformation.cfg] oder in einer Datei [!DNL Transformation Dataset Include] definiert ist.

Beachten Sie beim Lesen der Beschreibungen der Parameter in der folgenden Tabelle Folgendes:

* Die Ausgabezeile ist die Datenzeile, an der die Transformation zu einem bestimmten Zeitpunkt arbeitet.
* Eingabezeilen sind alle anderen Datenzeilen (vor, nach oder einschließlich der Ausgabezeile), deren Werte des Eingabefelds als Eingabe für die Transformation dienen. Die Eingabezeilen unterliegen den Parametern &quot;Eingabebedingung&quot;, &quot;Schlüssel&quot;, &quot;Zeilenbeginn&quot;, &quot;Zeilenende&quot;, &quot;Zeitbeginn&quot;und &quot;Zeitende&quot;.

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
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
   <td colname="col2"> Begrenzt die Ausgabe der Transformation auf bestimmte Protokolleinträge. Wenn die Bedingung für einen bestimmten Protokolleintrag nicht erfüllt ist, bleibt das Feld im Parameter "Ausgabe"unverändert. Die Eingabe kann weiterhin verwendet werden, um andere Protokolleinträge zu beeinflussen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Name des Felds in der als Eingabe zu verwendenden Eingabezeile. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabebedingung </td> 
   <td colname="col2"> Akzeptiert Eingaben für die Transformation nur aus bestimmten Eingabezeilen. Wenn die Eingabebedingung für eine bestimmte Eingabezeile nicht erfüllt ist, wird das Eingabefeld aus dieser Zeile ignoriert und wirkt sich nicht auf andere Ausgabezeilen aus. Das Ausgabefeld aus dieser Zeile wird jedoch weiterhin gemäß der angegebenen Bedingung geändert. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schlüssel </td> 
   <td colname="col2"> <p>Optional. Der Name des Felds, das als Schlüssel verwendet werden soll. </p> <p> Wenn ein Schlüssel angegeben ist, sind die Eingabelzeilen für eine bestimmte Ausgabezeile auf den zusammenhängenden Zeilenblock mit demselben Schlüsselwert wie die Ausgabezeile beschränkt. Diese Einschränkung gilt zusätzlich zu allen anderen Einschränkungen, die durch andere Parameter der <span class="wintitle">-Transformation auf den Eingabezeilen platziert werden.</span> </p> <p> Wenn Sie z. B. mit Webdaten arbeiten und den Schlüssel für das Feld x-session-key (der für jede Sitzung einen eindeutigen Wert hat) festlegen, sind die Eingabelzeilen für die Transformation auf die Zeilen beschränkt, die denselben X-Session-Key-Wert wie die Ausgabezeile haben. Daher erwägen Sie nur die Eingabezeilen, die Seitenzeilen darstellen, die während derselben Sitzung wie die Ausgabezeile auftreten. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Ein Vorgang, der für jede Ausgabezeile auf alle Eingabezeilen angewendet wird, die alle Bedingungen erfüllen, die durch die Parameter "Eingabebedingung", "Schlüssel", "Zeilenbeginn", "Zeilenende", "Zeitbeginn"und "Zeitende"definiert werden, um eine Ausgabe zu erzeugen: 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL nimmt alle Werte des Eingabefelds aus den Eingabezeilen und gibt sie als Vektor aus. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM interpretiert die Werte des Eingabefelds aus den Eingabezeilen als Zahlen und Summen. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> ERSTE ZEILE gibt den Wert des Eingabefelds aus der ersten Eingabezeile aus. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST-ZEILE gibt den Wert des Eingabefelds aus der letzten Eingabezeile aus. </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des Ausgabefelds. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeilenbeginn/Zeilenende </td> 
   <td colname="col2"> <p>Optional. Gibt einen Bereich von Eingabezeilen relativ zur Ausgabezeile an. Bei einem Zeilenanfang-Wert von "0"werden beispielsweise alle Zeilen vor der Ausgabezeile ausgeschlossen. Bei einem Zeilenanfang-Wert von "1"wird auch die Ausgabezeile ausgeschlossen. Häufige Bereiche sind: 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> 0 beginnen: Diese Zeile und alle nachfolgenden Zeilen. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Beginn 1: Alle nachfolgenden Zeilen. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Ende 0: Diese und alle vorherigen Zeilen. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Ende -1: Alle vorherigen Zeilen. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Beginnen -1, Ende -1: Die vorherige Zeile. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Beginn 1, Ende 1: Die nächste Zeile. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Alle Zeilen </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitraum Anfang/Ende </td> 
   <td colname="col2"> <p>Optional. Gibt einen Zeitbereich im Verhältnis zur Zeit der Ausgabezeile an. Ein Zeitende von 30 Minuten umfasst z. B. alle Zeilen, die innerhalb von 30 Minuten nach der Ausgabezeile stattfinden. Ein Zeitbeginn von -30 Minuten umfasst alle Zeilen, die innerhalb von 30 Minuten vor der Ausgabeliste stattfinden. </p> <p> Verfügbare Zeiteinheiten sind Tage, Wochen, Stunden, Minuten, ms (Millisekunden), Zecken (100 Nanosekunden) und ns (Nanosekunden). </p> </td> 
   <td colname="col3"> Alle Zeiten </td> 
  </tr> 
 </tbody> 
</table>

Die [!DNL CrossRows]-Transformation in diesem Beispiel wird auf Zeilen mit Webdaten angewendet, um für jede Ansicht den Zeitpunkt der nächsten Ansicht zu ermitteln. Da wir wissen, dass [!DNL CrossRows] nur während der Konvertierungsphase des Datensatzerstellungsprozesses angewendet wird, werden die Datenzeilen nach Besucher (jeder Besucher hat eine eindeutige Tracking-ID) und Uhrzeit sortiert.

Das Eingabefeld x-timestamp gilt nur für die Eingabelzeilen, in denen das Feld x-is-page-Ansicht ausgefüllt ist (die Datenzeile steht für eine Ansicht der Seite). Das Feld x-session-key (das für jede Sitzung einen eindeutigen Wert enthält) wird für den Parameter key angegeben. Daher sind die Eingabezeilen (Protokolleinträge) für die Transformation auf den zusammenhängenden Zeilenblock beschränkt, der denselben Wert wie die Ausgabezeile hat. Damit eine Eingabezeile für die Konvertierung berücksichtigt werden kann, muss sie eine Seitenzeile darstellen, die während der gleichen Ansicht wie die Seite in der Ausgabezeile auftritt. Der erste Zeilenvorgang nimmt den Wert des Ausgabefelds aus der ersten Eingabezeile, die die Bedingung [!DNL Input] erfüllt und denselben X-Session-Key-Wert wie die Ausgabezeile hat.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] wird in einem Zeitraum ausgeführt, der proportional zur Größe der Eingaben und der Größe der Ausgaben ist. Das bedeutet, dass für die Vorgänge SUM, FIRST ROW und LAST ROW diese nicht weniger effizient sind als andere Transformationen. Für ALLE ist die Situation komplexer, da es möglich ist, [!DNL CrossRows] so zu konfigurieren, dass für jede Datenzeile (Protokolleintrag) eine Datenmenge ausgegeben wird, die proportional zur Gesamtanzahl der Zeilen (Protokolleinträge) für eine bestimmte Tracking-ID ist.
