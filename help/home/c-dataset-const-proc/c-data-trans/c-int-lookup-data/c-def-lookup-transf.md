---
description: Informationen zu den Transformationen, mit denen Sie Suchdaten in den Datensatz integrieren können.
title: Definieren von Lookup-Umwandlungen
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 3%

---

# Definieren von Lookup-Umwandlungen{#defining-lookup-transformations}

Informationen zu den Transformationen, mit denen Sie Suchdaten in den Datensatz integrieren können.

Beachten Sie, dass nicht alle Typen in beiden Phasen des Datensatzerstellungsprozesses verwendet werden können.

* [Kategorisieren](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Kategorisieren {#section-8474376c14e54d14ae73749696ada468}

Die Umwandlung von [!DNL Categorize] verwendet eine zweispaltige Nachschlagetabelle, die aus Musterzeichenfolgen-/Wertpaaren besteht. Während dieser Transformation liest der Data Workbench-Server jeden Ereignisdatensatz abwechselnd und vergleicht den Inhalt eines angegebenen Felds im Datensatz mit jeder der in der ersten Spalte der Suchtabelle aufgelisteten Musterzeichenfolgen. Wenn das angegebene Feld mit einer der Musterzeichenfolgen übereinstimmt, schreibt der Data Workbench-Server den Wert (in der zweiten Spalte zu finden), der mit dieser Musterzeichenfolge verknüpft ist, in ein bestimmtes Ausgabefeld im Datensatz.

Die Zeichenfolgen in der ersten Spalte der Suchtabelle können optional mit dem Zeichen ^ beginnen und/oder im Zeichen $ enden, um die Übereinstimmung am Anfang und/oder Ende zu erzwingen. Diese Umwandlung akzeptiert keine regulären Ausdrücke zum Definieren von Übereinstimmungsbedingungen in der ersten Spalte. Wenn der Eingabewert ein Vektor von Zeichenfolgen ist, wird jede Zeichenfolge durch die Transformation ausgeführt und die Ergebnisse werden an einen Ausgabezeichenfolgenvektor angehängt.

Eine [!DNL Categorize]-Umwandlung ist im Allgemeinen einfacher und schneller als die Verwendung einer [!DNL Regular Expression]-Umwandlung, um dasselbe zu erreichen.

>[!NOTE]
>
>Beim in [!DNL Categorize] verwendeten Teilzeichenfolgentest wird zwischen Groß- und Kleinschreibung unterschieden, sofern nicht anders mit dem Parameter [!DNL Case Sensitive] angegeben.

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
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
   <td colname="col1"> Groß-/Kleinschreibung </td> 
   <td colname="col2"> Wahr oder falsch. Gibt an, ob beim Teilzeichenfolgentest die Groß-/Kleinschreibung beachtet wird. </td> 
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
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn der Bedingungstest erfolgreich ist und kein Eintrag in der Kategorisierungsdatei mit der Eingabe übereinstimmt oder das Eingabefeld im angegebenen Protokolleintrag nicht definiert ist. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>Zeichenfolge, die verwendet wird, um die Spalten in der Lookup-Datei zu trennen. Muss ein einzelnes Zeichen in der Länge sein. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste im Trennzeichen-Parameter klicken, wird das Menü <span class="wintitle"> Einfügen</span> angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mehrfachwerte </td> 
   <td colname="col2"> Wahr oder falsch. Wenn der Wert "true"lautet und mehrere Zeilen in der Datei mit der Eingabe übereinstimmen, führt jede Übereinstimmung dazu, dass ein Wert an den Ausgabevektor von Zeichenfolgen angehängt wird. Wenn "false", wird nur die erste übereinstimmende Zeile in der Datei in der Ausgabe verwendet. Wenn die Eingabe ein Vektor ist, ist die Ausgabe in letzterem Fall auch ein Vektor der äquivalenten Länge. Wenn es sich bei der Eingabe um eine einfache Zeichenfolge handelt, ist die Ausgabe auch eine einfache Zeichenfolge. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei </td> 
   <td colname="col2"> Pfad und Dateiname der Kategorisierungsdatei. Relative Pfade beziehen sich auf den Installationsordner für den Data Workbench-Server. Diese Datei befindet sich normalerweise im Ordner Suchen im Installationsordner des Data Workbench-Servers. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> Die Kategorisierungsdatei stimmt die zugehörigen Unterzeichenfolgen mit dem Wert in diesem Feld überein, um die übereinstimmende Zeile in der Datei zu identifizieren. </td> 
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

* Änderungen an Lookup-Dateien in [!DNL Categorize]-Transformationen, die in der [!DNL Transformation.cfg]-Datei oder in einer [!DNL Transformation Dataset Include]-Datei definiert sind, erfordern eine Neuumwandlung des Datensatzes. Suchdateien für [!DNL Categorize]-Transformationen, die in der [!DNL Log Processing.cfg]-Datei oder in einer [!DNL Log Processing Dataset Include]-Datei definiert sind, unterliegen dieser Einschränkung nicht. Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] in der  [!DNL Log Processing.cfg] Datei oder in einer  [!DNL Log Processing Dataset Include] Datei definierte Umwandlungen laden ihre Lookup-Dateien neu, sobald sich die Lookup-Dateien ändern. Änderungen werden nicht rückwirkend angewendet, sondern gelten für alle Protokolldaten, die nach der Änderung gelesen werden.

In diesem Beispiel wird die Verwendung der Umwandlung [!DNL Categorize] zur Integration von Suchdaten in Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Angenommen, eine bestimmte Website enthält Geschäftsbereiche, und es ist erforderlich, dass sie sich ansehen und Vergleiche auf der Grundlage von Traffic-Fluss und -Wert vornehmen kann, der von den verschiedenen Abschnitten generiert wurde. Sie können eine Lookup-Datei erstellen, in der die Unterzeichenfolgen aufgelistet werden, die zur Identifizierung dieser verschiedenen Abschnitte verwendet werden.

Die Lookup-Datei [!DNL Lookups\custommap.txt] enthält die folgende Tabelle:

| /products/ | Produkte |
|---|---|
| ^/Sport/ | Sport |
| ^/News/ | Nachrichten |
| ... | ... |

Diese Kategorisierungsdatei ordnet alles, das die Zeichenfolge &quot;/products/&quot;enthält, dem Wert &quot;Products&quot;zu, alles, was mit &quot;/sports/&quot;beginnt, dem Wert &quot;Sports&quot;und alles, was mit &quot;/news/&quot;beginnt, dem Wert &quot;News&quot; zu. Die folgende Kategorisierungstransformation verwendet den Wert im Feld &quot;cs-uri-stamm&quot;als Zeichenfolge, in der wir nach einer übereinstimmenden Teilzeichenfolge suchen. Das Ergebnis der Transformation wird in das Feld x-customMap eingefügt.

![](assets/cfg_TransformationType_Categorize.png)

Wenn der Parameter &quot;Multiple Values&quot;auf &quot;false&quot;gesetzt ist, würde das Beispiel die folgenden Werte für &quot;x-customMap&quot;mit den aufgelisteten Werten für cs-uri-Stamm generieren.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Sport |
| [!DNL /sports/products/buy.php] | Produkte |
| [!DNL /news/headlines.php] | Nachrichten |
| [!DNL /news/products/subscribe.php] | Produkte |

Die Ausgabe basiert auf der Reihenfolge der Unterzeichenfolgen in der Lookup-Datei. Beispielsweise gibt der cs-uri-Stamm [!DNL /sports/products/buy.php] &quot;Products&quot;zurück. Obwohl der URI-Stamm mit &quot;/sports/&quot;beginnt, wird die Zeichenfolge &quot;/products/&quot;vor &quot;/sports/&quot;in der Lookup-Datei aufgeführt. Wenn der Parameter &quot;Multiple Values&quot;auf &quot;true&quot;gesetzt wäre, gäbe es einen zusätzlichen Wert für &quot;x-customMap&quot;, da das letzte Beispiel mit zwei Zeilen in der Suchtabelle übereinstimmen würde: Produkte und Nachrichten.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

Die Umwandlung von [!DNL FlatFileLookup] verwendet eine Nachschlagetabelle, die aus einer beliebigen Anzahl von Spalten und Zeilen besteht (obwohl Sie sich daran erinnern, dass sie sich im Speicher befindet). Während dieser Umwandlung liest der Data Workbench-Server jeden Ereignisdatensatz einzeln und vergleicht den Inhalt eines bestimmten Felds im Datensatz mit jedem der Werte in einer bestimmten Spalte der Suchtabelle. Wenn eine Übereinstimmung vorliegt, schreibt der Data Workbench-Server einen oder mehrere Werte aus der entsprechenden Zeile in der Suchtabelle in ein oder mehrere ausgewiesene Ausgabefelder im Ereignisdatensatz.

Die bei dieser Umwandlung verwendete Nachschlagetabelle wird aus einer flachen Datei gefüllt, deren Speicherort Sie bei der Definition der Umwandlung angeben.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
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
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und kein Eintrag in der Lookup-Datei mit der Eingabe übereinstimmt. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trennzeichen </td> 
   <td colname="col2"> <p>Zeichenfolge, die verwendet wird, um die Spalten in der Lookup-Datei zu trennen. Muss ein einzelnes Zeichen in der Länge sein. </p> <p> Wenn Sie die Strg-Taste gedrückt halten und mit der rechten Maustaste im Trennzeichen-Parameter klicken, wird das Menü <span class="wintitle"> Einfügen</span> angezeigt. Dieses Menü enthält eine Liste von Sonderzeichen, die häufig als Trennzeichen verwendet werden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datei </td> 
   <td colname="col2"> Pfad und Dateiname der Lookup-Datei. Relative Pfade beziehen sich auf den Installationsordner für den Data Workbench-Server. Diese Datei befindet sich normalerweise im Ordner "Suchen"im Installationsordner von Data Workbench Server. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kopfzeile </td> 
   <td colname="col2"> Wahr oder falsch. Gibt an, dass die erste Zeile in der Tabelle eine Kopfzeile ist, die bei der Verarbeitung ignoriert werden soll. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe </td> 
   <td colname="col2"> <span class="wintitle"> Spalte </span> Der Name der Spalte, die für die Zuordnung der Eingabe zu der/den Zeile(n) in der Datei verwendet wird. Wenn die Kopfzeile "true"ist, kann dies der Name einer Spalte in der Lookup-Datei sein. Andernfalls muss dies die nullbasierte Spaltennummer sein, mit der abgeglichen werden soll. <span class="wintitle"> Feld </span> Name: der Name des Felds, das zum Suchen der Zeile in der Lookup-Datei verwendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mehrfachwerte </td> 
   <td colname="col2"> <p>Wahr oder falsch. Bestimmt, ob ein einzelner Wert (eine übereinstimmende Zeile) oder mehrere Werte zurückgegeben werden sollen (einer für jede übereinstimmende Zeile). </p> <p> <p>Hinweis:  Wenn <span class="wintitle"> Multiple Values</span> auf "false"gesetzt ist, müssen Sie sicherstellen, dass nicht mehrere Übereinstimmungen vorliegen. Wenn mehrere Übereinstimmungen auftreten, gibt es keine Garantie, welche Übereinstimmung zurückgegeben wird. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgaben </td> 
   <td colname="col2"> <p>Ein Vektor von Spaltenobjekten (Ergebnisse), in dem jedes Objekt durch Spalten- und Feldnamen definiert wird. </p> <p> <span class="wintitle"> Spalte </span> Die Spalte, aus der der Ausgabewert abgerufen wird. Wenn <span class="wintitle"> Kopfzeile</span> "true"ist, kann dies der Name einer Spalte in der Lookup-Datei sein. Andernfalls muss dies die nullbasierte Spaltennummer sein, mit der abgeglichen werden soll. </p> <p> <span class="wintitle"> Feld </span> Name des Felds, das zum Erfassen der Ausgabe verwendet wird. Beachten Sie, dass dies ein Vektor von Ergebnissen sein kann, eine für jede Zeile, die identifiziert wird, wenn der Parameter "Multiple Values"wahr ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Überlegungen zu[!DNL FlatFileLookup]**

* Beim Abgleichen des Eingabefelds mit der Lookup-Datei wird immer zwischen Groß- und Kleinschreibung unterschieden.
* Änderungen an Lookup-Dateien in [!DNL FlatFileLookup] -Transformationen, die in der [!DNL Transformation.cfg] -Datei oder in [!DNL Transformation Dataset Include] -Dateien definiert sind, erfordern eine Neuumwandlung des Datensatzes. Suchdateien für [!DNL FlatFileLookup]-Transformationen, die in der [!DNL Log Processing.cfg]-Datei oder in [!DNL Log Processing Dataset Include]-Dateien definiert sind, unterliegen dieser Einschränkung nicht. Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] Transformationen in der  [!DNL Log Processing.cfg] Datei oder in  [!DNL Log Processing Dataset Include] Dateien laden ihre Lookup-Dateien neu, sobald sich die Lookup-Dateien ändern. Änderungen werden nicht rückwirkend angewendet, sondern gelten für alle Protokolldaten, die nach der Änderung gelesen werden.

