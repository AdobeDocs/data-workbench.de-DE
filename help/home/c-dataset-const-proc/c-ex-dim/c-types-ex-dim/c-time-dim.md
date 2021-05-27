---
description: Mit einer Zeitdimension können Sie einen Satz periodischer oder absoluter lokaler Zeitdimensionen erstellen (z. B. Tag, Wochentag, Stunde des Tages, Reservierungszeit usw.), die auf einem beliebigen Zeitstempelfeld basieren, das Sie für den Parameter Eingabezeit (Epoche 1970) angeben.
title: Zeitdimensionen
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
exl-id: f9534b24-3a16-4220-bac2-bc541e121005
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 11%

---

# Zeitdimensionen{#time-dimensions}

Mit einer Zeitdimension können Sie einen Satz periodischer oder absoluter lokaler Zeitdimensionen erstellen (z. B. Tag, Wochentag, Stunde des Tages, Reservierungszeit usw.), die auf einem beliebigen Zeitstempelfeld basieren, das Sie für den Parameter Eingabezeit (Epoche 1970) angeben.

Beim Definieren der Zeitdimensionen können Sie auch einen anderen Tag als Montag als ersten Tag der Woche festlegen, indem Sie den Parameter für den Anfangstag der Woche entsprechend einstellen. Sie können mehrere Zeitdimensionen in Ihrem Datensatz definieren, solange die Dimensionen unterschiedliche Namen haben.

Zeitdimensionen werden durch die folgenden Parameter definiert:

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
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
   <td colname="col1"> Dimensionen </td> 
   <td colname="col2"> <p>Sie können Dimensionsnamen für einen der folgenden Zeiträume angeben: </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> Tag </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> Wochentag </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> Stunde </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> Stunde des Tages </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> Monat </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> Woche </li> 
     </ul> </p> <p> Die Namen, die Sie hier eingeben, sind die Namen, die in den Dimensionsmenüs und in Visualisierungen in Data Workbench angezeigt werden. Wenn Sie den Namen einer Zeitdimension leer lassen, wird die Dimension nicht im Datensatz erstellt. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Benutzeroberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false gesetzt. Wenn die Dimension beispielsweise nur als Grundlage einer Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Data Workbench-Anzeige auszublenden. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabezeit (Epoche 1970) </td> 
   <td colname="col2"> <p>Der Name des Zeitstempelfelds, das als Eingabe verwendet werden soll. </p> <p> <p>Hinweis:  Die Werte des Felds müssen die Anzahl der Sekunden seit dem 1. Januar 1970 um 00:00:01 Uhr darstellen. Wenn die Eingabezeit keine gültige Zeit ist (1970 bis 2037), schlägt der Transformationsprozess fehl und der Data Workbench-Server erzeugt einen Fehler. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. Bei Webdaten ist das übergeordnete Element Sitzung. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Wochentag </td> 
   <td colname="col2"> <p>Der Tag, der als erster Tag einer Woche verwendet werden soll. </p> <p> Dieser Parameter wirkt sich auf die Dimension Woche , die Dimension Wochentag und alle in Wochen definierten Berichtszeitdimensionen aus. </p> </td> 
   <td colname="col3"> Mon </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird basierend auf dem benutzerdefinierten Eingabefeld x-time-1970 ein Satz von Zeitdimensionen erstellt. Die Zeitdimensionen werden als &quot;Sitzungszeit&quot;bezeichnet. Da das übergeordnete Element jeder Dimension die Dimension Sitzung ist, entspricht jedes Element der Zeitdimensionen dem Zeitpunkt, zu dem eine Sitzung begonnen hat. Der Parameter Wochenstart gibt an, dass jede Woche der Dimension Woche am Montag beginnt.

![](assets/cfg_Transformation_Dim_TimeDim.png)
