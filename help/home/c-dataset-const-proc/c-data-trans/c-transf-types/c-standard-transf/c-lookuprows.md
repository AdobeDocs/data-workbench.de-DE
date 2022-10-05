---
description: Die LookupRows-Transformation betrachtet andere Protokolleinträge mit derselben Tracking-ID und setzt den Wert des Ausgabefelds auf den Wert eines angegebenen Felds in der Eingabezeile.
title: LookupRows
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 1%

---

# LookupRows{#lookuprows}

{{eol}}

Die LookupRows-Transformation betrachtet andere Protokolleinträge mit derselben Tracking-ID und setzt den Wert des Ausgabefelds auf den Wert eines angegebenen Felds in der Eingabezeile.

Da die [!DNL LookupRows] -Transformation führt die Suche nach Protokolleinträgen durch und sucht keine Lookup-Dateien. Sie ähnelt sehr dem [!DNL CrossRows] Umwandlung. Siehe [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Um zu arbeiten, wird die [!DNL LookupRows] Für die Transformation müssen die Daten in der Zeit geordnet und nach der Tracking-ID in den Quelldaten gruppiert werden. Daher [!DNL LookupRows] funktioniert nur, wenn im [!DNL Transformation.cfg] oder in einer [!DNL Transformation Dataset Include] -Datei.

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
   <td colname="col2">Akzeptiert die Eingabe für die Umwandlung nur aus bestimmten Eingabezeilen. Wenn die Variable <span class="wintitle"> Eingabe</span> Die Bedingung ist für eine bestimmte Eingabezeile nicht erfüllt, das Eingabefeld aus dieser Zeile wird ignoriert und hat keine Auswirkungen auf andere Ausgabezeilen. Das Ausgabefeld aus dieser Zeile wird jedoch weiterhin gemäß der angegebenen Bedingung geändert. </td> 
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
   <td colname="col2"> <p>Ein Vorgang, der für jede Ausgabezeile auf alle Eingabezeilen angewendet wird, die alle durch die <span class="wintitle"> Eingabe</span> Eingabeparameter für Bedingung- und Eingabezeilen zur Erstellung einer Ausgabe: 
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
   <td colname="col2">Der Name des Felds in der Ausgabezeile, dessen Wert aus dem Feld im Eingabewertparameter kopiert wird, wenn alle Bedingungen erfüllt sind. Alle Ausgabezeilen mit derselben x-trackingid und <span class="wintitle"> Eingabe des Ausgabezeilenschlüssels </span>-Werte haben denselben <span class="wintitle"> Ausgabe des Ausgabezeilenwerts</span> -Wert. </td> 
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

* Leere Schlüsselwerte stimmen nie überein. Selbst wenn Eingabezeilen mit leeren Schlüsseln und nicht leeren Werten vorhanden sind, die mit dem [!DNL Input Condition], und [!DNL Output Row Key Input] von &quot;&quot;erzeugt immer eine [!DNL Output Row Value Output] von &quot;&quot;.

* Wenn nicht durch die Variable [!DNL Input Condition], kann eine Zeile selbst nachschlagen, wenn sie [!DNL Input Row Key Input] und [!DNL Output Row Key Input] -Werte sind identisch.

Wenn mehrere Schlüsselwerte vorhanden sind, können Sie sie mithilfe eines [!DNL Format] Transformation (siehe [Format](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) vor dem Anwenden einer [!DNL LookupRows] Umwandlung.

Angenommen, Sie haben eine Website mit einer Registrierungsseite für Haustiere, auf der der Name und die Rasse eingegeben werden, und eine spätere &quot;Spielzeug kaufen&quot;-Seite, auf der nur der Name des Tieres verwendet wird. Sie möchten den Namen des Tieres mit der auf der Registrierungsseite angegebenen Tierrasse verknüpfen können. Dazu können Sie Folgendes erstellen: [!DNL LookupRows] Umwandlung:

![](assets/cfg_TransformationType_LookupRows.png)

Analysieren wir dieses Beispiel anhand des vorherigen Entwurfs:

* Für jede Ausgabenzeile, die einen nicht leeren Wert von cs-uri-query(petname) aufweist:

   * Suchen Sie die letzte Eingabezeile so, dass

      * die Eingabezeile enthält einen nicht leeren Wert von cs-uri-query(petbreed) und
      * die x-trackingid der Eingabezeile entspricht der x-trackingid der Ausgabezeile und
      * der Wert von cs-uri-query(petname) der Eingabezeile entspricht dem Wert von cs-uri-query(petname) der Ausgabezeile;

* und legen Sie den Wert von x-pet-breed der Ausgabenzeile auf den Wert von cs-uri-query(petbreed) der Eingabezeile fest.

Die [!DNL LookupRows] Bei der Umwandlung wird der Name des Tieres (der Schlüssel) verwendet, um sicherzustellen, dass die Heimtierrasse sowohl mit der Registrierung des Tieres als auch mit dem Kauf von Spielzeugseiten verknüpft ist, sodass Sie die für jede Tierrasse gekauften Spielzeuge analysieren können, auch für Besucher mit mehreren Haustieren.
