---
description: Die LookupRows-Transformation betrachtet andere Protokolleinträge mit derselben Tracking-ID und stellt den Wert des Ausgabefelds auf den Wert eines angegebenen Felds in der Eingabelzeile ein.
solution: Analytics
title: LookupRows
topic: Data workbench
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# LookupRows{#lookuprows}

Die LookupRows-Transformation betrachtet andere Protokolleinträge mit derselben Tracking-ID und stellt den Wert des Ausgabefelds auf den Wert eines angegebenen Felds in der Eingabelzeile ein.

Da die [!DNL LookupRows] Transformation die Suche nach Protokolleinträgen und nicht nach Lookup-Dateien durchführt, ist sie der [!DNL CrossRows] Transformation sehr ähnlich. Siehe [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Damit die [!DNL LookupRows] Transformation funktioniert, müssen die Daten in der Zeit angeordnet und nach der Tracking-ID in den Quelldaten gruppiert werden. Daher [!DNL LookupRows] funktioniert nur, wenn sie in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definiert ist.

Beachten Sie beim Lesen der Beschreibungen der Parameter in der folgenden Tabelle Folgendes:

* Die Ausgabezeile ist die Datenzeile, an der die Transformation zu einem bestimmten Zeitpunkt arbeitet.
* Eingabezeilen sind alle anderen Datenzeilen (vor, nach oder einschließlich der Ausgabezeile), deren Werte des Eingabefelds als Eingabe für die Transformation dienen.

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col2"> Begrenzt die Ausgabe der Transformation auf bestimmte Protokolleinträge. Wenn die Bedingung für einen bestimmten Protokolleintrag nicht erfüllt ist, bleibt das Feld im Ausgabezeichenwertausgabeparameter unverändert. Die Eingabe kann weiterhin verwendet werden, um andere Protokolleinträge zu beeinflussen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabebedingung </td> 
   <td colname="col2">Akzeptiert Eingaben für die Transformation nur aus bestimmten Eingabezeilen. Wenn die <span class="wintitle"> Eingabebedingung</span> für eine bestimmte Eingabezeile nicht erfüllt ist, wird das Eingabefeld aus dieser Zeile ignoriert und wirkt sich nicht auf andere Ausgabezeilen aus. Das Ausgabefeld aus dieser Zeile wird jedoch weiterhin gemäß der angegebenen Bedingung geändert. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe des Zeilenschlüssels </td> 
   <td colname="col2"> Der Name des Felds, das als Schlüssel für die Eingabezeilen verwendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe des Zeilenwertes </td> 
   <td colname="col2"> Der Name des Felds in der Eingabezeile, dessen Wert in das Feld im Ausgabezeichenwert-Ausgabeparameter kopiert wird, wenn alle Bedingungen erfüllt sind. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Ein Vorgang, der für jede Ausgabezeile auf alle Eingabezeilen angewendet wird, die alle Bedingungen erfüllen, die durch die Eingabebedingung <span class="wintitle"> und die Eingabezeileneingabeparameter</span> definiert sind, um eine Ausgabe zu erstellen: 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> ERST gibt den Wert des Felds im Eingabezeilenwert-Eingabeparameter aus der ersten übereinstimmenden Eingabezeile in den Daten aus (nicht die erste übereinstimmende Zeile nach der Ausgabezeile). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST gibt den Wert des Felds im Eingabezeileneingabewert-Parameter aus der letzten Eingabezeile in den Daten aus (nicht die letzte übereinstimmende Zeile vor der Ausgabezeile). </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe des Ausgabezeilenschlüssels </td> 
   <td colname="col2"> Der Name des Felds, das als Schlüssel für die Ausgabezeile verwendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe des Zeilenwertes </td> 
   <td colname="col2">Der Name des Felds in der Ausgabezeile, dessen Wert aus dem Feld im Eingabewert des Eingabeparameters kopiert wird, wenn alle Bedingungen erfüllt sind. Alle Ausgabezeilen mit demselben x-trackingid- und <span class="wintitle"> Ausgabe-Zeilenschlüssel- </span>Wert haben denselben <span class="wintitle"> Ausgabezeilenwert</span> . </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Die Parameter &quot;Eingabe des Zeilenschlüssels&quot;, &quot;Eingabe des Zeilenwertes&quot;und &quot;Eingabebedingung&quot;definieren zusammen die Abfragedatei für jede Verfolgungs-ID, während die Parameter &quot;Eingabe des Zeileneintrags&quot;, &quot;Eingabe des Ausgabezeilenwerts&quot;und &quot;Bedingung&quot;steuern, was in der Datei nachgeschlagen wird und welcher Wert in dem Feld gespeichert wird, das in der Ausgabe des Ausgabezeilenwerts angegeben ist.

Um die Funktionsweise der Transformation besser zu verstehen, beachten Sie die folgende Übersicht:

* Für jede Ausgabezeile, die die Bedingung erfüllt und einen nicht leeren Eingabe für die Ausgabezeichenfolge enthält:

   * Suchen Sie die erste oder letzte Eingabezeile, sodass

      * die Eingabezeile die Eingabebedingung erfüllt und
      * die x-trackingid der Eingabezeile gleich der x-trackingid der Ausgabezeile und
      * die Eingabe des Eingangszeilenschlüssels der Eingabezeile entspricht der Eingabe des Ausgabezeilenschlüssels in der Ausgabezeile;

* und legen Sie die Ausgabe des Ausgabezeilenwerts der Ausgabezeile auf die Eingabe des Eingabezeilenwerts der Eingabezeile fest.

Überlegungen zu [!DNL LookupRows]

* Leere Schlüsselwerte stimmen nie überein. Auch wenn es Eingabezeilen mit leeren Schlüsseln und nicht leeren Werten gibt, die mit dem Wert übereinstimmen [!DNL Input Condition], erzeugt ein [!DNL Output Row Key Input] von &quot;&quot;immer den [!DNL Output Row Value Output] Wert &quot;&quot;.

* Wenn eine Zeile nicht vom [!DNL Input Condition]Operator verboten ist, kann sie selbst nachschlagen, wenn ihre [!DNL Input Row Key Input] und [!DNL Output Row Key Input] Werte identisch sind.

Wenn Sie mehrere Schlüsselwerte haben, können Sie diese mithilfe einer [!DNL Format] Transformation (siehe [Format](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) kombinieren, bevor Sie eine [!DNL LookupRows] Transformation anwenden.

Angenommen, Sie haben eine Website mit einer Registrierungsseite für Haustiere, auf der der Name und die Rasse eingegeben werden, und eine spätere Seite &quot;Spielzeug kaufen&quot;, auf der nur der Name des Tieres verwendet wird. Sie möchten den Namen des Tieres mit der auf der Registrierungsseite eingetragenen Tierrasse verknüpfen können. Dazu können Sie die folgende [!DNL LookupRows] Transformation erstellen:

![](assets/cfg_TransformationType_LookupRows.png)

Analysieren wir dieses Beispiel anhand der vorherigen Gliederung:

* Für jede Ausgabezeile mit einem nicht leeren Wert von cs-uri-query(petname):

   * Suchen Sie die letzte Eingabezeile, sodass

      * die Eingabezeile enthält einen nicht leeren Wert von cs-uri-query(petbreed) und
      * die x-trackingid der Eingabezeile gleich der x-trackingid der Ausgabezeile und
      * der Wert von cs-uri-query(petname) der Eingabezeile entspricht dem Wert von cs-uri-query(petname) der Ausgabezeile;

* und legen Sie den Wert der X-Tier-Rasse der Ausgabezeile auf den Wert von cs-uri-query(petbreed) der Eingabezeile fest.

Die [!DNL LookupRows] Transformation verwendet den Namen des Tieres (den Schlüssel), um sicherzustellen, dass die Tierrasse sowohl mit der Registrierung des Tieres als auch mit dem Kauf von Spielzeugseiten verknüpft ist, damit Sie die für jede Tierrasse gekauften Spielzeuge analysieren können, auch für Besucher mit mehreren Haustieren.
