---
description: Die LookupRows-Transformation betrachtet andere Protokolleinträge mit derselben Tracking-ID und setzt den Wert des Ausgabefelds auf den Wert eines angegebenen Felds in der Eingabezeile.
title: LookupRows
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 1%

---

# LookupRows{#lookuprows}

Die LookupRows-Transformation betrachtet andere Protokolleinträge mit derselben Tracking-ID und setzt den Wert des Ausgabefelds auf den Wert eines angegebenen Felds in der Eingabezeile.

Da die Umwandlung [!DNL LookupRows] die Suche nach Protokolleinträgen und nicht nach Lookup-Dateien durchführt, ähnelt sie der Umwandlung [!DNL CrossRows]. Siehe [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Für die Umwandlung von [!DNL LookupRows] ist es erforderlich, dass die Daten in der Zeit sortiert und nach der Tracking-ID in den Quelldaten gruppiert werden. Daher funktioniert [!DNL LookupRows] nur, wenn sie in der Datei [!DNL Transformation.cfg] oder in der Datei [!DNL Transformation Dataset Include] definiert ist.

Beachten Sie beim Überprüfen der Beschreibungen der Parameter in der folgenden Tabelle Folgendes:

* Die Ausgabezeile ist die Datenzeile, an der die Umwandlung zu einem bestimmten Zeitpunkt arbeitet.
* Eingabezeilen sind alle anderen Datenzeilen (vor, nach oder einschließlich der Ausgabenzeile), deren Werte des Eingabefelds als Eingaben für die Transformation dienen.

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Beschränkt die Ausgabe der Transformation auf bestimmte Protokolleinträge. Wenn die Bedingung für einen bestimmten Protokolleintrag nicht erfüllt ist, bleibt das Feld im Ausgabezeichenwertparameter unverändert. Die Eingabe kann weiterhin verwendet werden, um andere Protokolleinträge zu beeinflussen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabebedingung </td> 
   <td colname="col2">Akzeptiert die Eingabe für die Umwandlung nur aus bestimmten Eingabezeilen. Wenn die Bedingung <span class="wintitle"> Eingabe</span> für eine bestimmte Eingabezeile nicht erfüllt ist, wird das Eingabefeld aus dieser Zeile ignoriert und wirkt sich nicht auf andere Ausgabezeilen aus. Das Ausgabefeld aus dieser Zeile wird jedoch weiterhin gemäß der angegebenen Bedingung geändert. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe des Eingabezeilenschlüssels </td> 
   <td colname="col2"> Der Name des Felds, das als Schlüssel für die Eingabezeilen verwendet werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe des Eingabezeilenwerts </td> 
   <td colname="col2"> Der Name des Felds in der Eingabezeile, dessen Wert in das Feld im Ausgabezeilenwert-Ausgabeparameter kopiert wird, wenn alle Bedingungen erfüllt sind. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgang </td> 
   <td colname="col2"> <p>Ein Vorgang, der für jede Ausgabezeile auf alle Eingabezeilen angewendet wird, die alle Bedingungen erfüllen, die durch die Eingabeparameter <span class="wintitle"> Eingabe</span> Bedingung und Eingabezeilenschlüssel definiert sind, um eine Ausgabe zu generieren: 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST gibt den Wert des Felds im Eingabeparameter Eingabewert der Eingabezeile aus der ersten übereinstimmenden Eingabezeile in den Daten aus (nicht die erste übereinstimmende Zeile nach der Ausgabezeile). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST gibt den Wert des Felds im Eingabeparameter Eingabewert der Eingabezeile aus der letzten Eingabezeile in den Daten aus (nicht die letzte übereinstimmende Zeile vor der Ausgabezeile). </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe des Ausgabezeilenschlüssels </td> 
   <td colname="col2"> Der Name des Felds, das als Schlüssel für die Ausgabezeile verwendet werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe des Ausgabezeilenwerts </td> 
   <td colname="col2">Der Name des Felds in der Ausgabezeile, dessen Wert aus dem Feld im Eingabewertparameter kopiert wird, wenn alle Bedingungen erfüllt sind. Alle Ausgabezeilen mit derselben x-trackingid und <span class="wintitle"> Ausgabezeilen-Schlüsseleingabe </span>haben denselben Wert <span class="wintitle"> Ausgabezeilenwert Output</span> . </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Die Parameter Eingabe-Zeilenschlüssel, Eingabe-Zeilenwert und Eingabebedingung definieren zusammen die Suchdatei für jede Tracking-ID, während die Parameter Eingabe des Ausgabezeilenschlüssels, Eingabe des Ausgabezeilenwerts und Bedingung steuern, was in der Datei nachgeschlagen wird und welcher Wert in dem von Ausgabe-Zeilenwertausgabe angegebenen Feld gespeichert wird.

Gehen Sie wie folgt vor, um die Funktionsweise der Umwandlung besser zu verstehen:

* Für jede Ausgabezeile, die die Bedingung erfüllt und eine nicht leere Ausgabe-Zeileneingabe enthält:

   * Suchen Sie die erste oder letzte Eingabezeile so, dass

      * die Eingabezeile erfüllt die Eingabebedingung und
      * die x-trackingid der Eingabezeile entspricht der x-trackingid der Ausgabezeile und
      * die Eingabe des Eingabezeilenschlüssels der Eingabezeile entspricht der Eingabe des Ausgabezeilenschlüssels der Ausgabezeile;

* und legen Sie die Ausgabe des Ausgabezeilenwerts der Ausgabenzeile auf die Eingabewerteingabe der Eingabezeile fest.

Überlegungen zu [!DNL LookupRows]

* Leere Schlüsselwerte stimmen nie überein. Selbst wenn es Eingabezeilen mit leeren Schlüsseln und nicht leeren Werten gibt, die mit [!DNL Input Condition] übereinstimmen, erzeugt ein [!DNL Output Row Key Input] von &quot;&quot;immer einen [!DNL Output Row Value Output] von &quot;&quot;.

* Wenn die Werte [!DNL Input Condition] nicht verbieten, kann sich eine Zeile selbst nachschlagen, wenn die Werte [!DNL Input Row Key Input] und [!DNL Output Row Key Input] identisch sind.

Wenn Sie mehrere Schlüsselwerte haben, können Sie diese mithilfe einer [!DNL Format] -Umwandlung kombinieren (siehe [Format](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)), bevor Sie eine [!DNL LookupRows] -Transformation anwenden.

Angenommen, Sie haben eine Website mit einer Registrierungsseite für Haustiere, auf der der Name und die Rasse eingegeben werden, und eine spätere &quot;Spielzeug kaufen&quot;-Seite, auf der nur der Name des Tieres verwendet wird. Sie möchten den Namen des Tieres mit der auf der Registrierungsseite angegebenen Tierrasse verknüpfen können. Dazu können Sie die folgende [!DNL LookupRows]-Umwandlung erstellen:

![](assets/cfg_TransformationType_LookupRows.png)

Analysieren wir dieses Beispiel anhand des vorherigen Entwurfs:

* Für jede Ausgabenzeile, die einen nicht leeren Wert von cs-uri-query(petname) aufweist:

   * Suchen Sie die letzte Eingabezeile so, dass

      * die Eingabezeile enthält einen nicht leeren Wert von cs-uri-query(petbreed) und
      * die x-trackingid der Eingabezeile entspricht der x-trackingid der Ausgabezeile und
      * der Wert von cs-uri-query(petname) der Eingabezeile entspricht dem Wert von cs-uri-query(petname) der Ausgabezeile;

* und legen Sie den Wert von x-pet-breed der Ausgabenzeile auf den Wert von cs-uri-query(petbreed) der Eingabezeile fest.

Die Umwandlung von [!DNL LookupRows] verwendet den Haustiernamen (den Schlüssel), um sicherzustellen, dass die Heimtierrasse sowohl mit der Heimtierregistrierung als auch mit den Seiten zum Kauf von Spielzeug verknüpft ist, sodass Sie die für jede Tierrasse gekauften Spielzeuge analysieren können, selbst für Besucher mit mehreren Haustieren.
