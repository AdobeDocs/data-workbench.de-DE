---
description: Informationen zu den Transformationen, mit denen Sie Nachschlagedaten in den Datensatz integrieren können.
solution: Analytics
title: Definieren von Suchtransformationen
topic: Data workbench
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definieren von Suchtransformationen{#defining-lookup-transformations}

Informationen zu den Transformationen, mit denen Sie Nachschlagedaten in den Datensatz integrieren können.

Beachten Sie, dass nicht alle Typen in beiden Phasen des Datensatzerstellungsprozesses verwendet werden können.

* [Kategorisieren](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Kategorisieren {#section-8474376c14e54d14ae73749696ada468}

Die [!DNL Categorize] Transformation verwendet eine zweispaltige Nachschlagetabelle, die aus Paaren aus Musterzeichenfolge und Wert besteht. Während dieser Transformation liest der Data Workbench-Server jeden Ereignisdatensatz nacheinander und vergleicht den Inhalt eines angegebenen Felds im Datensatz mit jeder der in der ersten Spalte der Suchtabelle aufgeführten Musterzeichenfolgen. Wenn das angegebene Feld mit einer der Musterzeichenfolgen übereinstimmt, schreibt der Data Workbench-Server den Wert (in der zweiten Spalte zu finden), der mit dieser Musterzeichenfolge verknüpft ist, in ein angegebenes Ausgabefeld im Datensatz.

Die Zeichenfolgen in der ersten Spalte der Suchtabelle können optional mit dem Zeichen ^ beginnen und/oder mit dem Zeichen $ enden, um die Übereinstimmung am Anfang und/oder Ende zu erzwingen. Diese Transformation akzeptiert keine regulären Ausdrücke zum Definieren von Übereinstimmungsbedingungen in der ersten Spalte. Wenn der Eingabewert ein Vektor von Zeichenfolgen ist, wird jede Zeichenfolge durch die Transformation ausgeführt und das Ergebnis/die Ergebnisse werden an einen Ausgabezeichenfolgen-Vektor angehängt.

Eine [!DNL Categorize] Transformation ist im Allgemeinen einfacher und schneller als die Verwendung einer [!DNL Regular Expression] Transformation, um dasselbe zu erreichen.

>[!NOTE]
>
>Bei dem in verwendeten Teilzeichenfolgentest wird [!DNL Categorize] die Groß-/Kleinschreibung beachtet, sofern nicht anders mit dem [!DNL Case Sensitive] Parameter angegeben.

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
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
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2"> True oder false. Gibt an, ob beim Unterzeichenfolgentest die Groß-/Kleinschreibung beachtet wird. </td> 
   <td colname="col3"> true (wahr) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standardeinstellung </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn der Bedingungstest erfolgreich verläuft und kein Eintrag in der Kategorisierungsdatei mit der Eingabe übereinstimmt oder das Eingabefeld im angegebenen Protokolleintrag nicht definiert ist. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>String, der zum Trennen der Spalten in der Lookup-Datei verwendet wird. Muss ein einzelnes Zeichen lang sein. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste in den Trennzeichner-Parameter klicken, wird ein Menü " <span class="wintitle"> Einfügen</span> "angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mehrfachwerte </td> 
   <td colname="col2"> True oder false. Wenn "true", werden mehrere Zeilen in der Datei mit der Eingabe übereinstimmen, wird bei jeder Übereinstimmung ein Wert an den Ausgabevektor der Zeichenfolgen angehängt. Bei "false"wird nur die erste übereinstimmende Zeile in der Datei in der Ausgabe verwendet. Im letzteren Fall, wenn die Eingabe ein Vektor ist, ist die Ausgabe auch ein Vektor der entsprechenden Länge. Wenn die Eingabe eine einfache Zeichenfolge ist, ist die Ausgabe auch eine einfache Zeichenfolge. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei </td> 
   <td colname="col2"> Pfad und Dateiname der Kategorisierungsdatei. Relative Pfade beziehen sich auf den Installationsordner für den Data Workbench-Server. Diese Datei befindet sich normalerweise im Ordner "Suchen"im Installationsordner des Data Workbench-Servers. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Die Kategorisierungsdatei stimmt mit ihren Unterzeichenfolgen mit dem Wert in diesem Feld überein, um die übereinstimmende Zeile in der Datei zu identifizieren. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabe </td> 
   <td colname="col2"> Der Name des mit dem Ergebnis verknüpften Felds. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Überlegungen zur Kategorisierung**

* Änderungen an Lookup-Dateien in [!DNL Categorize] Konvertierungen, die in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definiert sind, erfordern eine erneute Transformation des Datensatzes. Suchdateien für [!DNL Categorize] Konvertierungen, die in der [!DNL Log Processing.cfg] Datei oder in einer [!DNL Log Processing Dataset Include] Datei definiert sind, unterliegen nicht dieser Einschränkung. Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Verarbeitung und Verarbeitung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] Konvertierungen, die in der [!DNL Log Processing.cfg] Datei oder in einer [!DNL Log Processing Dataset Include] Datei definiert sind, laden ihre Lookup-Dateien erneut, sobald sich die Lookup-Dateien ändern. Änderungen werden nicht rückwirkend angewendet, sondern gelten für alle Protokolldaten, die nach der Änderung gelesen werden.

In diesem Beispiel wird die Verwendung der [!DNL Categorize] Transformation zur Integration von Nachschlagedaten mit Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Nehmen wir an, eine bestimmte Website hat Geschäftsbereiche, und es ist erforderlich, dass Sie Vergleiche auf Grundlage des Traffic-Flusses und des durch die verschiedenen Abschnitte generierten Wertes anstellen und durchführen können. Sie können eine Lookup-Datei erstellen, die die Unterzeichenfolgen auflistet, die zur Identifizierung dieser verschiedenen Abschnitte verwendet werden.

Die Lookup-Datei [!DNL Lookups\custommap.txt] enthält die folgende Tabelle:

| /products/ | Produkte |
|---|---|
| ^/Sport/ | Sport |
| ^/News/ | Nachrichten |
| ... | ... |

Diese Kategorisierungsdatei ordnet alles, was die Zeichenfolge &quot;/products/&quot;enthält, dem Wert &quot;Produkte&quot;zu, alles was mit &quot;/sports/&quot;beginnt, dem Wert &quot;Sports&quot;und alles, was mit &quot;/news/&quot;beginnt, dem Wert &quot;News&quot;zu. Die folgende Kategorisierungstransformation verwendet den Wert im Feld &quot;cs-uri-stamm&quot;als Zeichenfolge, in der wir nach einer übereinstimmenden Teilzeichenfolge suchen. Das Ergebnis der Transformation wird in das Feld x-customMap platziert.

![](assets/cfg_TransformationType_Categorize.png)

Unter der Annahme, dass der Parameter &quot;Mehrere Werte&quot;auf &quot;false&quot;gesetzt ist, würde das Beispiel die folgenden Werte für x-customMap bei den aufgeführten Werten für cs-uri-stamm erzeugen.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Sport |
| [!DNL /sports/products/buy.php] | Produkte |
| [!DNL /news/headlines.php] | Nachrichten |
| [!DNL /news/products/subscribe.php] | Produkte |

Die Ausgabe basiert auf der Reihenfolge der Unterzeichenfolgen in der Abfragedatei. Der Stamm &quot;cs-uri&quot; [!DNL /sports/products/buy.php] gibt beispielsweise &quot;Produkte&quot;zurück. Obwohl der URI-Stamm mit &quot;/sports/&quot;beginnt, wird die Zeichenfolge &quot;/products/&quot;vor &quot;/sports/&quot;in der Lookup-Datei aufgeführt. Wenn der Parameter &quot;Mehrere Werte&quot;auf &quot;true&quot;gesetzt wurde, gibt es einen zusätzlichen Wert für x-customMap, da das letzte Beispiel zwei Zeilen in der Suchtabelle entsprechen würde: Produkte und Nachrichten.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

Die [!DNL FlatFileLookup] Transformation verwendet eine Nachschlagetabelle, die aus einer beliebigen Anzahl von Spalten und Zeilen besteht (auch wenn Sie sich daran erinnern, dass sie sich im Speicher befindet). Während dieser Art der Transformation liest der Data Workbench-Server jeden Ereignisdatensatz nacheinander und vergleicht den Inhalt eines angegebenen Felds im Datensatz mit jedem der Werte in einer angegebenen Spalte der Suchtabelle. Wenn eine Übereinstimmung vorliegt, schreibt der Data Workbench-Server einen oder mehrere Werte aus der übereinstimmenden Zeile in der Suchtabelle in eines oder mehrere festgelegte Ausgabefelder im Ereignisdatensatz.

Die bei dieser Transformation verwendete Nachschlagetabelle wird aus einer reduzierten Datei gefüllt, deren Speicherort Sie beim Definieren der Transformation angeben.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
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
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standardeinstellung </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und kein Eintrag in der Abfragedatei mit der Eingabe übereinstimmt. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>String, der zum Trennen der Spalten in der Lookup-Datei verwendet wird. Muss ein einzelnes Zeichen lang sein. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste in den Trennzeichner-Parameter klicken, wird ein Menü " <span class="wintitle"> Einfügen</span> "angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei </td> 
   <td colname="col2"> Pfad und Dateiname der Lookup-Datei. Relative Pfade beziehen sich auf den Installationsordner für den Data Workbench-Server. Diese Datei befindet sich normalerweise im Ordner "Suchen"im Installationsordner von Data Workbench Server. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kopfzeile </td> 
   <td colname="col2"> True oder false. Gibt an, dass die erste Zeile in der Tabelle eine Kopfzeile ist, die bei der Verarbeitung ignoriert werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> <span class="wintitle"> Spaltenname</span> ist der Name der Spalte, die für die Zuordnung der Eingabe zu der/den Zeilen in der Datei verwendet wird/werden. Wenn "Kopfzeile"den Wert "true"hat, kann dies der Name einer Spalte in der Lookup-Datei sein. Andernfalls muss es sich um die auf null basierende Spaltennummer handeln, mit der abgeglichen werden soll. <span class="wintitle"> Feldname</span> ist der Name des Felds, das zum Suchen der Zeile in der Nachschlagedatei verwendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mehrfachwerte </td> 
   <td colname="col2"> <p>True oder false. Bestimmt, ob ein einzelner Wert (eine übereinstimmende Zeile) oder mehrere Werte zurückgegeben werden sollen (einer für jede übereinstimmende Zeile). </p> <p> <p>Hinweis:  Wenn " <span class="wintitle"> Mehrere Werte</span> "auf "false"gesetzt ist, müssen Sie sicherstellen, dass nicht mehrere Übereinstimmungen vorhanden sind. Wenn mehrere Übereinstimmungen auftreten, gibt es keine Garantie, welche Übereinstimmung zurückgegeben wird. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgaben </td> 
   <td colname="col2"> <p>Ein Vektor von Spaltenobjekten (Ergebnisse), in dem jedes Objekt durch Spalten- und Feldnamen definiert wird. </p> <p> <span class="wintitle"> Spaltenname</span> ist die Spalte, aus der der Ausgabewert abgerufen wird. Wenn <span class="wintitle"> Kopfzeile</span> "true"ist, kann dies der Name einer Spalte in der Lookup-Datei sein. Andernfalls muss es sich um die auf null basierende Spaltennummer handeln, mit der abgeglichen werden soll. </p> <p> <span class="wintitle"> Feldname</span> ist der Name des Felds, das zum Erfassen der Ausgabe verwendet wird. Beachten Sie, dass dies ein Vektor von Ergebnissen sein kann, einer für jede Zeile, die identifiziert wird, wenn der Parameter "Mehrere Werte"wahr ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Überlegungen zu[!DNL FlatFileLookup]**

* Beim Abgleichen des Eingabefelds mit der Nachschlagedatei wird immer zwischen Groß- und Kleinschreibung unterschieden.
* Änderungen an Lookup-Dateien in [!DNL FlatFileLookup] Konvertierungen, die in der [!DNL Transformation.cfg] -Datei oder in den [!DNL Transformation Dataset Include] -Dateien definiert sind, erfordern eine Konvertierung des Datensatzes. Nachschlagedateien für [!DNL FlatFileLookup] Konvertierungen, die in der [!DNL Log Processing.cfg] Datei oder in den [!DNL Log Processing Dataset Include] Dateien definiert sind, unterliegen nicht dieser Einschränkung. Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Verarbeitung und Verarbeitung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] Konvertierungen in der [!DNL Log Processing.cfg] Datei oder in den [!DNL Log Processing Dataset Include] Dateien laden ihre Lookup-Dateien erneut, sobald sich die Lookup-Dateien ändern. Änderungen werden nicht rückwirkend angewendet, sondern gelten für alle Protokolldaten, die nach der Änderung gelesen werden.

In diesem Beispiel wird die Verwendung der [!DNL FlatFileLookup] Transformation zur Integration von Nachschlagedaten mit Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Angenommen, Sie möchten Website-Partner isolieren, die Traffic zu der Website weiterleiten, und ihre Partner-IDs in benutzerfreundlichere Namen umwandeln. Anschließend können Sie die benutzerfreundlichen Namen verwenden, um erweiterte Dimensionen und Visualisierungen zu erstellen, die der Geschäftsbeziehung klarer zugeordnet sind als die Site-zu-Site-Beziehung, die für das Routing von Traffic verwendet wird.

Die Beispieltransformation durchsucht das Feld cs(referrer-query) nach dem PartnerID-Namen-Wert-Paar. Wenn sich dieses befindet, [!DNL Lookups\partners.txt] wird die Lookup-Datei verwendet, um den PartnerID-Wert mit den Werten in der [!DNL Partner] Tabellenspalte zu vergleichen. Wenn sich eine Zeile befindet, erhält das Ausgabefeld x-partner-name den Namen aus der [!DNL PrintName] Spalte der angegebenen Zeile.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Wenn die Suchtabelle die folgenden Informationen enthält:

| ID | Partner | Gestartet | PrintName |
|---|---|---|---|
| 1 | P154 | 21.08.1999 | Yahoo |
| 2 | P232 | 10. Juli 2000 | Microsoft |
| 3 | P945 | 12.01.2001 | Amazon |

Die folgenden Beispiele würden sich wie folgt verändern:

* Wenn cs(referrer)(PartnerID) P232 zurückgegeben hat, erhält das Feld x-partner-name den Wert &quot;Microsoft&quot;.
* Wenn cs(referrer)(PartnerID) P100 zurückgegeben hat, erhält das Feld x-partner-name den Wert &quot;Kein Partner&quot;.
* Wenn cs(referrer)(PartnerID) nichts zurückgegeben hat, erhält das Feld x-partner-name den Wert &quot;Kein Partner&quot;, wie im Parameter Default angegeben.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

Die [!DNL ODBCLookup] Transformation funktioniert wie eine [!DNL FlatFileLookup] Transformation. Der einzige Unterschied besteht darin, dass die bei dieser Transformation verwendete Nachschlagetabelle aus einer ODBC-Datenbank und nicht aus einer einfachen Datei gefüllt wird.

>[!NOTE]
>
>[!DNL ODBCLookup] Transformationen können nur während der Umwandlungsphase des Dataset-Aufbaus ausgeführt werden. Adobe empfiehlt, nach Möglichkeit die [!DNL FlatFileLookup] Transformation anstelle der [!DNL ODBCLookup] Transformation zu verwenden. [!DNL FlatFileLookup] Transformationen sind von Natur aus zuverlässiger, da sie nicht von der Verfügbarkeit eines externen Systems abhängen. Außerdem besteht weniger Risiko, dass die Suchtabelle geändert wird, wenn sie sich in einer flachen Datei befindet, die Sie lokal steuern.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
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
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenquellenname </td> 
   <td colname="col2"> Ein DSN, das von einem Administrator des Data Workbench-Servercomputers, auf dem der Datensatz verarbeitet wird, bereitgestellt wird und sich auf die Datenbank bezieht, aus der Daten geladen werden sollen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenbankkennwort </td> 
   <td colname="col2">Das Kennwort, das beim Herstellen einer Verbindung zur Datenbank verwendet wird. Wenn im Datenquellen-Administrator <span class="wintitle"></span>ein Kennwort für das DSN konfiguriert wurde, bleibt dieses ggf. leer. Jedes hier bereitgestellte Kennwort setzt das für das DSN konfigurierte Kennwort im <span class="wintitle"> Datenquellen-Administrator</span>außer Kraft. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer-ID der Datenbank </td> 
   <td colname="col2">Die beim Herstellen einer Verbindung zur Datenbank zu verwendende Benutzer-ID. Wenn im Datenquellen-Administrator <span class="wintitle"></span>eine Benutzer-ID für das DSN konfiguriert wurde, bleibt diese ggf. leer. Jede hier bereitgestellte Benutzer-ID setzt die Benutzer-ID außer Kraft, die für das DSN im <span class="wintitle"> Datenquellenadministrator</span>konfiguriert wurde. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standardeinstellung </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und kein Eintrag in der Abfragedatei mit der Eingabe übereinstimmt. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabespalte </td> 
   <td colname="col2"> <span class="wintitle"> Spaltenname</span> ist der Spaltenname oder SQL-Ausdruck für die Daten, die mit der Eingabe abgeglichen werden. <span class="wintitle"> Feldname</span> ist der Name des Felds, das die zu suchenden Daten enthält. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mehrfachwerte </td> 
   <td colname="col2"> <p>True oder false. Bestimmt, ob ein einzelner Wert (eine übereinstimmende Zeile) oder mehrere Werte zurückgegeben werden sollen (einer für jede übereinstimmende Zeile). </p> <p> <p>Hinweis:  Wenn " <span class="wintitle"> Mehrere Werte</span> "auf "false"gesetzt ist, müssen Sie sicherstellen, dass nicht mehrere Übereinstimmungen vorhanden sind. Wenn mehrere Übereinstimmungen auftreten, gibt es keine Garantie, welche Übereinstimmung zurückgegeben wird. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabespalten </td> 
   <td colname="col2"> <p>Ein Vektor von Spaltenobjekten (Ergebnisse), bei dem jedes Objekt durch Spalten- und Feldnamen definiert wird. </p> <p> <span class="wintitle"> Spaltenname</span> ist der Name oder SQL-Ausdruck für die Spalte, aus der der Ausgabewert abgerufen wird. <span class="wintitle"> Feldname</span> ist der Name des Felds, das zum Erfassen der Ausgabe verwendet wird. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tabellenkennung</span> </td> 
   <td colname="col2"> Ein SQL-Ausdruck, der die Tabelle oder Ansicht benennt, aus der Daten geladen werden sollen. Eine typische Tabellenkennung ist die Form SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Die Parameter &quot;Datenquellenname&quot;, &quot; [!DNL Database User ID]Tabelle-ID&quot; [!DNL Database Password]und &quot;Tabellenname&quot;entsprechen den Parametern der gleichen Namen, die für ODBC-Datenquellen beschrieben werden. See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Im Gegensatz zu ODBC-Datenquellen erfordern [!DNL ODBCLookup] Transformationen keine zunehmende ID-Spalte. See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Das liegt daran, dass sich der Inhalt der Suchtabelle während der aktiven Ausführung des Datensatzes in keiner Weise ändern darf. Änderungen in einer Suchtabelle oder Ansicht können erst erkannt werden, wenn eine Umgestaltung erfolgt. Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Verarbeitung und Verarbeitung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Angenommen, Sie möchten veraltete DNS-Datensätze in die aktualisierten Datensätze konvertieren. Beide Datensätze werden in einer SQL-Datenbank gespeichert. Zur Durchführung dieser Aufgabe würden Sie auf eine Nachschlagetabelle verweisen, die aus der Datenbank generiert wird, und die veralteten DNS-Datensätze ersetzen.

Unsere Beispieltransformation durchsucht die Protokolleinträge nach dem s-dns-Feld und, falls vorhanden, die Suchtabelle VISUAL.LOOKUP wird verwendet, um den s-dns-Eintrag mit den Einträgen in der [!DNL OLDDNS] Tabellenspalte zu vergleichen. Befindet sich eine Zeile in der Tabelle, erhält das Ausgabefeld s-dns den aktualisierten DNS-Datensatz aus der [!DNL NEWDNS] Spalte der angegebenen Zeile.

![](assets/cfg_TransformationType_ODBCLookup.png)

