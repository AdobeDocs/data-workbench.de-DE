---
description: Eine denormale Dimension weist eine Eins-zu-Eins-Beziehung mit ihrer übergeordneten zählbaren Dimension auf.
title: Denormale Dimensionen
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# Denormale Dimensionen{#denormal-dimensions}

{{eol}}

Eine denormale Dimension weist eine Eins-zu-Eins-Beziehung mit ihrer übergeordneten zählbaren Dimension auf.

Sie würden eine denormale Dimension definieren, wenn die gewünschte Dimension ein eindeutiges Element für jedes Element des übergeordneten Elements enthält. Beispiel: [!DNL EMail Address] ist eine denormale Dimension mit dem übergeordneten Element Besucher. Jeder Besucher verfügt über eine E-Mail-Adresse und jedes Element in der Dimension &quot;E-Mail-Adresse&quot;ist die E-Mail-Adresse eines einzelnen Besuchers. Selbst wenn zwei Besucher dieselbe E-Mail-Adresse haben, sind die Adressen eindeutige Elemente der Dimension &quot;E-Mail-Adresse&quot;.

Sie können denormale Dimensionen in jeder Tabellenvisualisierung, in Detailtabellen oder zum Erstellen von Filtern verwenden. Darüber hinaus können Sie denormale Dimensionen mit der Segmentexportfunktion des Data Workbench-Servers verwenden, um Werte von Feldern zu exportieren (z. B. [!DNL Tracking ID] oder [!DNL EMail Address]), die viele Werte aufweisen. Da alle Segmentdaten, die Sie exportieren möchten, als Dimension im Profil definiert werden müssen, müssen Sie eine denormale Dimension erstellen, die die Rohzeichenfolgen der Felddaten speichert.

>[!NOTE]
>
>Bei Verwendung einer denormalen Dimension in einer Tabelle oder einer anderen Visualisierung, die eine normale Dimension erwartet, wird automatisch eine abgeleitete denormale Dimension erstellt. Die abgeleitete denormale Dimension weist eine Eins-zu-viele-Beziehung mit der übergeordneten Dimension auf.

Informationen zur Visualisierung und Filterung der Detailtabelle finden Sie im Kapitel Analysevisualisierungen im Abschnitt *Data Workbench-Benutzerhandbuch*. Weitere Informationen zum Segmentexport finden Sie im Kapitel &quot;Konfiguration der Benutzeroberfläche und Analysefunktionen&quot;im *Data Workbench-Benutzerhandbuch*.

>[!NOTE]
>
>Denormale Dimensionen können in der Abfragezeit und im Festplattenspeicher sehr teuer sein. Eine denormale Dimension mit übergeordnetem [!DNL Page View]und eine durchschnittliche 50-Byte-Eingabezeichenfolge den Puffern 25 GB Daten in einem typischen, großen Datensatz hinzufügen, was etwa 13 einfachen oder numerischen Seitenansichtsdimensionen oder etwa 125 Dimensionen auf Sitzungsebene entspricht. Fügen Sie einem Datensatz niemals eine denormale Dimension hinzu, ohne die Auswirkungen auf die Leistung sorgfältig zu bewerten.

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
   <td colname="col2"> Deskriptiver Name der Dimension, wie er in Data Workbench angezeigt wird. Der Dimensionsname darf keinen Bindestrich (-) enthalten. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Hinweise zur erweiterten Dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen die Beziehung zwischen dem übergeordneten Element und dem Wert des Eingabefelds erstellt werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgeblendet </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Benutzeroberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false gesetzt. Wenn die Dimension beispielsweise nur als Grundlage einer Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Data Workbench-Anzeige auszublenden. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Der Wert, der mit der übergeordneten Dimension (Übergeordnetes Element) verknüpft ist. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalisierte Elemente </td> 
   <td colname="col2"> Ein Leistungsparameter, der die Anzahl der Dimensionselemente angibt, deren Namen im Systemspeicher gespeichert werden sollen. Wenn Sie diesen Parameter auf einen höheren Wert setzen, verwendet eine denormale Dimension mehr RAM, führt aber zu schnelleren Abfragen. Der Standardwert lautet 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Folgende Vorgänge sind verfügbar: </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> ERSTE NONBLANK: Der erste nicht leere Eingabewert wird verwendet, unabhängig davon, ob er aus dem ersten Protokolleintrag stammt. Wenn <span class="wintitle"> Eingabe</span> ein Vektorfeld ist, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> ERSTE ZEILE: Der Wert für den ersten Protokolleintrag, der sich auf das übergeordnete Dimensionselement bezieht, wird verwendet, auch wenn die Eingabe leer ist. Wenn <span class="wintitle"> Eingabe</span> ein Vektorfeld ist, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag die Bedingung der Dimension nicht erfüllt, wird kein Wert verwendet. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> LETZTES NONBLANK: Der letzte nicht leere Eingabewert wird verwendet, unabhängig davon, ob er aus dem letzten Protokolleintrag stammt. Wenn <span class="wintitle"> Eingabe</span> ein Vektorfeld ist, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> LETZTE ZEILE: Der Wert für den letzten Protokolleintrag im Zusammenhang mit dem übergeordneten Dimensionselement wird verwendet, auch wenn die Eingabe leer ist. Wenn <span class="wintitle"> Eingabe</span> ein Vektorfeld ist, wird die erste Zeile im Vektor für den relevanten Protokolleintrag verwendet. Wenn dieser Wert leer ist oder keine Zahl ist oder der relevante Protokolleintrag die Bedingung der Dimension nicht erfüllt, wird kein Wert verwendet. </li> 
     </ul> </p> <p> <p>Hinweis: Wenn der Vorgang keinen Wert ergibt, wird ein leerer Wert ("") verwendet. </p> </p> <p> Sie sollten einen Vorgang angeben, um sicherzustellen, dass die Dimension wie gewünscht definiert ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Die in diesem Beispiel dargestellte denormale Dimension nimmt alle Daten im Feld x-trackingid als Eingabe und nimmt sie in eine Dimension namens Besucher-ID auf. Für ein von Ihnen erstelltes Besuchersegment können Sie die Daten in die Besucher-ID-Dimension (sowie in jede andere definierte Dimension) exportieren.

![](assets/cfg_Transformation_Dim_Denormal.png)