In diesem Beispiel wird die Verwendung der Umwandlung [!DNL FlatFileLookup] zur Integration von Suchdaten in Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Angenommen, Sie möchten Website-Partner isolieren, die den Traffic an die Website weiterleiten, und ihre Partner-IDs in benutzerfreundlichere Namen umwandeln. Anschließend können Sie die benutzerfreundlichen Namen verwenden, um erweiterte Dimensionen und Visualisierungen zu erstellen, die der Geschäftsbeziehung besser zugeordnet sind als die Site-zu-Site-Beziehung, die für das Routing von Traffic verwendet wird.

Die Beispielumwandlung durchsucht das Feld cs(referrer-query) nach dem PartnerID-Namens-Wert-Paar. Wenn sich dieses Feld befindet, wird die Lookup-Datei [!DNL Lookups\partners.txt] verwendet, um den PartnerID-Wert mit den Werten in der Spalte [!DNL Partner] der Tabelle zu vergleichen. Wenn sich eine Zeile befindet, erhält das Ausgabefeld x-partner-name den Namen aus der Spalte [!DNL PrintName] der identifizierten Zeile.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Wenn die Suchtabelle die folgenden Informationen enthält:

| ID | Partner | Gestartet | PrintName |
|---|---|---|---|
| 1 | P154 | 21.08.1999 | Yahoo |
| 2 | P232 | 10. Juli 2000 | Microsoft |
| 3 | P945 | 12. Januar 2001 | Amazon |

