---
description: Eine denormale Dimension hat eine Eins-zu-Eins-Beziehung zu ihrer übergeordneten zählbaren Dimension.
title: Denormale Dimensionen
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# Denormale Dimensionen{#denormal-dimensions}

Eine denormale Dimension hat eine Eins-zu-Eins-Beziehung zu ihrer übergeordneten zählbaren Dimension.

Sie definieren eine denormale Dimension, wenn die gewünschte Dimension ein eindeutiges Element für jedes Element des übergeordneten Elements enthält. [!DNL EMail Address] ist beispielsweise eine denormale Dimension mit einer übergeordneten Dimension von Besucher. Jeder Besucher hat eine E-Mail-Adresse, und jedes Element in der Dimension &quot;E-Mail-Adresse&quot;ist die E-Mail-Adresse eines einzelnen Besuchers. Auch wenn zwei Besucher dieselbe E-Mail-Adresse haben, sind die Adressen verschiedene Elemente der Dimension &quot;E-Mail-Adresse&quot;.

Sie können denormale Dimensionen in jeder Tabellenvisualisierung, in Detailtabellen oder zum Erstellen von Filtern verwenden. Darüber hinaus können Sie denormale Dimensionen mit der Segmentexportfunktion des Data Workbench-Servers verwenden, um Werte von Feldern (z. B. [!DNL Tracking ID] oder [!DNL EMail Address]) mit vielen Werten zu exportieren. Da alle Segmentdaten, die Sie exportieren möchten, als Dimension innerhalb des Profils definiert werden müssen, müssen Sie eine denormale Dimension erstellen, die die Rohzeichenfolgen der Felddaten speichert.

>[!NOTE]
>
>Bei Verwendung einer denormalen Dimension in einer Tabelle oder einer anderen Visualisierung, die eine normale Dimension erwartet, wird automatisch eine abgeleitete denormale Dimension erstellt. Die abgeleitete denormale Dimension hat eine Eins-zu-viele-Beziehung zur übergeordneten Dimension.

Informationen zur Visualisierung der Detailtabelle und zu den Filtern finden Sie im Kapitel &quot;Visualisierungen für Analysen&quot;im *Data Workbench Benutzerhandbuch*. Informationen zum Segmentexport finden Sie im Kapitel Configuring Interface and Analyse Features im *Data Workbench Benutzerhandbuch*.

>[!NOTE]
>
>Denormale Abmessungen können in Abfrage und Speicherplatz sehr teuer sein. Eine denormale Dimension mit dem übergeordneten Element [!DNL Page View]und einer 50-Byte-durchschnittlichen Eingabestring könnten den Puffern in einem typischen, großen Datensatz 25 GB Daten hinzufügen, was etwa 13 Dimensionen der Ansicht einfacher oder numerischer Seiten oder etwa 125 Dimensionen auf Sitzungsebene entspricht. Fügen Sie einem Datensatz nie eine denormale Dimension hinzu, ohne dass die Leistungsauswirkungen sorgfältig geprüft werden.

Denormale Dimensionen werden durch die folgenden Parameter definiert:

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
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
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Wert, der sich auf die übergeordnete Dimension bezieht (Übergeordnet). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalisierte Elemente </td> 
   <td colname="col2"> Ein Leistungsoptimierungsparameter, der die Anzahl der Dimensionselemente angibt, deren Namen im Systemspeicher gespeichert werden sollen. Wenn Sie diesen Parameter auf einen höheren Wert setzen, verwendet eine denormale Dimension mehr RAM, führt aber zu schnelleren Abfragen. Der Standardwert lautet 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Folgende Vorgänge stehen zur Verfügung: </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> ERSTE NONBLANK: Der erste nicht-leere Eingabewert wird verwendet, unabhängig davon, ob er vom ersten Protokolleintrag stammt. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> ERSTE ZEILE: Der Wert für den ersten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag nicht der Bedingung der Dimension entspricht, wird kein Wert verwendet. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> LETZTES NONBLANK: Der letzte nicht leere Eingabewert wird verwendet, unabhängig davon, ob er vom letzten Protokolleintrag stammt. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> LETZTE ZEILE: Der Wert für den letzten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Ist <span class="wintitle"> Input</span> ein Vektorfeld, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag nicht der Bedingung der Dimension entspricht, wird kein Wert verwendet. </li> 
     </ul> </p> <p> <p>Hinweis:  Wenn der Vorgang keinen Wert ergibt, wird ein leerer Wert ("") verwendet. </p> </p> <p> Sie sollten einen Vorgang angeben, um sicherzustellen, dass die Dimension wie gewünscht definiert ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Die in diesem Beispiel dargestellte denormale Dimension nimmt alle Daten im Feld x-trackingid als Eingabe und bezieht sie in eine Dimension namens Besucher-ID ein. Für ein Segment von Besuchern, die Sie erstellt haben, können Sie die Daten in die Besucher-ID-Dimension (sowie in eine andere definierte Dimension) exportieren.

![](assets/cfg_Transformation_Dim_Denormal.png)