Die folgenden Beispiele würden sich wie folgt transformieren:

* Wenn cs(referrer)(PartnerID) P232 zurückgegeben hat, erhält das Feld x-partner-name den Wert &quot;Microsoft&quot;.
* Wenn cs(referrer)(PartnerID) P100 zurückgegeben hat, erhält das Feld x-partner-name den Wert &quot;Kein Partner&quot;.
* Wenn cs(referrer)(PartnerID) nichts zurückgegeben hat, erhält das Feld x-partner-name den Wert &quot;Kein Partner&quot;, wie im Parameter &quot;Standard&quot;angegeben.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

Die Umwandlung [!DNL ODBCLookup] funktioniert wie eine Umwandlung von [!DNL FlatFileLookup]. Der einzige Unterschied besteht darin, dass die bei dieser Umwandlung verwendete Suchtabelle aus einer ODBC-Datenbank und nicht aus einer reduzierten Datei gefüllt wird.

>[!NOTE]
>
>[!DNL ODBCLookup] Transformationen können nur während der Umwandlungsphase des Datensatzerstellungsprozesses ausgeführt werden. Wenn möglich, empfiehlt Adobe, die Umwandlung [!DNL FlatFileLookup] anstelle der Umwandlung [!DNL ODBCLookup] zu verwenden. [!DNL FlatFileLookup] Transformationen sind von Natur aus zuverlässiger, da sie nicht von der Verfügbarkeit eines externen Systems abhängen. Außerdem besteht ein geringeres Risiko, dass die Suchtabelle geändert wird, wenn sie sich in einer flachen Datei befindet, die Sie lokal steuern.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
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
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenquellenname </td> 
   <td colname="col2"> Ein DSN, das von einem Administrator des Data Workbench-Servercomputers bereitgestellt wird, auf dem der Datensatz verarbeitet wird, und sich auf die Datenbank bezieht, aus der Daten geladen werden sollen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datenbankkennwort </td> 
   <td colname="col2">Das Kennwort für die Verbindung mit der Datenbank. Wenn im <span class="wintitle"> Data Source Administrator</span> ein Kennwort für den DSN konfiguriert wurde, kann dies leer gelassen werden. Jedes hier angegebene Kennwort setzt das für den DSN konfigurierte Kennwort im <span class="wintitle"> Datenquellenadministrator</span> außer Kraft. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer-ID der Datenbank </td> 
   <td colname="col2">Die Benutzer-ID, die beim Herstellen einer Verbindung zur Datenbank verwendet wird. Wenn im <span class="wintitle"> Data Source Administrator</span> eine Benutzer-ID für das DSN konfiguriert wurde, kann dies leer gelassen werden. Jede hier bereitgestellte Benutzer-ID setzt die Benutzer-ID außer Kraft, die für den DSN in <span class="wintitle"> Data Source Administrator</span> konfiguriert ist. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Der Standardwert, der verwendet wird, wenn die Bedingung erfüllt ist und kein Eintrag in der Lookup-Datei mit der Eingabe übereinstimmt. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabespalte </td> 
   <td colname="col2"> <span class="wintitle"> Spalte </span> Name: Spaltenname oder SQL-Ausdruck für die Daten, die mit der Eingabe abgeglichen werden. <span class="wintitle"> Feld </span> Der Name des Felds, das die zu suchenden Daten enthält. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mehrfachwerte </td> 
   <td colname="col2"> <p>Wahr oder falsch. Bestimmt, ob ein einzelner Wert (eine übereinstimmende Zeile) oder mehrere Werte zurückgegeben werden sollen (einer für jede übereinstimmende Zeile). </p> <p> <p>Hinweis:  Wenn <span class="wintitle"> Multiple Values</span> auf "false"gesetzt ist, müssen Sie sicherstellen, dass nicht mehrere Übereinstimmungen vorliegen. Wenn mehrere Übereinstimmungen auftreten, gibt es keine Garantie, welche Übereinstimmung zurückgegeben wird. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ausgabespalten </td> 
   <td colname="col2"> <p>Ein Vektor von Spaltenobjekten (Ergebnissen), wobei jedes Objekt durch Spalten- und Feldnamen definiert wird. </p> <p> <span class="wintitle"> Spalte </span> Name: der Name oder SQL-Ausdruck für die Spalte, aus der der Ausgabewert abgerufen wird. <span class="wintitle"> Feld </span> Name des Felds, das zum Erfassen der Ausgabe verwendet wird. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tabellenkennung</span> </td> 
   <td colname="col2"> Ein SQL-Ausdruck, der die Tabelle oder Ansicht benennt, aus der Daten geladen werden sollen. Eine typische Tabellenkennung ist vom Formular SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Die Parameter für den Datenquellennamen, [!DNL Database User ID], [!DNL Database Password] und die Tabellenkennung sind mit den Parametern der gleichen Namen identisch, die für ODBC-Datenquellen beschrieben werden. Siehe [ODBC-Datenquellen](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Im Gegensatz zu ODBC-Datenquellen erfordern [!DNL ODBCLookup]-Transformationen keine zunehmende ID-Spalte. Siehe [ODBC-Datenquellen](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Dies liegt daran, dass sich der Inhalt der Suchtabelle während der aktiven Verwendung des Datensatzes in keiner Weise ändern darf. Änderungen in einer Suchtabelle oder Ansicht können erst erkannt werden, wenn eine Neuumwandlung erfolgt. Weitere Informationen zur erneuten Verarbeitung Ihrer Daten finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Angenommen, Sie möchten veraltete DNS-Einträge in die aktualisierten Einträge konvertieren. Beide Datensätze werden in einer SQL-Datenbank gespeichert. Zu diesem Zweck würden Sie eine aus der Datenbank generierte Nachschlagetabelle referenzieren und die veralteten DNS-Einträge ersetzen.

Unsere Beispielumwandlung durchsucht die Protokolleinträge nach dem Feld s-dns und, falls vorhanden, wird die Suchtabelle VISUAL.LOOKUP verwendet, um den Eintrag s-dns mit den Einträgen in der Spalte [!DNL OLDDNS] der Tabelle zu vergleichen. Wenn sich eine Zeile in der Tabelle befindet, erhält das Ausgabefeld s-dns den aktualisierten DNS-Eintrag aus der Spalte [!DNL NEWDNS] der identifizierten Zeile.

![](assets/cfg_TransformationType_ODBCLookup.png)
